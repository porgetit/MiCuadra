# Ingestor/Homologador de Facturas Electrónicas XML DIAN

> **"La herramienta más rápida para pasar de un correo con factura electrónica a inventario actualizado. Diseñada para tenderos y comerciantes, no para contadores."**

---

## 📌 Visión General del Proyecto

Este proyecto es un **ingestor especializado de facturas electrónicas en formato XML (estándar UBL 2.1 de la DIAN en Colombia)**. Su propósito principal es eliminar la carga operativa y el margen de error en el proceso de recepción e ingesta de mercancía para microempresas y PYMEs.

A diferencia de los sistemas ERP tradicionalmente complejos (como Siigo o Alegra), esta solución se enfoca de manera quirúrgica (*hyper-focus*) en:

1. Extraer los datos de compras desde las facturas XML enviadas por los proveedores.
2. Facilitar una **homologación visual e intuitiva** entre el catálogo del proveedor y el inventario interno del comercio.
3. Actualizar el stock disponible en un solo clic.

---

## 🎯 Mercado Objetivo y Contexto

* **Ubicación de Impacto Inicial:** Eje Cafetero, Colombia (Pereira, Risaralda).
* **Segmento:** Microempresas y PYMEs de hasta 20 empleados.
* **Tipos de Negocio:** Ferreterías independientes, tiendas de repuestos, minimarkets/abarrotes y pequeñas droguerías.
* **Volumen de Operación:** Comercio al por menor/mayor con catálogos superiores a 100 referencias de productos.

---

## 💡 Ventaja Competitiva y Posicionamiento

En el ecosistema actual existen diversas herramientas:

* **Alegra / Siigo Nube:** Centrados en la contabilidad general y administración empresarial, con flujos de trabajo extensos para el registro de compras.
* **Bsale / QuickBooks Online:** Enfocados en venta de cara al cliente (POS) o contabilidad global sin automatización nativa para compras por XML DIAN.
* **Tickelia:** Solución dedicada al control de gastos corporativos y viáticos, no a la entrada de inventario comercial.

### **Diferenciales Clave de esta Solución:**

* **Especialización Láser:** No es un ERP genérico; es una herramienta especializada exclusivamente en la ingesta y homologación ágil de compras.
* **Módulo de Homologación Visual:** Interfaz rápida que permite asociar productos entre el proveedor y el catálogo propio. (Posiblemente mediante *drag-and-drop* o emparejamiento semi-automático)
* **Ingesta Automática por Correo:** Captura directa de archivos XML mediante buzón de correo integrado.
* **Precios Asequibles:** Modelo pensado para microempresas, ofreciendo una solución accesible para comercios que no requieren pagar módulos contables complejos.

---

## ⚙️ Funcionalidades Principales

* **Parser XML UBL 2.1 (DIAN):** Lectura e interpretación de encabezados, ítems, cantidades, valores unitarios, descuentos e impuestos.
* **Motor de Homologación de Productos:**
* Mapeo automático de ítems para proveedores recurrentes previamente asociados.
* Interfaz visual para la vinculación rápida de productos nuevos.

* **Actualización de Inventario:** Sincronización e incremento automático del stock al confirmar la recepción. (Dependiente de la integración disponible)
* **Control de Duplicados:** Validación mediante CUFE e identificadores de factura para evitar doble contabilización. (CUFE: Código Único de Facturación Electrónica)
* **Exportación e Integración:** Exportación de datos estructurados a formatos Excel, CSV o consumo mediante API para sistemas POS locales.

---

## 🚀 Roadmap de Desarrollo (Tiempos sujetos a modificaciones)*

El desarrollo se encuentra estructurado en tres fases estratégicas de validación:

![Diagrama de fases de desarrollo de Invio](/docs/invio-diagrama-de-fases.png)

### 📦 **Fase 1: Parsing Core (Semanas 1 - 3)**

* Construcción del parser en Python para extraer 100% de datos desde facturas XML UBL 2.1 reales.
* Generación de tablas ordenadas (CSV) y validación de datos con comercios locales en Pereira.

### 🧪 **Fase 2: Alfa Cerrada (Semanas 4 - 7)**

* Pruebas de campo con 3 a 5 ferreterías del Eje Cafetero.
* Desarrollo de la interfaz de usuario para homologación manual.
* Exportación de datos hacia archivos o bases de datos de inventario local.

### 🌐 **Fase 3: Beta Pública (Semanas 8 - 15)**

* Automatización de la ingesta de XML vía correo electrónico (IMAP / OAuth).
* Motor de homologación semi-automática con aprendizaje de mapeos previos.
* Integraciones mediante API con sistemas POS locales.

---

## 🏗️ Arquitectura Propuesta (Borrador)

* **Backend:** Python 3.10+ (Procesamiento XML con `lxml` / `pandas`, API con FastAPI / Flask).
* **Frontend:** Framework moderno basado en web (React / Vue) optimizado para interacción ágil.
* **Base de Datos:** PostgreSQL / SQLite (Almacenamiento de catálogo de productos, proveedores, mapa de homologaciones e historial de facturas procesadas).

---

## 💼 Modelo de Negocio y Entrega (SaaS)

**Invio** opera bajo un modelo de distribución **Software como Servicio (SaaS)** basado en la nube. Esta decisión de arquitectura y negocio responde directamente a 
las necesidades operativas de los pequeños comerciantes y microempresas, ofreciendo las siguientes ventajas estratégicas:

### 1. Delegación de la Carga Técnica
El procesamiento y parseo de las facturas electrónicas XML (estándar UBL 2.1 de la DIAN) reside de manera centralizada en la infraestructura del sistema. 
Los clientes no necesitan instalar, configurar ni mantener un backend local (*Invio Core Parser*). Toda la responsabilidad técnica, la alta disponibilidad y la capacidad 
de cómputo recaen sobre el operador del servicio.

### 2. Actualizaciones e Integración Regulatoria Transparente
Dado que la normativa fiscal y los esquemas XML de la DIAN sufren modificaciones periódicas, el modelo SaaS permite aplicar parches de seguridad, optimizaciones del motor 
de homologación y actualizaciones regulatorias en el servidor de forma inmediata. El usuario final siempre utiliza la versión más reciente y compatible sin requerir intervenciones manuales, 
descargas o interrupciones en su operación diaria.

### 3. Esquema de Suscripción Asequible y Escalable
El cobro del servicio se estructura mediante planes de suscripción mensual o anual ajustados al volumen real de facturas procesadas por el negocio, 
garantizando un costo muy inferior al de un ERP tradicional: (TODO: ajustar todos los precios de este documento a COP)

| Plan | Perfil de Comercio | Volumen Mensual de Facturas | Rango de Precio Estimado |
|---|---|---|---|
| **Micro / Inicial** | Pequeños minimarkets / Droguerías | Hasta 30 facturas / mes | $10 - $15 USD / mes |
| **Pyme Pro** | Ferreterías / Tiendas de repuestos | Hasta 100 facturas / mes | $15 - $25 USD / mes |
| **Corporativo / Multi-bodega** | Comercio de alto volumen | > 100 facturas / mes | Personalizado |

### 4. Flexibilidad y Accesibilidad
Al ser una plataforma cloud, los comerciantes pueden acceder a la interfaz de homologación y control de inventario desde cualquier dispositivo con navegador web 
(computador de escritorio, tablet o smartphone) sin depender de un servidor local en la tienda.
