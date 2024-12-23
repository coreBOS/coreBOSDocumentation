---
title: 'How to update an image field from code'
metadata:
    description: 'How to update an image field from code'
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
        - unittest
    tag:
        - workflow
---

Don't complicate it: use Web Service API

===

```php
require_once 'include/Webservices/Revise.php';

require_once 'include/tcpdf/tcpdf_barcodes_2d.php';
require_once 'include/tcpdf/tcpdf_barcodes_1d.php';
$barcodeobj = new TCPDF2DBarcode('http://www.tcpdf.org', 'QRCODE,H');
//$barcodeobj = new TCPDFBarcode('http://www.tcpdf.org', 'bar_codes');

// export as PNG image
$data = $barcodeobj->getBarcodePngData(3, 3, array(0,128,0));

$model_filename=array(
	'name'=>'barcode',  // no slash nor paths in the name
	'size'=>strlen($data),
	'type'=>'image/png',
	'content'=>base64_encode($data)
);

$assetData  = array(
	'attachments' => array(
		'cf_1114' => $model_filename,
	),
	'id'=> '29x4062',
);
vtws_revise($assetData, $current_user);
```

Now, if you need to do this from inside a workflow task you could run into a loop because vtws\_revise will actually launch the workflows again. In this case setup the environment for a direct file upload and call **insertIntoAttachment** like this:

```php
require_once 'include/tcpdf/tcpdf_barcodes_2d.php';
require_once 'include/tcpdf/tcpdf_barcodes_1d.php';
$barcodeobj = new TCPDF2DBarcode('http://www.tcpdf.org', 'QRCODE,H');
//$barcodeobj = new TCPDFBarcode('http://www.tcpdf.org', 'bar_codes');

// export as PNG image
$data = $barcodeobj->getBarcodePngData(3, 3, array(0,128,0));
$attachment_name = 'BARCODEname.png';
$filepath = $root_directory.'cache/'.$attachment_name;
file_put_contents($filepath, $data);
$_FILES['cf_1114'] = array(
	'name' => $attachment_name,
	'type' => 'image/png',
	'tmp_name' => $filepath,
	'error' => 0,
	'size' => strlen($data),
);
$a = CRMEntity::getInstance('Assets');
$a->id = 4062;
$a->mode = 'edit';
$a->DirectImageFieldValues['cf_1114'] = $attachment_name; // this is to delete previous image with the same name
$a->retrieve_entity_info(4062, 'Assets');
$a->insertIntoAttachment(4062, 'Assets');
unlink($filepath);
```