# Preguntas de Comprension‌‌‌​‌​‌‌​﻿‍‍​﻿‍​‌‍​‌​﻿‌‌​﻿​‌​﻿‌‌​﻿‌‌​﻿‍​​﻿​​​﻿‌‌​﻿​‌‌‍​‍‌‍‌‌​﻿​﻿​﻿​​​﻿​﻿​﻿‍​

Responder con sus propias palabras (minimo 3-4 lineas cada una).

---

## 1. Infraestructura
**Si tu app necesita conectarse a PostgreSQL pero el contenedor de la BD tarda 30 segundos en arrancar, que pasa? Como lo solucionarias?**

Si la conexión tarda mucho tiempo en realizarse podrian saltar errores ya que no se conectaria a la base de datos.
Para solucionarlo se pueden poner metodos de reinicio en caso de que no se haya conectado, para forzar que se conecten una vez reiniciado.

## 2. JPA
**Por que `findAll()` puede ser lento con 100,000 registros? Que alternativa usarias?**

Para 100000 registros findAll() tardaría mucho y podria dar a lugar a fallo una vez los intentase cargar en memoria, pudiendo provocar errores si no hay espacio.
Para ello se puede usar la paginación de JPA, lo que nos da una serie de elementos "por bloques". 

## 3. API REST
**Diferencia entre error 400 y error 500. Un ejemplo de cada uno en tu proyecto.**

Un error 400 es un error por el lado del cliente, donde no se encuentra un id dicho o el formato es incorrecto.
Por ejemplo si quieres buscar un espectador por ID y este no existe saltará un error "404 not Found" indicando que no existe.

Un error 500 es un error por el lado del servidor, un fallo de conexión o un error en el codigo no contemplado.
Intentas conseguir todas las entradas para un evento y te devuelve un error 500, resultando ser que no habias iniciado la app, al no poderse conectar salta el error.

## 4. Escalabilidad
**Si tu app pasa de 100 a 10,000 usuarios, que cambiarias en Docker?**

Si tu aplicacion pasa tan rapido de un numero de usuarios a otro lo normal es que las solicitudes vayan lento y acaben colapsando los procesos y las peticiones.
Para ello lo mejor seria escalar y usar muchos dockers que se pueden almacenar en kubernete para asi poder gestionar de una mejor manera el flujo de usuarios
