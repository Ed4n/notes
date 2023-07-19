---
id: 9ysks5j03ll7nrii4h9qwm6
title: Codigo Asincrono
desc: ""
updated: 1689726088457
created: 1689725982699
---

En el contexto de la programación, "asincrónico" se refiere a un estilo de programación en el cual las tareas y operaciones ==no se ejecutan de forma secuencial, una después de la otra, sino que pueden realizarse de manera concurrente y no bloqueante.==

Cuando una tarea se ejecuta de forma sincrónica, **el programa espera a que dicha tarea se complete antes de continuar con la siguiente línea de código.** Por otro lado, en un enfoque asincrónico, una tarea **puede iniciarse y continuar ejecutándose en segundo plano mientras el programa sigue adelante con otras tareas.** Esto permite que el programa sea más eficiente y aproveche mejor los recursos disponibles.

Un escenario común donde se utilizan operaciones asincrónicas es cuando se realiza una solicitud a un servidor para obtener datos. En lugar de esperar bloqueado hasta que los datos lleguen, se puede iniciar la solicitud y continuar realizando otras tareas. Cuando los datos estén disponibles, se activará una función de callback, se resolverá una promesa o se utilizará async/await para manejar los datos recibidos.
