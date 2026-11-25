# CLEANSEA — Videojuego de limpieza de cuerpos de agua

# Especificación de Requerimientos de Software (SRS)

**Versión:** 1.0\
**Fecha:** 24 de noviembre de 2026\
**Equipo:**

- Osmar Itiel Murguía Hernández
- Karol Roberto Navarro Urzúa

**Materia:** Introducción a la Ingeniería de Software\

---

# Tabla de contenido

1. Introducción
2. Descripción general
3. Reglas del juego

---

# 1. Introducción

## 1.1 Propósito

Este documento establece los requerimientos funcionales y no funcionales del videojuego **CLEANSEA**. Describe sus características, mecánicas, progresión, interfaces y condiciones técnicas que deberá cumplir durante su desarrollo.

Está dirigido al equipo de desarrollo y al personal académico encargado de evaluar el proyecto.

## 1.2 Alcance

**CLEANSEA** es un videojuego educativo y recreativo en el que el jugador controla a un personaje que explora diferentes cuerpos de agua con el objetivo de recolectar basura y reducir la contaminación de cada escenario.

El jugador podrá vender los residuos recolectados, obtener dinero y utilizarlo para comprar mejoras que faciliten la exploración y limpieza de los escenarios.

El videojuego contará inicialmente con cinco escenarios, cada uno con diferentes características y distribución de residuos.

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

## 1.3 Definiciones, acrónimos y abreviaturas

| Término                | Definición                                                                     |
| ---------------------- | ------------------------------------------------------------------------------ |
| Cuerpo de agua         | Río, lago, laguna o mar que el jugador deberá limpiar.                         |
| Escenario              | Nivel del videojuego que representa un cuerpo de agua específico.              |
| Basura                 | Objeto recolectable que representa un residuo contaminante.                    |
| Basura orgánica        | Residuos de origen orgánico.                                                   |
| Basura inorgánica      | Residuos de origen inorgánico.                                                 |
| Porcentaje de limpieza | Proporción de basura retirada respecto al total considerado para el escenario. |
| Umbral de avance       | Porcentaje mínimo de limpieza necesario para desbloquear otro escenario.       |
| Inventario             | Espacio disponible para almacenar los residuos recolectados.                   |
| Mejora                 | Elemento comprable que aumenta las capacidades del personaje.                  |
| Oxígeno                | Recurso que determina el tiempo de permanencia bajo el agua.                   |
| Moneda                 | Dinero virtual obtenido mediante la venta de basura y recompensas.             |
| HUD                    | Interfaz que muestra información durante la partida.                           |
| Pygame                 | Biblioteca de Python utilizada para desarrollar videojuegos.                   |
| SRS                    | Software Requirements Specification.                                           |
| RF                     | Requerimiento funcional.                                                       |
| RNF                    | Requerimiento no funcional.                                                    |

## 1.4 Referencias

- IEEE Std 830-1998.
- ISO/IEC/IEEE 29148, ingeniería de requerimientos.
- Lineamientos académicos del proyecto.
- Documentación oficial de Python.
- Documentación de Pygame.

---

# 2. Descripción general

## 2.1 Perspectiva del producto

Río Limpio será un videojuego independiente desarrollado utilizando Python y la biblioteca Pygame.

No dependerá de otros sistemas para su funcionamiento y estará diseñado para ejecutarse sin conexión a internet.

El progreso se conservará mediante un sistema de guardado automático.

### Plataformas objetivo

| Plataforma | Orientación |
| ---------- | ----------- |
| PC         | Horizontal  |
| Android    | Vertical    |

El videojuego tendrá una interfaz adaptada a cada plataforma.

## 2.2 Funciones principales

El funcionamiento del videojuego estará basado en el siguiente ciclo:

**Explorar → Recolectar basura → Almacenar → Vender → Comprar mejoras → Limpiar escenarios → Avanzar.**

Las funciones principales serán:

1. Controlar el movimiento del personaje.
2. Explorar los diferentes cuerpos de agua.
3. Recoger basura mediante interacción.
4. Almacenar residuos dependiendo de la capacidad del bolso.
5. Vender los objetos recolectados en tiendas.
6. Obtener dinero adicional al completar escenarios.
7. Comprar mejoras para aumentar las capacidades del personaje.
8. Consultar el porcentaje de limpieza.
9. Desbloquear nuevos escenarios al alcanzar el 80% de limpieza.
10. Regresar a escenarios anteriores para continuar recolectando basura.
11. Guardar automáticamente el progreso.

## 2.3 Características de los usuarios

- **Perfil:** jugadores casuales.
- **Edad aproximada:** de 8 a 35 años (pendiente de confirmar).
- **Experiencia:** no se requiere experiencia previa en videojuegos.
- **Idioma:** español.
- **Duración estimada de las sesiones:** entre 10 y 20 minutos.
- **Plataformas:** PC y Android.

## 2.4 Restricciones

- Lenguaje de programación: Python.
- Biblioteca de desarrollo: Pygame.
- Herramientas de desarrollo: Visual Studio Code y GitHub.
- Estilo gráfico: pixel art de 64 bits.
- Orientación horizontal en PC.
- Orientación vertical en Android.
- El videojuego deberá funcionar sin conexión a internet.
- Se buscará que pueda ejecutarse en dispositivos de bajos recursos.
- El objetivo de rendimiento será de 60 FPS.
- Los recursos gráficos y de audio deberán ser propios o contar con licencias que permitan su utilización.

## 2.5 Suposiciones y dependencias

- El jugador contará con un dispositivo compatible con el videojuego.
- El juego no dependerá de servicios externos para funcionar.
- Se utilizará Python y Pygame como base del desarrollo.
- Se contempla la adaptación de controles e interfaces para PC y Android.
- Se buscará utilizar música libre de derechos de autor o con licencias adecuadas.
- La compatibilidad con Android dependerá de las herramientas adicionales de empaquetado y adaptación que se seleccionen.

## 2.6 Progresión del videojuego

El videojuego contará inicialmente con cinco escenarios.

Cada escenario tendrá una cantidad y distribución de basura propias.

El jugador podrá desbloquear el siguiente escenario cuando alcance un porcentaje de limpieza del 80%.

El jugador también podrá regresar a escenarios anteriores para continuar limpiándolos.

Al alcanzar el 100% de limpieza, recibirá una recompensa económica adicional. Ocasionalmente, podrá generarse basura nuevamente.

Cuando esto ocurra, el porcentaje de limpieza no podrá disminuir por debajo del 80%.

---


# 3. Reglas del juego

## 3.1 Reglas de recolección

1. El jugador deberá acercarse a un objeto de basura.
2. Deberá presionar el botón de interacción para recogerlo.
3. El objeto se almacenará en el inventario si existe espacio suficiente.
4. Cada objeto ocupará una cantidad determinada de espacio.
5. Si el inventario está lleno, no será posible recoger más basura hasta liberar espacio.

## 3.2 Reglas de venta

1. El jugador deberá acudir a una tienda de recolección.
2. Podrá vender la basura almacenada.
3. El dinero recibido dependerá del tipo, tamaño y rareza de los objetos.
4. Después de una venta, el inventario correspondiente quedará liberado.

## 3.3 Reglas de mejoras

1. Las mejoras se adquirirán en diferentes tiendas.
2. Se utilizará el dinero disponible para realizar las compras.
3. Si el jugador no cuenta con dinero suficiente, la compra no podrá realizarse.
4. Cada mejora podrá alcanzar hasta tres niveles inicialmente.
5. Las mejoras modificarán las capacidades correspondientes del personaje.

## 3.4 Reglas de oxígeno

1. El oxígeno será un recurso limitado durante la exploración bajo el agua.
2. Al agotarse, el personaje se desmayará.
3. El jugador perderá la basura que tenga almacenada.
4. Se descontará una cantidad de dinero por el servicio de rescate.

## 3.5 Reglas de progresión

1. El videojuego contará inicialmente con cinco escenarios.
2. Cada escenario tendrá sus propias características y distribución de basura.
3. Al alcanzar el 80% de limpieza, se desbloqueará el siguiente escenario.
4. El jugador podrá regresar a escenarios anteriores.
5. Al alcanzar el 100% de limpieza, recibirá una recompensa económica adicional.
6. En ocasiones podrá aparecer basura nuevamente.
7. La regeneración de basura no reducirá el porcentaje de limpieza por debajo del 80%.

## 3.6 Reglas de guardado

El videojuego realizará guardados automáticos después de las siguientes acciones:

- Vender basura.
- Comprar mejoras.
- Desbloquear un escenario.
- Completar un escenario.
- Recibir recompensas.

La información que deberá conservarse será:

- Dinero disponible.
- Mejoras compradas y sus niveles.
- Escenarios desbloqueados.
- Porcentaje de limpieza de cada escenario.
- Inventario actual.

El guardado no se realizará simplemente por sumergirse en el agua.

---
https://github.com/osmar-itiel-murguia/CLEANSEA/blob/main/pantallas.md

**Fin del documento SRS — CLEAN SEA**

*Versión 1.0 — 24 de noviembre de 2026*
