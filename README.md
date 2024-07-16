# ms_auth
Describe las posibilidades de autenticación a traves de Ms Graph

Se van a desarrollar las modalidades:
- authorization_code
- device_flow

### Authorization Code Flow
El flujo de autorización de código (authorization_code) es un modo de autenticación utilizado principalmente por aplicaciones web y móviles que requieren acceder a recursos en nombre del usuario. Funciona de la siguiente manera:

1. **Solicitud de Autorización**: La aplicación redirige al usuario a la página de inicio de sesión de Azure AD, donde el usuario inicia sesión y otorga permisos.
2. **Código de Autorización**: Azure AD devuelve un código de autorización a la aplicación.
3. **Intercambio de Código**: La aplicación envía este código de autorización al servidor de autenticación de Azure AD junto con su identificador de cliente y secreto.
4. **Token de Acceso**: Azure AD verifica el código y devuelve un token de acceso (y opcionalmente un token de actualización) que la aplicación puede usar para acceder a los recursos protegidos en nombre del usuario.

Este flujo es seguro ya que el código de autorización es temporal y se intercambia directamente entre la aplicación y Azure AD.

### Device Code Flow
El flujo de código de dispositivo (device_flow) es un modo de autenticación ideal para dispositivos sin navegador o con capacidades de entrada limitadas, como televisores inteligentes, consolas de juegos y otros dispositivos IoT. Funciona de la siguiente manera:

1. **Solicitud de Código de Dispositivo**: La aplicación solicita un código de dispositivo a Azure AD.
2. **Mostrar Código de Usuario**: Azure AD devuelve un código de usuario y una URL. La aplicación muestra estos al usuario, quien debe ir a la URL en otro dispositivo con un navegador e ingresar el código.
3. **Autenticación del Usuario**: El usuario inicia sesión en la URL proporcionada y da su consentimiento para que la aplicación acceda a los recursos.
4. **Intercambio de Código**: La aplicación verifica periódicamente con Azure AD si el usuario ha completado la autenticación.
5. **Token de Acceso**: Una vez que el usuario ha dado su consentimiento, Azure AD devuelve un token de acceso que la aplicación puede usar para acceder a los recursos protegidos.

Este flujo es útil para dispositivos donde la entrada del usuario es limitada o no hay navegador disponible para redirigir al usuario directamente.

### Microsoft Graph
Microsoft Graph es una API unificada que permite a los desarrolladores acceder a los datos y servicios de Microsoft 365, incluyendo servicios como Outlook, OneDrive, Microsoft Teams, y más. Proporciona un punto de entrada único para interactuar con datos de productividad, seguridad, administración de dispositivos, e inteligencia de la organización. Microsoft Graph facilita la integración y la automatización de tareas, permitiendo a los desarrolladores crear aplicaciones que interactúan con múltiples servicios de Microsoft 365, obteniendo información valiosa para mejorar la colaboración, la productividad y la gestión dentro de las organizaciones.

### Graph Explorer
URL: https://developer.microsoft.com/en-us/graph/graph-explorer
Graph Explorer es una herramienta interactiva en línea proporcionada por Microsoft que permite a los desarrolladores probar y explorar las APIs de Microsoft Graph. Facilita la creación y el envío de solicitudes HTTP a Microsoft Graph, visualizando las respuestas de manera clara. Graph Explorer es ideal para aprender, experimentar y prototipar con Microsoft Graph sin necesidad de escribir código, ofreciendo un entorno seguro para entender cómo funcionan las API y cómo pueden integrarse en aplicaciones.


