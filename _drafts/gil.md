El Global Interpreter Lock (GIL) del MRI (CRuby) es una de las mayores diferencias de diseño que explica por qué implementaciones como JRuby pueden manejar la concurrencia de manera superior.

🔒 El Global Interpreter Lock (GIL) en MRI
El GIL es un mecanismo que permite que solo un hilo de ejecución (thread) corra código Ruby a la vez dentro del proceso del intérprete.

¿Cómo Afecta la Concurrencia?
Bloqueo de Hilos: Aunque Ruby permite crear múltiples hilos, el GIL asegura que, en cualquier momento dado, solo uno de esos hilos pueda estar ejecutando código Ruby.

CPU Bound (Limitado por CPU): Si tienes una tarea que requiere mucha capacidad de procesamiento (cálculos matemáticos, etc.), el GIL impide que se aprovechen múltiples núcleos de CPU de forma paralela. Si tienes 8 núcleos, tu programa Ruby solo usará uno a la vez. El rendimiento no escalará al añadir más hilos.

I/O Bound (Limitado por Entrada/Salida): El GIL se libera (suelta el bloqueo) automáticamente cuando un hilo está esperando operaciones lentas, como leer un archivo o esperar una respuesta de red (I/O). En estos casos, otro hilo puede tomar el control. Por eso, para las aplicaciones web (que son en su mayoría I/O bound), el MRI funciona bien con hilos.

⚡ La Ventaja de Concurrencia de JRuby
JRuby elimina la limitación del GIL porque corre sobre la JVM (Java Virtual Machine).

Característica	MRI (CRuby)	JRuby (JVM)
Paralelismo	No (usa el GIL, solo un núcleo a la vez).	Sí (aprovecha los núcleos del sistema).
Hilos (Threads)	Hilos internos (limitados por el GIL).	Hilos nativos de la JVM (manejo robusto y escalable).
Uso de CPU	Eficiente para I/O; limitado para CPU-bound.	Escalable para CPU-bound y I/O-bound.
Memoria	Tiende a usar más memoria por proceso.	La JVM ofrece recolección de basura (Garbage Collection) más avanzada.

Beneficio Principal
La principal ventaja de JRuby es el paralelismo real. Un programa Ruby que corre en JRuby puede ejecutar código en múltiples núcleos de CPU simultáneamente. Esto lo hace ideal para aplicaciones que:

Tienen tareas intensivas de procesamiento (CPU-bound).

Necesitan manejar cientos o miles de conexiones concurrentes de manera eficiente, aprovechando la arquitectura de la JVM.

En resumen, la limitación del MRI (GIL) es el precio que se paga por tener un intérprete simple y una implementación más sencilla de las C-Extensions, mientras que JRuby sacrifica parte de esa compatibilidad con C-Extensions para ganar la robusta concurrencia y paralelismo de la JVM.

¿Te gustaría ver un ejemplo de un caso de uso específico donde la concurrencia de JRuby sería una ventaja clara sobre el MRI?

Un ejemplo clásico donde JRuby demuestra una ventaja clara y significativa sobre el MRI es en el procesamiento intensivo y concurrente de datos o en el manejo de una gran cantidad de solicitudes web que requieren cálculos pesados.🖥️ Caso de Uso: Procesamiento de Archivos Grandes y ConcurrentesImagina que tienes una aplicación web que debe hacer lo siguiente:Recibir peticiones de varios usuarios al mismo tiempo.Por cada petición, debe analizar un archivo grande (por ejemplo, un CSV de 1 GB), realizar cálculos estadísticos complejos sobre esos datos (una tarea CPU-Bound), y devolver el resultado.Scenario 1: Corriendo en MRI (con GIL)ImplementaciónMRI (CRuby)Recurso UtilizadoUn solo núcleo de CPU a la vez.ComportamientoCuando el Usuario A comienza a procesar su archivo (toma 10 segundos), el GIL se activa. Si el Usuario B envía su petición, su hilo debe esperar a que el hilo del Usuario A complete el cálculo.ResultadoAunque el servidor tenga 8 núcleos, el tiempo de procesamiento total es la suma de los tiempos (Usuario A: 10s + Usuario B: 10s = 20 segundos para el último usuario). La aplicación se vuelve lenta bajo carga pesada.Scenario 2: Corriendo en JRuby (sin GIL)ImplementaciónJRuby (JVM)Recurso UtilizadoMúltiples núcleos de CPU simultáneamente.ComportamientoCuando el Usuario A comienza a procesar, JRuby le asigna un hilo que corre en el Núcleo 1. Cuando el Usuario B llega, JRuby le asigna un hilo que corre en el Núcleo 2. Ambos procesan en paralelo.ResultadoEl tiempo de procesamiento total es casi el mismo que si fuera un solo usuario (Usuario A: 10s, Usuario B: 10s, y ambos terminan aproximadamente a los 10 segundos). La aplicación es mucho más escalable y eficiente para tareas CPU-Bound.En resumen, si tu aplicación en Jekyll o cualquier otro proyecto de Ruby necesita realizar cálculos complejos o manejar muchas tareas CPU-Bound a la vez, JRuby es una alternativa más eficiente para aprovechar el hardware moderno. Si, por el contrario, tu aplicación es principalmente I/O-Bound (como la mayoría de los blogs y APIs web estándar), el MRI sigue siendo la opción preferida debido a su compatibilidad con las C-Extensions.
