---
title: 'Frequently Asked Questions'
metadata:
    description: 'Frequently Asked Questions'
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
        - course
    tag:
        - faq
---
---

[Can I install vtDZiner](../faq/item.md#can-i-install-vtdziner) <br>
[How can I add new fonts to pdfmaker? I need to use Helvetica Neue Light](../faq/item.md#how-can-i-add-new-fonts-to-pdfmaker-i-need-to-use-helvetica-neue-light)<br>
[Can I install the theme from neevtech](../faq/item.md#can-i-install-the-theme-from-neevtech)<br>

<div class="notices blue">
<h3>Can I install vtDZiner</h3>
</div>


 ### [Yes]() 

---

<div class="notices blue">
<h3>How can I add new fonts to pdfmaker? I need to use Helvetica Neue Light</h3>
</div>

<h3>PDFMaker uses the mpdf library so you'll find a definitive answer at <br>
<a href="http://www.mpdf1.com/mpdf/index.php">http://www.mpdf1.com/mpdf/index.php</a> or <br>
<a href="https://discussions.vtiger.com/index.php?p=/discussion/53074/pdf-maker-own-font/p1">https://discussions.vtiger.com/index.php?p=/discussion/53074/pdf-maker-own-font/p1</a> <br>
I've styled my pdfs with a css file referenced from each pdf template. If you can do it this will be the way.<br><br>
Matt Bracewell </h3>

---

<div class="notices blue">
<h3>Can I install the theme from neevtech<h3>
</div>

<h3>Yes. Just you have to download the zip from <br>
<a href="http://www.neevtech.com/vtigerpage/">http://www.neevtech.com/vtigerpage/</a> and extract.  <br>

- Inside the new folder you have to copy the script called neevdbentry.php in corebos root directory and the directory inside enterdata/themes/ inside theme corebos directory.<br>
- Now you have to edit the file Smarty/templates/Header.tpl and add the next line:
<div class="notices blue">
{if $THEME eq 'enterdata'}      
       <script type="text/javascript" src="themes/enterdata/theme.js"></script>
   {/if}
</div>
- Finally you have to execute the script neevdbentry.php from your browser like: <br> <a href="http://your_corebos/neevdbentry.php">http://your_corebos/neevdbentry.php</a>

After that you will can select this new theme from user preferences.
</h3>