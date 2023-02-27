# Maps-GPS-Js
fitur untuk mencari titik kordinat pada aplikasi web dengan javascript
``` html
1.langkah pertama:
        <form action="" method="post" id="maps" hidden>
        <input type="text" name="lat" id="lat">
        <input type="text" name="long" id="long">
        </form>
        <button name="cek" id="cek">Cek Maps</button>
      
      
2.langkah kedua:
      <script type="text/javascript">
        handlePermission(this);
        function handlePermission(geoBtn) {
            navigator.permissions.query({name:'geolocation'}).then(function(result) {
                if( result.state == 'prompt' || result.state == 'granted' )
                {
                    navigator.geolocation.getCurrentPosition(revealPosition,showErrorLocation);
                }else{
                    console.log( result.state );
                }
                result.onchange = function() {
                    console.log(result.state);
                }
            });
        }
        function revealPosition(position)
        {
            var data = position.coords;
            var lat  = data.latitude;
            var long = data.longitude;
            //alert("Lat : " + lat + ", Long: " + long );
            //window.location.href='https://earth.google.com/web/@'+lat+','+long+',25.06630657a,1020.05133961d,35y,0h,0t,0r';
            var latt=document.querySelector('#maps #lat');
            latt.value=lat;
            var longg=document.querySelector('#maps #long');
            longg.value=long;
        }
        function showErrorLocation(error) {
            switch(error.code) {
            case error.PERMISSION_DENIED:
                var err = "User denied the request for Geolocation."
                break;
            case error.POSITION_UNAVAILABLE:
                var err = "Location information is unavailable."
                break;
            case error.TIMEOUT:
                var err = "The request to get user location timed out."
                break;
            case error.UNKNOWN_ERROR:
                var err = "An unknown error occurred."
                break;
            }
            console.log(err);
        }

        var cek=document.querySelector('#cek');
        cek.addEventListener('click',function(){
            var latt=document.querySelector('#maps #lat').value;
            var longg=document.querySelector('#maps #long').value;
            window.location.href='https://earth.google.com/web/@'+latt+','+longg+',25.06630657a,1020.05133961d,35y,0h,0t,0r';
        });
    </script>
      
3.langkah ketiga:
      <DOCTYPE html>
      <html lang="en">
      <head>
          <meta charset="UTF-8">
          <meta http-equiv="X-UA-Compatible" content="IE=edge">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A==" crossorigin="" />
          <!-- bootstrap cdn  -->
          <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css" integrity="sha384-TX8t27EcRE3e/ihU7zmQxVncDAy5uIKz4rEkgIXeMed4M0jlfIDPvg6uqKI2xXr2" crossorigin="anonymous">
          <title>Jasakumedia.Maps</title>
      </head>
      <body>

          <form action="" method="post" id="maps" hidden>
              <input type="text" name="lat" id="lat">
              <input type="text" name="long" id="long">
          </form>
          <button name="cek" id="cek">Cek Maps</button>

          <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.4.2/jquery.min.js"></script>
          <script type="text/javascript" src="http://maps.google.com/maps/api/js?sensor=false"></script>
          <script src="http://maps.google.com/maps?file=api&v=2&key=ABQIAAAA7A7Eu8gZ_mTslgWnRR9TGRQByQgPDcFg0q0wOb9u6rRtBOFyKBQD4QgfPHRxBFGL7JviJdz_jAlHfw" type="text/javascript"></script>
          <script type="text/javascript">
              handlePermission(this);
              function handlePermission(geoBtn) {
                  navigator.permissions.query({name:'geolocation'}).then(function(result) {
                      if( result.state == 'prompt' || result.state == 'granted' )
                      {
                          navigator.geolocation.getCurrentPosition(revealPosition,showErrorLocation);
                      }else{
                          console.log( result.state );
                      }
                      result.onchange = function() {
                          console.log(result.state);
                      }
                  });
              }
              function revealPosition(position)
              {
                  var data = position.coords;
                  var lat  = data.latitude;
                  var long = data.longitude;
                  //alert("Lat : " + lat + ", Long: " + long );
                  //window.location.href='https://earth.google.com/web/@'+lat+','+long+',25.06630657a,1020.05133961d,35y,0h,0t,0r';
                  var latt=document.querySelector('#maps #lat');
                  latt.value=lat;
                  var longg=document.querySelector('#maps #long');
                  longg.value=long;
              }
              function showErrorLocation(error) {
                  switch(error.code) {
                  case error.PERMISSION_DENIED:
                      var err = "User denied the request for Geolocation."
                      break;
                  case error.POSITION_UNAVAILABLE:
                      var err = "Location information is unavailable."
                      break;
                  case error.TIMEOUT:
                      var err = "The request to get user location timed out."
                      break;
                  case error.UNKNOWN_ERROR:
                      var err = "An unknown error occurred."
                      break;
                  }
                  console.log(err);
              }

              var cek=document.querySelector('#cek');
              cek.addEventListener('click',function(){
                  var latt=document.querySelector('#maps #lat').value;
                  var longg=document.querySelector('#maps #long').value;
                  window.location.href='https://earth.google.com/web/@'+latt+','+longg+',25.06630657a,1020.05133961d,35y,0h,0t,0r';
              });
          </script>

      </body>
      </html>
      
Perlu di ingat, fitur ini membutuhkan akses internet dan cookie.
```
      
      
# Support
Follow my instagram : https://www.instagram.com/wahyu_illahi07/ 
Youtube Channel : https://www.youtube.com/playlist?list=PL2DC6n3PrEKVXN9nvzONe9idXa9BgCusj
