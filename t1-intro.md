# Introducción a los Sistemas Distribuidos

**Autores:** David Villa, Felix Villanueva, Soledad Escolar

**Correo Electrónico:**  
David.Villa@uclm.es  
Felix.Villanueva@uclm.es  
Soledad.Escolar@uclm.es

## Contenidos

1. Conceptos y ejemplos de sistemas distribuidos
2. Características, ventajas y desventajas de los sistemas distribuidos
3. Computación distribuida vs. Computación paralela
4. Nomenclatura: protocolos, clientes, servicios y servidores
5. Middleware
6. Paradigmas de computación distribuida

---

## Conceptos y ejemplos de sistemas distribuidos

### Definición de Sistema Distribuido

Un sistema distribuido es uno en el que componentes ubicados en computadoras en red se comunican y coordinan sus acciones únicamente mediante el paso de mensajes. Según G. Coulouris, J. Dollimore y T. Kindberg (2001), los sistemas distribuidos presentan tres características principales:
- **Ejecución concurrente de procesos:** Varios procesos se ejecutan simultáneamente en diferentes nodos.
- **Falta de un reloj global:** No hay un reloj sincronizado globalmente, lo cual complica la coordinación.
- **Fallos independientes:** Cada componente puede fallar independientemente de los demás.

Los sistemas distribuidos son fundamentales en muchas aplicaciones modernas, como redes sociales, aplicaciones en la nube, computación en grid, computación móvil e IoT.

### Fallos Independientes

En un sistema distribuido, el cliente y el servidor son procesos independientes que pueden ejecutarse en diferentes nodos. Cada uno puede tener sus propias circunstancias y restricciones. Un ejemplo de esto es gRPC, donde tanto el cliente como el servidor determinan de manera local e independiente el éxito de una llamada RPC. Esto puede resultar en una situación donde el servidor considera que una llamada ha sido exitosa mientras que el cliente la considera fallida debido a diferencias en sus criterios de éxito.

### Componentes de un Sistema Distribuido

Un sistema distribuido se compone de:
- **Recursos computacionales (hardware y software):** Físicamente distribuidos.
- **Red de comunicación:** Los recursos están conectados a través de una red de computadoras.
- **Mensajería:** Los componentes se comunican y coordinan sus acciones mediante el paso de mensajes.
- **Cooperación:** Los componentes cooperan para realizar una tarea conjunta, proporcionando un servicio integrado.

### Las Ocho Falacias de los Sistemas Distribuidos

Peter Deutsch identificó ocho falacias comunes en el diseño y uso de sistemas distribuidos:
1. La red es confiable.
2. La latencia es cero.
3. El ancho de banda es infinito.
4. La red es segura.
5. La topología no cambia.
6. Existe un único administrador.
7. El costo de transporte es cero.
8. La red es homogénea.

### Origen: Compartición de Recursos

La creación de sistemas distribuidos surgió de la necesidad de compartir recursos a través de redes. El modelo de llamada a procedimiento (RPC) elevó la tarea de crear protocolos de aplicación al nivel de definir procedimientos y sus secuencias de llamada, extendiendo el entorno de programación local para incluir módulos en otras máquinas, facilitando así el trabajo del programador de aplicaciones.

### Ejemplos de Sistemas Distribuidos

#### Internet y Búsqueda en la Web

La búsqueda en Internet es un claro ejemplo de un sistema distribuido, como lo muestra el sistema de Google que maneja billones de páginas web y URLs.

#### Computación en la Nube

La computación en la nube proporciona recursos de software y hardware bajo demanda a través de Internet. Estos recursos son elásticos, es decir, escalan según la carga de trabajo y los clientes pagan solo por lo que utilizan.

**Tipos de Servicios en la Nube:**
1. **IaaS (Infrastructure as a Service):** Proporciona recursos de TI (nodos, almacenamiento, redes) gestionados por el cliente. Ejemplos: AWS, Azure, Google Cloud.
2. **PaaS (Platform as a Service):** El cliente se enfoca solo en la construcción de aplicaciones mientras el proveedor gestiona los recursos de TI. Ejemplos: Heroku, Google App Engine.
3. **SaaS (Software as a Service):** Tanto la infraestructura como la aplicación son gestionadas por el proveedor. Ejemplos: Microsoft 365, Slack, Dropbox.

---

## Características, ventajas y desventajas

### Ventajas

- **Compartición de recursos:** Hardware, software y datos.
- **Buena relación costo/rendimiento:** Aumenta la eficiencia económica.
- **Capacidad de crecimiento (escalabilidad):** Puede adaptarse a un aumento en la demanda.
- **Mayor disponibilidad:** Tolerancia a fallos.
- **Concurrencia:** Servicio simultáneo a múltiples usuarios.
- **Velocidad:** Mayor capacidad de procesamiento.

### Desventajas

- **Interconexión de recursos:** Implica costos, problemas de fiabilidad y posibles saturaciones.
- **Seguridad en las comunicaciones:** Necesidad de robustez frente a ataques.
- **Complejidad del software:** Mayor dificultad en el desarrollo y mantenimiento.

---

## Métricas de Rendimiento en Sistemas Distribuidos

### Métricas de red/infrastructura

- **Retardo y latencia:** Tiempo que tarda un paquete en viajar desde el origen hasta el destino.
- **Ancho de banda:** Capacidad de la red para transmitir datos.
- **Rendimiento:** Medición del desempeño general del sistema.
- **Tiempo de respuesta:** Tiempo que tarda el sistema en responder a una solicitud.

### Métricas específicas de aplicación

- **Transacciones por segundo en bases de datos.**
- **Frames per second (FPS) en juegos.**
- **Tiempo de respuesta en aplicaciones web.**

Estas métricas se miden utilizando herramientas como ping, iperf3, y wireshark, y mediante pruebas y benchmarks estándar.

---

## Computación Distribuida vs. Computación Paralela

### Sistemas Distribuidos

- **Objetivo:** Compartición de recursos.
- **Redes de computadoras heterogéneas:** Conjunto de computadoras conectadas por una inter-red heterogénea.

### Sistemas Paralelos

- **Objetivo:** Alto rendimiento y alta productividad.
- **Arquitecturas dedicadas:** Multiprocesadores y multicomputadoras.

---

## Nomenclatura en Sistemas Distribuidos

### Servicio

Un componente que maneja una colección de recursos relacionados y proporciona funcionalidad a usuarios y aplicaciones a través de una API bien definida. Ejemplo: un servidor de archivos que proporciona operaciones de lectura, escritura y eliminación.

### Servidor

Un programa en ejecución en una computadora en red que acepta solicitudes de otro programa en otra computadora y responde apropiadamente. Los procesos solicitantes se conocen como clientes y este enfoque se denomina computación cliente-servidor. Un servidor puede implementar uno o varios servicios utilizando una API para cada uno.

### Protocolo

Un conjunto de reglas que permite que dos entidades se conecten y transmitan datos entre sí. Un protocolo especifica sintaxis, semántica y sincronización/timing para la comunicación.

---

## Retos en los Sistemas Distribuidos

### Heterogeneidad

Variedad y diferencias en los componentes del sistema, como hardware, software, redes y usos.

### Apertura

Capacidad del sistema para ser extendido y reimplementado, proporcionando interfaces abiertas y bien documentadas.

### Seguridad (CIA)

Confidencialidad, Integridad y Disponibilidad. La seguridad debe ser asegurada en diferentes niveles y utilizando diversas herramientas como SSL, infraestructura de clave pública y VPNs.

### Escalabilidad

La capacidad de un sistema para mantener su efectividad al crecer en número de recursos o usuarios.

### Manejo de Fallos

Capacidad para gestionar fallos en cualquier proceso, computadora o red. Esto incluye detección, enmascaramiento, recuperación y redundancia de fallos.

### Concurrencia

Capacidad de atender múltiples solicitudes de recursos simultáneamente. Los procesos concurrentes deben comunicarse y sincronizarse eficientemente.

### Transparencia

Ocultar detalles del sistema a los usuarios y programadores, proporcionando una visión unificada del sistema.

### Calidad de Servicio

Asegurar fiabilidad, seguridad y rendimiento adecuado del servicio.

---

## Transparencia en los Sistemas Distribuidos

La transparencia se refiere a ocultar los detalles del sistema a los usuarios, permitiéndoles acceder a los recursos de manera uniforme, sin importar su ubicación, concurrencia, replicación, fallos, movilidad, rendimiento y escalabilidad.

---

## Middleware

El middleware es una infraestructura de software que facilita el desarrollo de aplicaciones en entornos distribuidos. Proporciona un modelo de programación común y servicios estructurales como nombramiento, seguridad, persistencia y transacciones. Aísla al desarrollador de las características no funcionales de la aplicación, permitiéndole centrarse en los requisitos funcionales.

---

## Paradigmas de Computación Distribuida

### Sockets

Mecanismo de comunicación entre procesos en diferentes computadoras. Introdujo TCP/IP en UNIX y proporciona una interfaz universal a nivel bajo, aunque es complejo y propenso a errores.

### Cliente/Servidor

Asigna roles diferentes a los procesos que se comunican, donde el cliente solicita un servicio y el servidor lo ofrece, gestionando recursos y esperando solicitudes.

### RPC (Remote Procedure Call)

Facilita la programación de software distribuido al permitir invocar procedimientos remotos como si fueran locales.

### RMI (Remote Method Invocation)

Contraparte de RPC para la programación orientada a objetos. Permite ejecutar métodos de objetos remotos como si fueran locales.

### Comunicación Indirecta

Paradigma orientado a eventos donde los eventos distribuidos por los editores se gestionan a través de un intermediario (broker) que maneja la distribución de eventos y suscripciones.

---

## Modelos Fundamentales en Sistemas Distribuidos

### Modelo de Interacción

Define cómo los procesos se comunican mediante el paso de mensajes para lograr un objetivo común.

### Modelo de Fallos

Clasifica los tipos de fallos que pueden afectar un sistema distribuido, proporcionando una base para diseñar sistemas tolerantes a fallos.

### Modelo de Seguridad

Define y clasifica las amenazas y ataques que pueden afectar un sistema distribuido, proporcionando una base para construir sistemas robustos.

---

## Conclusión

Los sistemas distribuidos son una parte integral de las aplicaciones y servicios modernos, proporcionando una infraestructura robusta, escalable y eficiente para gestionar recursos distribuidos y permitir la cooperación entre múltiples procesos. La comprensión de sus conceptos, ventajas, desventajas, y retos es esencial para el diseño y la implementación efectiva de sistemas distribuidos.
