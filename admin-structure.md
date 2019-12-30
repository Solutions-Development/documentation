# Admin Console data types & parameter structure


## Meta:
- Crear Congreso
- Crear Conferencista
- Agendar Conferencia (conferencista-side)
##

> Login

| Field          | Parameter Name        | Data Type
|--------------- |-----------------------|----------
| Usuario | username | string
| Contrasena | password | string

> Informacion General Congreso - Section A

| Field          | Parameter Name        | Data Type
|--------------- |-----------------------|----------
| Titulo Congreso     | tituloCongreso | String
| Fecha de Inicio/Hora         | fechaInicio  | String
| Fecha de Fin/Hora        |fechaFin  | String
| Venue/Sede     | venue | String
| Banner           | banner | base64 encoded image string (SEE SECTION A - BASE64)
| Logo         | logo | base64 encoded image string (SEE SECTION A - BASE64)

> Section A POST example - Web

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
> Section A - BASE64 - Web - Mobile
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
> Section B - Conferencistas - Web - Mobile

| Field          | Parameter Name        | Data Type
|--------------- |-----------------------|----------
|Nombre Completo | nombre | String
|Foto de Perfil | fotoPerfil| String
|Pais | pais| String
|Telefono Movil | telefonoMovil| String
|Telefono Trabajo | telefonoTrabajo| String
|Email | email| String
|Estudio de Grado | estudioGrado| String
|Especialidad | especialidad| String
|Sub Especialidad / Doctorado | doctorado| String
|Practica Publica / Privada | practicas| String
|Detalle Membresias Profesionales / Gremiales | membresias| String
|Pais de Partida | paisPartida| String
|Cantidad de Personas | cantidadPersonas| String
|Numero de Pasaporte | numeroPasaporte| String
|Hora de Viaje | horaViaje| String
|Lugar de Partida  | lugarPartida| String
|Lugar de Llegada | lugarLlegada| String



> Login POST RESPONSE - Web

```json
{
 "responseStatus": "200",
 "authenticated": "yes" | "no",
 "role": "user" | "doctor" | "admin" | "custom"
}
```
> Agenda Conferencistas GET Request -  Web - Mobile
```json

{
 "nombre": "Felix Bautista",
 "role": "doctor",
 "conferencias": ["Cirugia de Rodilla", "Practicas de Implante Tobillo", "Cuidado del Hombro"],
 "id": [145, 332, 442]
}
```
> Home Screen - Mobile

| Field          | Parameter Name        | Data Type
|--------------- |-----------------------|----------
| Header     | homeScreenHeader | String
| Icons         | icon  | base64 encoded image string
| Icon Name        | iconName  | string
