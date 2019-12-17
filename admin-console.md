> Congreso Admin Console
```js
POST /conferencistas

nombre: { type: String },
imagen: { type: String },
pais:   { type: String },
telefonoPersonal: { type: String },
telefonoTrabajo: { type: String },
email: { type: String },
estudioGrado: { type: String },
especialidad: { type: String },
doctorado: { type: String },
practica: { type: String },
membresia: { type: String },
paisPartida: { type: String },
cantidadPersonas: { type: String },
numeroPasaporte: { type: String },
horaViaje: { type: String },
lugarPartida: { type: String },
lugarLlegada: { type: String }

FORMAT

{
 exampleParam: "example value"
}

RESPONSE STATUS 200
{
 message: "OK"
}
```
