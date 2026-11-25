# CLEANSEA — Videojuego de limpieza de cuerpos de agua

**Materia:** Introducción a la Ingeniería de Software\
**Equipo:**

- Osmar Itiel Murguía Hernández
- Karol Roberto Navarro Urzúa

# Tabla de contenido

1. Requerimientos funcionales
2. Requerimientos no funcionales
3. Interfaces externas
4. Restricciones y aspectos pendientes


### Funciones incluidas

- Exploración y movimiento del personaje dentro de los cuerpos de agua.
- Recolección de basura mediante interacción.
- Sistema de inventario con capacidad limitada.
- Clasificación de basura por tipo, tamaño y rareza.
- Venta de basura a cambio de dinero.
- Recompensas económicas por completar escenarios.
- Compra y mejora de habilidades y equipamiento.
- Medición del porcentaje de limpieza.
- Desbloqueo de nuevos escenarios.
- Regreso a escenarios anteriores.
- Sistema de oxígeno para controlar el tiempo de exploración.
- Guardado automático del progreso.
- Menús de navegación y configuración.
- Tutorial inicial.

### Funciones excluidas

- Modo multijugador.
- Compras con dinero real.
- Rankings en línea.
- Editor de niveles.
- Funciones que requieran conexión a internet.

---

# 1. Requerimientos funcionales

Los siguientes requerimientos describen las acciones y funciones que deberá realizar el videojuego.

| ID    | Descripción                                                                                              | Prioridad | Criterio de aceptación                                                                                                        |
| ----- | -------------------------------------------------------------------------------------------------------- | --------- | ----------------------------------------------------------------------------------------------------------------------------- |
| RF-01 | El jugador podrá desplazarse por el escenario utilizando los controles correspondientes a su plataforma. | Alta      | El personaje responde correctamente a las flechas del teclado o botones de pantalla.                                          |
| RF-02 | El jugador podrá explorar libremente el cuerpo de agua dentro de los límites establecidos del mapa.      | Alta      | El personaje puede desplazarse por las zonas permitidas sin salir de los límites.                                             |
| RF-03 | El jugador podrá recolectar basura acercándose a un objeto y presionando un botón de interacción.        | Alta      | El objeto desaparece del escenario y se incorpora al inventario cuando existe espacio suficiente.                             |
| RF-04 | El sistema identificará los diferentes tipos de basura presentes en el escenario.                        | Alta      | Los residuos pueden clasificarse según su categoría y características.                                                        |
| RF-05 | El sistema asignará un valor económico a cada objeto según su tamaño, tipo y rareza.                     | Alta      | Los objetos tienen valores correspondientes a sus características.                                                            |
| RF-06 | El sistema administrará un inventario con capacidad limitada.                                            | Alta      | El jugador no puede almacenar objetos cuando no existe espacio suficiente.                                                    |
| RF-07 | El jugador podrá vender la basura recolectada en tiendas de recolección.                                 | Alta      | Al realizar una venta, se calcula el valor de los objetos y se actualiza el dinero disponible.                                |
| RF-08 | El sistema otorgará una recompensa económica adicional al completar un escenario.                        | Media     | Al alcanzar el 100% de limpieza se entrega la recompensa correspondiente.                                                     |
| RF-09 | El jugador podrá comprar mejoras utilizando el dinero obtenido.                                          | Alta      | Si cuenta con dinero suficiente, la compra se realiza y se descuenta el costo.                                                |
| RF-10 | El sistema permitirá mejorar las capacidades del personaje.                                              | Alta      | Las mejoras adquiridas modifican las características correspondientes.                                                        |
| RF-11 | Las mejoras tendrán hasta tres niveles inicialmente.                                                     | Media     | El jugador podrá adquirir mejoras hasta alcanzar el nivel máximo establecido.                                                 |
| RF-12 | El sistema administrará el oxígeno disponible del personaje.                                             | Alta      | El oxígeno disminuye durante la exploración bajo el agua.                                                                     |
| RF-13 | El sistema aplicará una penalización cuando el oxígeno llegue a cero.                                    | Alta      | El personaje se desmaya, pierde la basura almacenada y una cantidad de dinero por el servicio de rescate.                     |
| RF-14 | El sistema calculará y mostrará el porcentaje de limpieza del escenario.                                 | Alta      | El porcentaje corresponde a la cantidad de basura retirada respecto al total considerado.                                     |
| RF-15 | El sistema desbloqueará el siguiente escenario al alcanzar el 80% de limpieza.                           | Alta      | Al alcanzar el porcentaje requerido, el siguiente escenario queda disponible.                                                 |
| RF-16 | El jugador podrá regresar a escenarios anteriores que ya haya desbloqueado.                              | Media     | El jugador puede seleccionar y acceder a cualquier escenario previamente desbloqueado.                                        |
| RF-17 | El sistema permitirá que aparezca basura nuevamente en escenarios completados.                           | Media     | Puede generarse basura adicional sin reducir el porcentaje de limpieza por debajo del 80%.                                    |
| RF-18 | El sistema guardará automáticamente el progreso después de acciones importantes.                         | Alta      | El progreso se guarda después de vender, comprar mejoras, desbloquear escenarios, completar escenarios y recibir recompensas. |
| RF-19 | El sistema cargará la información guardada al iniciar una nueva sesión.                                  | Alta      | Se recuperan los datos correspondientes al último guardado válido.                                                            |
| RF-20 | El videojuego contará con un menú principal.                                                             | Alta      | El menú permite acceder a Jugar, Créditos, Salir y Configuración.                                                             |
| RF-21 | El videojuego contará con un tutorial inicial.                                                           | Media     | El tutorial explica las acciones básicas necesarias para comenzar a jugar.                                                    |
| RF-22 | El sistema mostrará información relevante durante la partida.                                            | Alta      | Se muestra el dinero disponible, el porcentaje de limpieza y los botones de interacción.                                      |
| RF-23 | El sistema contará con tiendas para adquirir diferentes mejoras.                                         | Media     | El jugador puede acceder a las tiendas y consultar las mejoras disponibles.                                                   |
| RF-24 | El sistema permitirá administrar los diferentes tipos de mejoras.                                        | Media     | Las mejoras de almacenamiento, oxígeno, velocidad, alcance y profundidad afectan sus capacidades correspondientes.            |

## 1.1 Sistema de mejoras

El videojuego contará inicialmente con cinco categorías de mejoras.

| Mejora         | Función                                                         |
| -------------- | --------------------------------------------------------------- |
| Almacenamiento | Aumenta la capacidad del bolso para guardar basura.             |
| Oxígeno        | Aumenta el tiempo disponible para permanecer bajo el agua.      |
| Velocidad      | Aumenta la velocidad de desplazamiento del personaje.           |
| Alcance        | Aumenta la distancia desde la que se pueden recolectar objetos. |
| Profundidad    | Permite explorar zonas más profundas de los cuerpos de agua.    |

Todas las mejoras tendrán hasta tres niveles inicialmente.

Los precios y los valores exactos de mejora estarán sujetos al balance del videojuego.

## 1.2 Sistema de recolección y economía

Los residuos tendrán características que determinarán su valor:

- Tipo de basura.
- Tamaño del objeto.
- Rareza.

La distribución de residuos dependerá del escenario. Algunos cuerpos de agua podrán contener una mayor cantidad de determinados tipos de basura.

La basura recolectada ocupará espacio en el inventario dependiendo de sus características.

El jugador podrá vender los residuos en tiendas especializadas y obtener dinero para comprar mejoras.

También recibirá recompensas económicas al completar escenarios.

## 1.3 Sistema de oxígeno

El personaje tendrá una cantidad limitada de oxígeno para permanecer bajo el agua.

Al agotarse, se desmayará y se aplicarán las siguientes penalizaciones:

- Pérdida de toda la basura almacenada.
- Descuento de algunas monedas por el servicio de rescate.

La cantidad exacta de oxígeno, el costo del rescate y las condiciones de recuperación estarán pendientes de establecerse.

---

# 2. Requerimientos no funcionales

Los requerimientos no funcionales establecen las condiciones de calidad, rendimiento y funcionamiento que deberá cumplir el videojuego.

| ID     | Categoría                  | Descripción                                                                                         | Prioridad | Criterio de aceptación                                                                                                    |
| ------ | -------------------------- | --------------------------------------------------------------------------------------------------- | --------- | ------------------------------------------------------------------------------------------------------------------------- |
| RNF-01 | Rendimiento                | El videojuego deberá buscar un rendimiento estable de 60 FPS.                                       | Alta      | Mantiene aproximadamente 60 FPS en los dispositivos de referencia definidos para las pruebas.                             |
| RNF-02 | Usabilidad                 | El videojuego deberá ser fácil de entender para jugadores sin experiencia previa.                   | Alta      | Un usuario nuevo puede realizar las acciones básicas mediante el tutorial sin ayuda externa.                              |
| RNF-03 | Compatibilidad             | El videojuego deberá funcionar en PC y Android.                                                     | Alta      | Se ejecuta correctamente en las plataformas objetivo definidas.                                                           |
| RNF-04 | Confiabilidad              | El progreso deberá conservarse mediante guardado automático.                                        | Alta      | Después de cerrar y volver a abrir el juego, se recuperan los datos del último guardado válido.                           |
| RNF-05 | Mantenibilidad             | El código deberá organizarse para facilitar modificaciones y la incorporación de nuevos escenarios. | Media     | Es posible agregar escenarios mediante la configuración de sus datos sin modificar innecesariamente la lógica principal.  |
| RNF-06 | Portabilidad               | El videojuego deberá adaptar su interfaz a las características de cada plataforma.                  | Alta      | La interfaz se muestra correctamente en orientación vertical en Android y horizontal en PC.                               |
| RNF-07 | Disponibilidad             | El videojuego deberá funcionar sin conexión a internet.                                             | Alta      | Las funciones principales pueden utilizarse sin conexión.                                                                 |
| RNF-08 | Compatibilidad de hardware | El videojuego deberá estar optimizado para funcionar en computadoras de bajos recursos.             | Alta      | Las pruebas en el equipo mínimo definido permiten ejecutar las funciones principales sin problemas graves de rendimiento. |
| RNF-09 | Integridad de datos        | Los datos del jugador deberán conservarse correctamente durante los procesos de guardado y carga.   | Alta      | Los datos recuperados coinciden con los del último guardado válido.                                                       |
| RNF-10 | Recursos multimedia        | Los recursos de audio y gráficos deberán contar con permisos de utilización adecuados.              | Media     | Los recursos utilizados son propios, libres de derechos o cuentan con licencias compatibles con el proyecto.              |

---

# 3. Interfaces externas

## 3.1 Interfaz de usuario

El videojuego utilizará un estilo gráfico pixel art de 64 bits.

La interfaz deberá adaptarse a las características de cada plataforma.

### Menú principal

El menú principal contará con las siguientes opciones:

| Opción        | Función                                                                 |
| ------------- | ----------------------------------------------------------------------- |
| Jugar         | Iniciar una partida o continuar el progreso.                            |
| Créditos      | Mostrar información sobre los integrantes y colaboradores del proyecto. |
| Salir         | Cerrar el videojuego.                                                   |
| Configuración | Acceder a las opciones disponibles del juego.                           |

### Interfaz durante la partida (HUD)

Durante la partida se mostrarán los siguientes elementos:

- Dinero disponible.
- Porcentaje de limpieza.
- Botones de interacción.

La distribución visual definitiva estará pendiente de diseño.

### Orientación de pantalla

- **Android:** orientación vertical.
- **PC:** orientación horizontal.

## 3.2 Interfaz de controles

| Plataforma | Controles                                          |
| ---------- | -------------------------------------------------- |
| PC         | Flechas del teclado y botones de interacción.      |
| Android    | Botones en pantalla para movimiento e interacción. |

El personaje podrá desplazarse libremente dentro de los límites del escenario.

## 3.3 Interfaz de audio

El videojuego contará con:

- Efectos de sonido para las interacciones.
- Música ambiental durante los escenarios.
- Música permanente en la pantalla de inicio.

Se buscará utilizar música sin restricciones de derechos de autor o con licencias que permitan su uso.

---

# 4. Restricciones y aspectos pendientes

Los siguientes aspectos todavía necesitan ser definidos por el equipo antes de considerar completamente cerrada la especificación.

| ID   | Aspecto pendiente      | Descripción                                                                  |
| ---- | ---------------------- | ---------------------------------------------------------------------------- |
| P-01 | Resolución             | Definir las resoluciones objetivo para PC y Android.                         |
| P-02 | Compatibilidad Android | Definir la versión mínima y el método de empaquetado del videojuego.         |
| P-03 | Hardware mínimo        | Establecer los requisitos mínimos de memoria, procesador y gráficos.         |
| P-04 | Guardado               | Definir el formato y la ubicación de almacenamiento de los datos.            |
| P-05 | HUD                    | Diseñar la distribución definitiva de los elementos de interfaz.             |
| P-06 | Economía               | Establecer los precios de los objetos, mejoras y recompensas.                |
| P-07 | Inventario             | Definir la capacidad inicial y el espacio ocupado por cada objeto.           |
| P-08 | Oxígeno                | Definir la duración inicial y los valores de las mejoras.                    |
| P-09 | Penalizaciones         | Establecer la cantidad de monedas descontadas por rescate.                   |
| P-10 | Escenarios             | Definir los nombres, características y dificultades de los cinco escenarios. |
| P-11 | Regeneración           | Definir la frecuencia y cantidad de basura que podrá reaparecer.             |
| P-12 | Música                 | Seleccionar los recursos musicales y sus licencias.                          |

## 4.1 Consideración técnica

Pygame está orientado principalmente al desarrollo de videojuegos para PC. Por lo tanto, la ejecución en Android representa un aspecto técnico que deberá investigarse y comprobarse mediante pruebas de compatibilidad y empaquetado.

## 4.2 Consideración sobre el rendimiento

Los 60 FPS representan el objetivo de rendimiento del proyecto. Será necesario realizar pruebas en los dispositivos de referencia para comprobar que se alcanza una fluidez adecuada, especialmente en equipos de bajos recursos.

---

**Fin del documento SRS — CLEAN SEA**

*Versión 1.0 — 24 de noviembre de 2026*
