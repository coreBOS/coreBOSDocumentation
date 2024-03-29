---
title: 'Server Side Events'
metadata:
    description: 'Learn how to implement Server Side Events in coreBOS.'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - development
        - serversideevents
    tag:
        - howto
        - sse
---

coreBOS supports Server Side Events.

===

[See how coreBOS does it reading the Business Action::Launch script section!](../../../05.configuration-tools/03.business-actions/item.md)

Server side events in coreBOS are very easy to implement. Since you have control of many ways to add javascript code to the application and also many ways to add PHP code, you can insert your EventSource javascript code and call a PHP script via ajax in order for it to send the header and subsequent messages.

You can find an example of this in the [Import/Export Relations Extension](https://github.com/tsolucio/coreBOSIERelations) which uses SSE to launch the import process and inform the user of the progress of the operation.

In that code, you can see that the launchImportProcess() function in coreBOSIERelations.js creates the EventSource object against an AJAX URL to the module, which calls the PHP script cbierelate.php. The messages sent by this script are read by the EventSource object and updated on the screen accordingly.

There is a lot of information and many examples of how SSE works on the internet, but I [add here a standalone example](sse.zip) upon which I constructed the code in coreBOSIERelations

**es.html**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8" />
<script>
    var es;

    function startTask() {
        es = new EventSource('source.php');

        //a message is received
        es.addEventListener('message', function(e) {
            var result = JSON.parse(e.data);

            addLog(result.message);

            if (e.lastEventId == 'CLOSE') {
                addLog('Received CLOSE closing');
                es.close();
                var pBar = document.getElementById('progressor');
                pBar.value = pBar.max; //max out the progress bar
            } else {
                var pBar = document.getElementById('progressor');
                pBar.value = result.progress;
                var perc = document.getElementById('percentage');
                perc.innerHTML = result.progress + "%";
                perc.style.width = (Math.floor(pBar.clientWidth * (result.progress / 100)) + 15) + 'px';
            }
        });

        es.addEventListener('error', function(e) {
            addLog('Error occurred');
            es.close();
        });
    }

    function stopTask() {
        es.close();
        addLog('Interrupted');
    }

    function addLog(message) {
        var r = document.getElementById('results');
        r.innerHTML += message + '<br>';
        r.scrollTop = r.scrollHeight;
    }
</script>
</head>
<body>
    <br />
    <input type="button" onclick="startTask();" value="Start Long Task" />
    <input type="button" onclick="stopTask();" value="Stop Task" />
    <br />
    <br />

    <p>Results</p>
    <br />
    <div id="results"
        style="border: 1px solid #000; padding: 10px; width: 300px; height: 150px; overflow: auto; background: #eee;"></div>
    <br />

    <progress id='progressor' value="0" max='100' style=""></progress>
    <span id="percentage"
        style="text-align: right; display: block; margin-top: 5px;">0</span>
</body>
</html>
```

**source.php**

```php
<?php
header('Content-Type: text/event-stream');
header('Cache-Control: no-cache'); // recommended to prevent caching of event data.

function sendMsg($msg) {
    echo "data: $msg" . PHP_EOL;
    echo PHP_EOL;
    flush();
}

function send_message($id, $message, $progress) {
    $d = array(
        'message' => $message,
        'progress' => $progress
    );
    echo "id: $id" . PHP_EOL;
    echo "data: " . json_encode($d) . PHP_EOL;
    echo PHP_EOL;
    ob_flush();
    flush();
}

// LONG RUNNING TASK
for ($i = 1; $i <= 10; $i ++) {
    send_message( $i, 'on iteration ' . $i . ' of 10', $i * 10 );
    sleep(1);
}

send_message('CLOSE', 'Process complete');
?>
```