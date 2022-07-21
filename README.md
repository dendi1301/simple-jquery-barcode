# simple-jquery-barcode
Simple JQuery Barcode

Referensi : https://github.com/jbdemonte/barcode

# Barcode EAN 13
Proyek ini adalah menggunakan bahasa HTML dan JQuery untuk membuat atau menampilkan barcode EAN 13.
```
<script type="text/javascript" src="https://code.jquery.com/jquery-1.12.4.min.js"></script>
<script type="text/javascript" src="js/jquery-barcode.js"></script>
<script type="text/javascript">
    function generateBarcode() {
        var value = $("#barcodeValue").val();
        var btype = "ean13";
        // barcodeType = ['ean8','ean13','upc','std25','int25','code11','code39','code93','code128','codabar','msi','datamatrix'];
        // barcodeType = ['EAN 8','EAN 13','UPC','Standard 2 of 5 (industrial)','Interleaved 2 of 5','Code 11','Code 39','Code 93','Code 128','Codabar','MSI','Data Matrix'];

        var settings = {
            output: "svg",
            bgColor: "#FFFFFF",
            color: "#000000",
            barWidth: "1",
            barHeight: "30",
        };
        $("#barcodeTarget").html("").show().barcode(value, btype, settings);
        $('#barcodeValue').focus();
    }


    $(function () {
        $('input').focus(function () {
            return $(this).select();
        })
        $('#barcodeValue').keypress(function (ev) {
            var event = ev.keyCode | ev.witch;
            if (event == 13) {
                generateBarcode();
            }
        })
        generateBarcode();
    });
</script> 
Please fill in the code :
<br />
<input type="text" id="barcodeValue">
<button type="button" onclick="generateBarcode()">Generate the barcode</button>
<div id="barcodeTarget" class="barcodeTarget"></div>
```
