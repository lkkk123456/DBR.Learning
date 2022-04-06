# DBR.Learning

//Create a simple barcode scanner (video and shows the content)

<!DOCTYPE html>
<html>

<body>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-javascript-barcode@9.0.0/dist/dbr.js"></script>
  <script>
        // specify a license, you can visit https://www.dynamsoft.com/customer/license/trialLicense?utm_source=guide&product=dbr&package=js to get your own trial license good for 30 days. 
        Dynamsoft.DBR.BarcodeScanner.license = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
        // initializes and uses the library
        (async () => {
            let scanner = await Dynamsoft.DBR.BarcodeScanner.createInstance();
            scanner.onFrameRead = results => {
                if (results.length > 0) console.log(results);
            };
            scanner.onUniqueRead = (txt, result) => {
                alert(txt);
            };
            await scanner.show();
        })();
    </script>
</body>

</html>

