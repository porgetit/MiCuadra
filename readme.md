# 🗺️ MiCuadra

### *El mapa vivo de tu cuadra — Directorio hiperlocal + Red de Mandados entre vecinos*

![Status](https://img.shields.io/badge/Estado-Documentación%20%2F%20Pre--MVP-yellow?style=flat-square)
![Region](https://img.shields.io/badge/Región-Eje%20Cafetero%2C%20Colombia-green?style=flat-square)
![License](https://img.shields.io/badge/Licencia-MIT-blue?style=flat-square)
![Team](https://img.shields.io/badge/Equipo-3%20Estudiantes%20UTP-orange?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-FastAPI%20%7C%20React%20%7C%20PostgreSQL-informational?style=flat-square)

---

## 📌 Descripción del Proyecto

**MiCuadra** es una plataforma web y móvil de tipo directorio hiperlocal que resuelve dos problemas simultáneos y complementarios en la economía informal colombiana:

1. **Para el negocio de barrio** — barberías, tiendas, panaderías, talleres, gimnasios y fruverías — que hoy son invisibles en internet a pesar de mover economías enteras a nivel de cuadra.
2. **Para el vecino o estudiante** que necesita un ingreso flexible, o que simplemente no puede salir a hacer una compra.

La plataforma combina un **directorio geoespacial gratuito** (cualquier negocio aparece en el mapa sin pagar) con una **red colaborativa de "mandados"** ejecutados por vecinos y estudiantes dentro de un radio de 5–10 cuadras. No es una app de domicilios industrial: es infraestructura comunitaria.

> *"Encuentra en segundos los negocios de tu barrio — y si no puedes salir, un vecino va por ti."*

El modelo de negocio opera por **micro-comisión por mandado completado**, generando ingresos desde la primera transacción sin requerir que ningún negocio pague una suscripción previa. El proyecto arranca con 2–3 barrios piloto en **Pereira, Risaralda**, con proyección de expansión al Eje Cafetero completo.

---

## 📂 Índice de Documentación

| Archivo | Tipo | Descripción |
|---|---|---|
| [`MiCuadraV1.md`](./micuadrav1.md) | 📋 Concepto Base | Idea original del proyecto: visión, mercado objetivo, funcionalidades, roadmap inicial, arquitectura borrador y modelo de negocio SaaS planteado por el equipo fundador. |
| [`analisis_micuadrav1.md`](./analisis_micuadrav1.md) | 🔬 Análisis Crítico | Análisis técnico-económico de la propuesta original: viabilidad del stack para un equipo de 3 estudiantes sin capital, evaluación del modelo SaaS vs. psicología del tendero, y matriz de Fortalezas vs. Riesgos. |
| [`MiCuadraV2.md`](./micuadrav2.md) | 🔄 Propuesta de Pivot | Modelo híbrido: Directorio Hiperlocal + Red de Mandados. Incluye descripción de las dos modalidades de servicio, justificación estratégica del pivot, hoja de ruta técnica por etapas y criterios de validación del MVP antes de activar el motor transaccional. |
| [`Speech.md`](./speech.md) | 🎤 Elevator Pitch | Guion oficial del pitch (2–3 minutos, ~380 palabras). Estructurado en 6 fases: Problema, Solución, Competencia, Mercado, Ingresos y Equipo. Listo para presentación oral con acotaciones de entonación. |

---

## 🏗️ Pilares de la Plataforma (Modelo Pivot)

### 🔍 Pilar 1 — Directorio Hiperlocal (Núcleo)

| Característica | Detalle |
|---|---|
| **Acceso** | Gratuito para negocios y usuarios finales |
| **Interfaz** | Mapa interactivo con filtros por categoría y cercanía |
| **Categorías** | Barberías, tiendas, panaderías, talleres, gimnasios, farmacias, fruverías, papelerías |
| **Perfil de negocio** | Fotos, horarios, catálogo, botón WhatsApp directo |
| **Registro** | Formulario guiado en 4 pasos, sin conocimientos técnicos |
| **Cobertura inicial** | 2–3 barrios piloto en Pereira, Risaralda |

### 📦 Pilar 2 — Red de Mandados entre Vecinos

| Modalidad | Descripción | Comisión plataforma |
|---|---|---|
| **A — Comprador Delegado** | El mensajero compra los productos dentro de un presupuesto indicado por el usuario | 8–12% del valor del mandado (mín. $2.000 COP) |
| **B — Transportista Puro** | El usuario ya compró; el mensajero solo recoge y entrega | $1.500–$3.000 COP fijos |

> ⚡ El negocio **nunca paga** para recibir mandados. Los mandados son el canal de adquisición de clientes que el directorio facilita.

---

## ⚙️ Stack Tecnológico Propuesto

Diseñado para **costo operativo inicial = $0**, usando capas gratuitas de servicios maduros:
