# Temario Introducción a las APIs

Las APIs (Application Programming Interfaces) son conjuntos de reglas y protocolos que permiten a diferentes software comunicarse entre sí. En términos simples, una API especifica cómo un software debe interactuar con otro software.

## Definición de API

Una API define los métodos y datos que una aplicación expone para que otras aplicaciones puedan utilizarlos. Esto permite que diferentes sistemas puedan comunicarse de manera efectiva sin necesidad de conocer los detalles internos de cómo están implementados.

- Tipos de APIs (REST, SOAP, GraphQL, etc.)

Existen varios tipos de APIs, entre los más comunes se encuentran:

1. REST (Representational State Transfer): Es un estilo arquitectónico para diseñar servicios web que utiliza los métodos estándar de HTTP (GET, POST, PUT, DELETE) para realizar operaciones sobre recursos. Es ampliamente utilizado en el desarrollo web debido a su simplicidad y flexibilidad.

2. SOAP (Simple Object Access Protocol): Es un protocolo basado en XML que define cómo dos objetos en diferentes procesos pueden comunicarse de manera que sea independiente del lenguaje de programación y de la plataforma. Aunque es más complejo que REST, se utiliza en entornos donde se requiere una alta seguridad y transacciones complejas.

3. GraphQL: Es un lenguaje de consulta desarrollado por Facebook que permite a los clientes solicitar solo los datos que necesitan y nada más. A diferencia de REST, donde cada endpoint devuelve una estructura fija de datos, en GraphQL el cliente especifica la estructura de los datos que desea recibir.

- Importancia de las APIs en el desarrollo de software

  Las APIs son fundamentales en el desarrollo de software por varias razones:
  
  - Reutilización de código: Permite a los desarrolladores reutilizar funcionalidades de otros sistemas sin tener que desarrollarlas desde cero.
  
  - Interoperabilidad: Facilita la comunicación entre diferentes sistemas, incluso si están desarrollados en diferentes lenguajes de programación o se ejecutan en diferentes plataformas.
  
  - Facilidad de mantenimiento: Al exponer solo una interfaz externa, los cambios internos en la implementación de un sistema no afectan a los sistemas que lo utilizan a través de la API.
  
  - Escalabilidad: Permite escalar sistemas de manera más efectiva al dividir la funcionalidad en servicios independientes que se comunican a través de APIs.

## Conceptos básicos de API REST

- Principios de REST

REST (Representational State Transfer) es un estilo arquitectónico para diseñar servicios web que se basa en los siguientes principios:

Cliente-servidor: Existe una separación entre la interfaz de usuario (cliente) y el servidor que almacena los datos y la lógica de la aplicación. Esto permite que ambos evolucionen de forma independiente.

Sin estado (stateless): Cada petición HTTP contiene toda la información necesaria para realizarla, lo que significa que el servidor no necesita mantener un estado de la comunicación entre peticiones. Cada petición se procesa de forma independiente.

Cacheable: Las respuestas a las peticiones deben ser marcadas como cacheables o no cacheables para mejorar la eficiencia de la red.

Interfaz uniforme: Las operaciones se realizan sobre recursos, que son identificados por URIs. Para interactuar con estos recursos, se utilizan métodos HTTP estándar (GET, POST, PUT, DELETE) y se emplean representaciones de los recursos en formatos como JSON o XML.

Sistema de capas (Layered system): Permite que la arquitectura esté compuesta por capas, lo que facilita la escalabilidad y la seguridad del sistema.

- Métodos HTTP (GET, POST, PUT, DELETE, etc.)

Los métodos HTTP más comunes utilizados en APIs REST son:

GET: Se utiliza para recuperar información de un recurso.

POST: Se utiliza para crear un nuevo recurso.

PUT: Se utiliza para actualizar un recurso existente.

DELETE: Se utiliza para eliminar un recurso.

Además de estos, existen otros métodos como PATCH (para realizar modificaciones parciales a un recurso), HEAD (similar a GET pero solo devuelve los encabezados de la respuesta) y OPTIONS (utilizado para obtener información sobre las opciones de comunicación disponibles para el recurso).

- Recursos y URIs

En una API REST, los recursos son las entidades que se manipulan a través de la interfaz. Cada recurso tiene una identificación única que se representa mediante una URI (Uniform Resource Identifier).

Por ejemplo, si tenemos un recurso "producto", su URI podría ser "/productos". Para acceder a un producto específico, se utilizaría una URI como "/productos/123", donde "123" es el identificador único del producto.

Las URIs en una API REST deben ser significativas y representar de manera clara la estructura de los recursos y las relaciones entre ellos.

## Creación de una API REST

- Diseño de endpoints
  
El diseño de endpoints en una API REST es una parte fundamental, ya que determina cómo los clientes interactuarán con los recursos de la API. Algunos principios importantes a considerar en el diseño de endpoints son:

Utilizar nombres de recursos significativos y descriptivos.

Utilizar verbos HTTP apropiados para cada operación (GET, POST, PUT, DELETE).

Evitar la inclusión de acciones en los nombres de los endpoints (por ejemplo, /actualizar-usuario en lugar de /usuarios/actualizar).

Utilizar rutas anidadas de manera lógica para representar relaciones entre recursos (por ejemplo, /usuarios/{id}/posts para obtener los posts de un usuario específico).

- Implementación de endpoints en un servidor web (Node.js, Flask, Django, etc.)

Implementación de endpoints en un servidor web

La implementación de endpoints en un servidor web puede variar dependiendo del lenguaje y el framework que estés utilizando. Aquí hay un ejemplo básico de cómo podrías implementar un endpoint en Node.js usando Express:

```javascript
  import express from 'express';
  const app = express();
  
  // Endpoint para obtener todos los usuarios
  app.get('/usuarios', (req, res) => {
    // Lógica para obtener todos los usuarios
    res.json({ usuarios: [] });
  });
  
  // Endpoint para crear un nuevo usuario
  app.post('/usuarios', (req, res) => {
    // Lógica para crear un nuevo usuario
    res.status(201).json({ mensaje: 'Usuario creado exitosamente' });
  });
  
  // Iniciar el servidor en el puerto 3000
  app.listen(3000, () => {
    console.log('Servidor iniciado en el puerto 3000');
  });
```

- Uso de herramientas como Postman o ThunderClient para probar la API

Postman es una herramienta muy útil para probar APIs, ya que te permite enviar solicitudes HTTP a tus endpoints y ver las respuestas. Puedes usar Postman para probar diferentes métodos HTTP, enviar datos en el cuerpo de la solicitud, establecer encabezados personalizados y mucho más.

De igual manera ThunderClient que se puede integrar en Visual Studio Code

- Seguridad en APIs

La seguridad en APIs es un aspecto crítico a tener en cuenta. Algunas prácticas comunes para asegurar tu API incluyen:

Utilizar HTTPS en lugar de HTTP para proteger la comunicación.

Autenticar y autorizar las solicitudes de los clientes.

Validar y sanitizar los datos de entrada para prevenir ataques como inyecciones SQL y XSS.

Limitar el acceso a recursos sensibles utilizando tokens de acceso o certificados.

Implementar buenas prácticas de seguridad ayudará a proteger tu API y los datos de tus usuarios.

## Autenticación y autorización

La autenticación y autorización son aspectos clave de la seguridad en las APIs. La autenticación verifica la identidad del usuario, mientras que la autorización determina si el usuario tiene permiso para acceder a un recurso específico. Algunas prácticas comunes incluyen:

Utilizar protocolos estándar como OAuth para la autenticación.
Implementar mecanismos de autorización basados en roles para controlar el acceso a recursos.

- Uso de tokens (JWT)

JSON Web Tokens (JWT) son una forma segura y eficiente de transmitir información entre partes como un objeto JSON. En el contexto de las APIs, los JWT se utilizan comúnmente para autenticar a los usuarios y compartir información de forma segura entre el cliente y el servidor.

- Protección contra ataques comunes (SQL injection, XSS, etc.)

Es importante proteger tu API contra ataques comunes como inyecciones SQL y XSS. Algunas medidas preventivas incluyen:

Utilizar consultas parametrizadas para prevenir inyecciones SQL.

Validar y sanitizar los datos de entrada para prevenir XSS.

Utilizar HTTPS para proteger la comunicación entre el cliente y el servidor.

- Documentación de APIs
  
Descripción de los endpoints disponibles y sus parámetros.

Ejemplos de solicitudes y respuestas.

Información sobre autenticación y autorización.

Ejemplos de código para diferentes lenguajes de programación.

La documentación de APIs es crucial para que los desarrolladores comprendan cómo utilizar tu API de manera efectiva. Algunas herramientas populares para documentar APIs incluyen Swagger, API Blueprint y Postman. La documentación debe incluir:

