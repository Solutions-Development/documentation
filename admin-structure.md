# Admin Console data types & parameter structure

> Informacion General Congreso - Section A


| Field          | Parameter Name        | Data Type
|--------------- |-----------------------|----------
| Titulo Congreso     | tituloCongreso | String
| Fecha de Inicio/Hora         | fechaInicio  | String
| Fecha de Fin/Hora        |fechaFin  | String
| Venue/Sede     | venue | String
| Banner           | banner | base64 encoded image string (SEE SECTION A - BASE64)
| Logo         | logo | base64 encoded image string (SEE SECTION A - BASE64)

> Section A POST example

```js
{
 "tituloCongreso": "XXVII Congreso de Ortopedia y Traumatologia 2019",
 "fechaInicio": {
      "date": "25/03/2019",
      "time": "3:00PM"
  },
  "venue": "Hard Rock Hotel & Casino, Punta Cana",
  "banner": "base64:ay;;'3rf/$cvi",
  "logo": "base64:ay;;'3rf/$cvi"
}
```
> Section A - BASE64
```js
var fs = require('fs');

// function to encode file data to base64 encoded string
function base64_encode(file) {
    // read binary data
    var bitmap = fs.readFileSync(file);
    // convert binary data to base64 encoded string
    return new Buffer(bitmap).toString('base64');
}

var base64str = Promise.resolve(base64_encode("PATH TO LOGO AND/OR BANNER IMAGE")).then(async rsp => {
    console.log(rsp); // RSP IS THE BASE64 STRING TO BE POSTED TO Api
});
```
