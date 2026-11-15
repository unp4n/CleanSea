# Investigación: Especificación de Requerimientos de Software (SRS/ERS)

**Equipo:** Karol Roberto Navarro Urzúa | Ozmar Itiel Murguia · **Fecha:** 12/11/2026

## 1. ¿Qué es un SRS/ERS y qué problemas evita?

Un SRS (*Software Requirements Specification*) o ERS (Especificación de Requerimientos de Software) es el documento que describe *qué* debe hacer el sistema y bajo qué restricciones, sin dictar *cómo* se implementa (IEEE, 1998). Funciona como acuerdo entre clientes, usuarios y desarrolladores, y como base para diseño, pruebas y mantenimiento.

Evita problemas frecuentes: malentendidos entre cliente y equipo, funcionalidades omitidas o inventadas, retrabajo por cambios no controlados (*scope creep*) y pruebas sin criterio claro de "terminado". Corregir un error de requerimientos es mucho más caro cuanto más tarde se detecta (Wiegers & Beatty, 2013).

## 2. Estructura según IEEE 830

| Sección | Contenido |
|---|---|
| **1. Introducción** | 1.1 Propósito · 1.2 Alcance (qué hace y qué no hace) · 1.3 Definiciones, acrónimos y abreviaturas · 1.4 Referencias · 1.5 Visión general del documento |
| **2. Descripción general** | 2.1 Perspectiva del producto · 2.2 Funciones del producto · 2.3 Características de los usuarios · 2.4 Restricciones · 2.5 Suposiciones y dependencias · 2.6 Distribución de requerimientos (lo que se pospone) |
| **3. Requerimientos específicos** | Interfaces externas · Funciones (requerimientos funcionales) · Requerimientos de desempeño · Restricciones de diseño · Atributos del sistema (seguridad, fiabilidad, mantenibilidad, etc.) · Otros |
| **Apéndices / Índice** | Material de apoyo y referencias cruzadas |

Nota: IEEE 830-1998 fue reemplazada por ISO/IEC/IEEE 29148, que conserva la idea pero amplía el proceso de ingeniería de requerimientos (ISO/IEC/IEEE, 2018).

## 3. Características de un buen requerimiento

IEEE 830 y 29148 piden que sean: **correctos, no ambiguos, completos, consistentes, priorizados, verificables, modificables y trazables**. Sommerville (2016) añade que deben redactarse con un verbo claro ("el sistema deberá…") y evitar mezclar varios requerimientos en uno.

| | Ejemplo | Por qué |
|---|---|---|
| ❌ Malo | "El sistema debe ser rápido y fácil de usar." | Ambiguo y no verificable: no define "rápido" ni "fácil". |
| ✅ Bueno | "El sistema deberá mostrar los resultados de búsqueda en un máximo de 2 segundos para el 95 % de las consultas, con hasta 100 usuarios concurrentes." | Medible, específico y verificable con una prueba de carga. |

## 4. Plantillas y herramientas

- **Plantillas:** IEEE 830 (clásica y sencilla), ISO/IEC/IEEE 29148 (más completa), plantilla de Wiegers y Beatty (2013), Volere (Robertson & Robertson).
- **Escritura y versionado:** Markdown + Git/GitHub (control de versiones, revisiones por *pull request*), Google Docs/Word con historial, Confluence.
- **Gestión y trazabilidad:** GitHub Issues/Projects, Jira, Doorstop (requerimientos como código), IBM DOORS (entornos industriales).

## 5. Plantilla elegida

**IEEE 830 en formato Markdown, versionada en Git.**
Justificación: (1) es la estructura que pide la actividad (secciones 1 a 3); (2) es sencilla y bien conocida, adecuada para un proyecto académico; (3) Markdown permite versionar cambios con commits y revisarlos en *pull requests*; (4) cada requerimiento funcional se enlaza directamente con un Issue de GitHub, lo que da trazabilidad sin herramientas de pago.

## 6. Declaración de uso de IA generativa

Se usó un asistente de IA generativa (Claude) para generar un borrador de este resumen y de la estructura del SRS. El equipo verificó el contenido contra las fuentes listadas y corrigió lo necesario.

## Referencias (APA 7)

IEEE. (1998). *IEEE recommended practice for software requirements specifications* (IEEE Std 830-1998). https://doi.org/10.1109/IEEESTD.1998.88286

ISO/IEC/IEEE. (2018). *Systems and software engineering—Life cycle processes—Requirements engineering* (ISO/IEC/IEEE Standard 29148:2018). https://doi.org/10.1109/IEEESTD.2018.8559686

Sommerville, I. (2016). *Software engineering* (10th ed.). Pearson.

Wiegers, K., & Beatty, J. (2013). *Software requirements* (3rd ed.). Microsoft Press.
