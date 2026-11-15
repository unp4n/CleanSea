# Especificación de Requerimientos de Software (SRS)

**Proyecto:** CleanSea — videojuego educativo sobre el cuidado de las zonas azules *CleanSea*
**Versión:** 1.0 · **Fecha:** 12/11/2026 · **Plantilla:** IEEE 830
**Equipo:** Karol Roberto Navarro Urzúa | Ozmar itiel Murguia

## Historial de versiones

| Versión | Fecha | Autor | Cambios |
|---|---|---|---|
| 1.0 | 12/11/2026 | Karol y Ozmar | Primera versión: secciones 1 a 3 |

---

## 1. Introducción

### 1.1 Propósito
Este documento especifica los requerimientos de *CleanSea*, un videojuego dirigido a niños que busca generar conciencia sobre el cuidado del medio ambiente, en particular de las zonas azules (cuerpos de agua). Está dirigido al equipo de desarrollo, al docente evaluador y a quienes validen el contenido educativo.

### 1.2 Alcance
En el juego, el jugador controla a un recolector de basura que limpia cuerpos de agua. Recolecta residuos, los vende para obtener monedas y compra herramientas que hacen la recolección más eficiente. Avanza por zonas de dificultad creciente: estanque, río, lago y playa *(lista editable)*.

**Incluye:** mecánica de recolección, venta, tienda de mejoras, progresión por zonas, mensajes educativos y guardado de progreso.
**No incluye:** compras con dinero real, publicidad, modo multijugador ni cuentas de usuario con datos personales.

### 1.3 Glosario

| Término | Definición |
|---|---|
| Zona azul | Cuerpo de agua (estanque, río, lago, playa) que el jugador debe limpiar. |
| Zona | Nivel del juego asociado a un cuerpo de agua, con su propia dificultad y tipos de basura. |
| Basura / residuo | Objeto contaminante que el jugador recolecta (botella, bolsa, lata, red, etc.). |
| Monedas | Moneda virtual obtenida al vender residuos. |
| Herramienta | Objeto comprable que mejora la recolección (red, caña con imán, bote, etc.). |
| Capacidad | Cantidad máxima de residuos que el jugador puede cargar antes de vender. |
| Dato educativo | Mensaje breve sobre contaminación o conservación del agua. |
| Jugador | Niño que usa el juego. |
| RF / RNF | Requerimiento funcional / no funcional. |

### 1.4 Referencias
IEEE Std 830-1998; ISO/IEC/IEEE 29148:2018. Ver `investigacion-srs.md`.

### 1.5 Visión general
La sección 2 describe el contexto del producto; la sección 3 lista los requerimientos específicos.

---

## 2. Descripción general

### 2.1 Perspectiva del producto
Videojuego 2D independiente, de un solo jugador, que funciona sin conexión a internet una vez cargado. *[Plataforma por confirmar: navegador web / móvil.]*

### 2.2 Funciones del producto
Recolectar residuos, administrar inventario, vender, comprar herramientas, desbloquear zonas, mostrar datos educativos y guardar el progreso.

### 2.3 Usuarios

| Usuario | Descripción | Características |
|---|---|---|
| Jugador (niño, 6 a 12 años *— por confirmar*) | Usuario final | Lectura básica, poca experiencia con juegos complejos, necesita controles simples e instrucciones visuales. |
| Docente / padre o tutor | Acompaña o recomienda el juego | No juega necesariamente; espera contenido apropiado y educativo. |

### 2.4 Restricciones
- Entrega dentro del semestre académico ([fecha]).
- Herramientas y recursos gráficos gratuitos o de licencia libre.
- Contenido apto para niños: sin violencia, sin lenguaje inapropiado.
- No se recopilan datos personales de los jugadores.
- Gestión de código y tareas en GitHub.

### 2.5 Suposiciones y dependencias
- Los jugadores cuentan con un dispositivo con navegador moderno *(por confirmar)*.
- El contenido educativo (datos sobre contaminación) se tomará de fuentes confiables y será validado por el equipo o el docente.
- Los recursos gráficos y de audio tendrán licencia que permita su uso.
- Si cambia la edad objetivo, se revisarán los requerimientos de usabilidad (RNF-02).

---

## 3. Requerimientos específicos

**Prioridades:** Alta (indispensable) · Media (importante) · Baja (deseable).

### 3.1 Requerimientos funcionales

#### RF-01 · Recolectar basura
- **Descripción:** El sistema deberá permitir al jugador recolectar un residuo al seleccionarlo o tocarlo dentro del alcance de su herramienta, añadiéndolo a su inventario.
- **Prioridad:** Alta
- **Criterio de aceptación:** Al interactuar con un residuo al alcance, este desaparece de la escena y el contador del inventario aumenta en 1; si el residuo está fuera de alcance, no se recolecta.

#### RF-02 · Capacidad de inventario
- **Descripción:** El sistema deberá limitar la cantidad de residuos que el jugador puede cargar según su capacidad actual, e indicar visualmente cuando el inventario esté lleno.
- **Prioridad:** Alta
- **Criterio de aceptación:** Con el inventario lleno, no se recolectan más residuos y aparece un aviso visible; tras vender, se puede volver a recolectar.

#### RF-03 · Vender basura
- **Descripción:** El sistema deberá permitir vender los residuos del inventario en un punto de venta, convirtiéndolos en monedas según el valor de cada tipo de residuo.
- **Prioridad:** Alta
- **Criterio de aceptación:** Al vender, el inventario queda vacío y el saldo aumenta en la suma exacta de los valores de los residuos vendidos.

#### RF-04 · Comprar herramientas
- **Descripción:** El sistema deberá mostrar una tienda donde el jugador pueda comprar herramientas que aumenten su alcance, velocidad o capacidad, siempre que tenga monedas suficientes.
- **Prioridad:** Alta
- **Criterio de aceptación:** Con saldo suficiente, la compra descuenta el precio y la herramienta mejora el atributo indicado; con saldo insuficiente, la compra se rechaza con un mensaje y el saldo no cambia.

#### RF-05 · Progresión por zonas
- **Descripción:** El sistema deberá desbloquear la siguiente zona (estanque → río → lago → playa) cuando el jugador cumpla la meta de la zona actual (por ejemplo, haber recolectado 50 residuos *— valor por definir*).
- **Prioridad:** Alta
- **Criterio de aceptación:** Al cumplir la meta, se muestra el aviso de zona desbloqueada y esta es seleccionable; antes de cumplirla, la zona aparece bloqueada.

#### RF-06 · Datos educativos
- **Descripción:** El sistema deberá mostrar un dato educativo breve (máximo 2 líneas) asociado al tipo de residuo la primera vez que el jugador lo recolecta, y al desbloquear cada zona.
- **Prioridad:** Media
- **Criterio de aceptación:** Cada tipo de residuo y cada zona tiene al menos un dato; este se muestra una sola vez por tipo y puede consultarse después en una sección "Mi colección".

#### RF-07 · Guardar y continuar progreso
- **Descripción:** El sistema deberá guardar automáticamente el progreso (monedas, herramientas, zonas desbloqueadas) y restaurarlo al volver a abrir el juego en el mismo dispositivo.
- **Prioridad:** Media
- **Criterio de aceptación:** Tras cerrar y reabrir el juego, el jugador conserva su saldo, herramientas y zonas desbloqueadas.

### 3.2 Requerimientos no funcionales

#### RNF-01 · Desempeño
- **Descripción:** El juego deberá mantener al menos 30 cuadros por segundo en un dispositivo de gama media y cargar cada zona en un máximo de 5 segundos.
- **Prioridad:** Alta
- **Criterio de aceptación:** En el dispositivo de prueba definido por el equipo, la medición durante 5 minutos de juego muestra un promedio ≥ 30 FPS y el tiempo de carga de cada zona es ≤ 5 s.

#### RNF-02 · Usabilidad para niños
- **Descripción:** El juego deberá usar controles simples (toque o clic), iconos grandes y textos cortos, de modo que un niño de la edad objetivo entienda cómo jugar sin ayuda de un adulto.
- **Prioridad:** Alta
- **Criterio de aceptación:** En una prueba con al menos 5 niños de la edad objetivo, al menos 4 recolectan y venden su primer residuo en menos de 3 minutos sin ayuda.

#### RNF-03 · Privacidad y seguridad infantil
- **Descripción:** El juego no deberá solicitar ni almacenar datos personales (nombre real, correo, ubicación), ni incluir enlaces externos, chat o publicidad.
- **Prioridad:** Alta
- **Criterio de aceptación:** La revisión del código y de los datos guardados confirma que solo se almacena el progreso del juego y que no existen enlaces, chat ni anuncios.

#### RNF-04 · Contenido apropiado y accesible
- **Descripción:** Todo el contenido deberá ser apto para niños; además, los mensajes importantes deberán ir acompañados de iconos o sonido (no solo color) y el texto tendrá un tamaño mínimo legible.
- **Prioridad:** Media
- **Criterio de aceptación:** Una revisión por el equipo y el docente no encuentra contenido inapropiado, y cada aviso (inventario lleno, saldo insuficiente, zona desbloqueada) incluye icono o sonido junto con el texto.

#### RNF-05 · Compatibilidad
- **Descripción:** El juego deberá funcionar en las dos últimas versiones de Chrome, Firefox y Edge, en pantallas desde 360 px de ancho *(por confirmar con la plataforma)*.
- **Prioridad:** Media
- **Criterio de aceptación:** Los casos de prueba de RF-01 a RF-05 pasan en los tres navegadores, en escritorio y móvil.

### 3.3 Checklist de calidad de requerimientos

| ID | Correcto | No ambiguo | Completo | Consistente | Factible | Verificable |
|---|---|---|---|---|---|---|
| RF-01 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-02 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-03 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-04 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-05 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-06 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-07 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-01 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-02 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-03 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-04 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-05 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |

### 3.4 Trazabilidad con el tablero

| Requerimiento | Issue | Responsable |
|---|---|---|
| RF-01 | #1 | @unp4n |
| RF-02 | #2 | @unp4n |
| RF-03 | #3 | @unp4n |
| RF-04 | #4 | @unp4n |
| RF-05 | #5 | @unp4n |
| RF-06 | #6 | @unpan |
| RF-07 | #7 | @unpan |
