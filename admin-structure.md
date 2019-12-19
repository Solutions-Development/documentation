# Admin Console data types & parameter structure

> Informacion General Congreso - Section A


| Field          | Parameter Name        | Data Type
|--------------- |-----------------------|----------
| Titulo Congreso     | tituloCongreso | String
| Fecha de Inicio/Hora         | fechaInicio  | String
| Fecha de Fin/Hora        |fechaFin  | String
| Venue/Sede     | venue | String
| Banner           | banner | base64 encoded image string
| Logo         | logo | base64 encoded image string

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
