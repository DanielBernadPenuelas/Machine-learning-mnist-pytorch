# Handwritten Digit Classifier (MNIST + PyTorch)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-ee4c2c.svg)](https://pytorch.org/)

🇬🇧 English | [🇪🇸 Español](#-clasificador-de-dígitos-manuscritos-mnist--pytorch)

---

## What is this project?

This project is a working **proof of concept** of a system that automatically reads handwritten digits (0–9) from images. It is built on the public MNIST dataset and PyTorch, and it is organized so that a team can reuse, extend and maintain it.

On its own, reading a single digit may look small. In a business setting, it is the building block behind a very common need: **turning handwritten or scanned numbers into reliable, usable data without a person typing them in.**

---

## The business problem it addresses

Many organizations still depend on people to read numbers from paper or images and type them into a system. That work is:

- **Slow**: it creates backlogs and delays downstream processes.
- **Expensive**: it consumes hours of qualified staff on repetitive tasks.
- **Error-prone**: fatigue and monotony lead to typos that spread into reports, invoices and inventory.

An automated digit reader reduces all three, and frees people to handle exceptions and decisions instead of data entry.

---

## Where this kind of solution applies

| Area | Typical use case | Value delivered |
|---|---|---|
| **Logistics & postal services** | Reading handwritten postal codes, parcel or batch numbers | Faster sorting, fewer misrouted shipments |
| **Banking & finance** | Reading amounts and account numbers on cheques and paper forms | Shorter processing times, fewer manual corrections |
| **Healthcare** | Digitizing handwritten values on forms, charts and lab sheets | Less transcription error, faster record availability |
| **Retail & inventory** | Capturing handwritten counts, prices or codes from stock sheets | Up-to-date inventory without manual re-entry |
| **Manufacturing & quality control** | Reading handwritten batch, lot or measurement values on the shop floor | Better traceability with no extra workload for operators |
| **Public administration & back office** | Digitizing archives, census-style forms, paper applications | Faster citizen and customer service, searchable archives |
| **Education** | Automatic grading of numeric answers on paper exercises | Time saved for teachers, quicker feedback for students |

---

## Why this approach works for a team

- **Reusable foundation**: the same pipeline (data → model → training → evaluation) can be retrained on a company's own documents, so the project is a starting point, not a dead end.
- **Fast experimentation**: all key settings live in a single configuration file, so the team can test variations quickly and compare results.
- **Measurable results**: every training run produces performance charts, which makes it easy to report progress to non-technical stakeholders.
- **Low barrier to adoption**: it runs on a standard laptop (CPU) and automatically uses a GPU when available, so a pilot does not require special infrastructure.
- **Maintainable by design**: the code is modular and documented, so new team members can understand and change it without depending on the original author.
- **Reproducible**: trained models are saved automatically, so results can be audited and re-used.

---

## From proof of concept to real value

It is important to be clear about what this project is and is not:

- **It is** a validated, well-structured starting point that demonstrates the approach end to end.
- **It is not**, by itself, a production system. MNIST contains clean, centered, single digits. Real documents have different handwriting styles, noise, poor scans and multiple digits per field.

A realistic path to a business solution looks like this:

1. **Define the process** to automate and the cost of errors (what is an acceptable error rate?).
2. **Collect a sample of real documents** and label them.
3. **Retrain and evaluate** the model on that data, and compare it against current manual accuracy.
4. **Add a human-in-the-loop step**: low-confidence readings are sent to a person for review, so quality stays high from day one.
5. **Integrate** the model into the existing workflow (scanner, form, ERP, database) and monitor it over time.

---

## Project structure

```text
clasificador-mnist-pytorch/
├── datos/                  # Dataset download and storage
├── modelos/                # Trained models (.pth)
├── resultados/             # Generated charts and images
├── configuracion.py        # Hyperparameters and global settings
├── datos.py                # Loading, transformation and DataLoaders
├── modelo.py               # Neural network architecture
├── entrenamiento.py        # Training and evaluation loop
├── utilidades.py           # Helpers (saving, charts)
├── principal.py            # Main execution script
└── requirements.txt        # Project dependencies
```

## Quick start

```bash
pip install -r requirements.txt
python principal.py
```

The script downloads the data, trains the model, saves it in `modelos/` and writes performance charts to `resultados/`.

---
---

# 🇪🇸 Clasificador de Dígitos Manuscritos (MNIST + PyTorch)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-ee4c2c.svg)](https://pytorch.org/)

[🇬🇧 English](#handwritten-digit-classifier-mnist--pytorch) | 🇪🇸 Español

---

## ¿Qué es este proyecto?

Este proyecto es una **prueba de concepto** funcional de un sistema que lee automáticamente dígitos manuscritos (0–9) a partir de imágenes. Está construido sobre el dataset público MNIST y PyTorch, y organizado para que un equipo pueda reutilizarlo, ampliarlo y mantenerlo.

Por sí solo, leer un dígito puede parecer poco. En un entorno laboral, es la pieza base de una necesidad muy común: **convertir números escritos a mano o escaneados en datos fiables y utilizables, sin que una persona tenga que teclearlos.**

---

## El problema de negocio que aborda

Muchas organizaciones siguen dependiendo de personas que leen números en papel o en imágenes y los introducen en un sistema. Ese trabajo es:

- **Lento**: genera acumulación de tareas y retrasa los procesos posteriores.
- **Costoso**: consume horas de personal cualificado en tareas repetitivas.
- **Propenso a errores**: el cansancio y la monotonía provocan fallos de transcripción que se propagan a informes, facturas e inventarios.

Un lector automático de dígitos reduce los tres problemas y libera a las personas para ocuparse de excepciones y decisiones en lugar de la entrada de datos.

---

## Dónde se aplica este tipo de solución

| Área | Caso de uso típico | Valor aportado |
|---|---|---|
| **Logística y correos** | Lectura de códigos postales, números de paquete o de lote escritos a mano | Clasificación más rápida, menos envíos mal dirigidos |
| **Banca y finanzas** | Lectura de importes y números de cuenta en cheques y formularios en papel | Menor tiempo de procesamiento, menos correcciones manuales |
| **Sanidad** | Digitalización de valores manuscritos en fichas, gráficas y hojas de laboratorio | Menos errores de transcripción, historial disponible antes |
| **Comercio e inventario** | Captura de recuentos, precios o códigos manuscritos en hojas de stock | Inventario actualizado sin reintroducir datos a mano |
| **Industria y control de calidad** | Lectura de lotes, series o mediciones escritas a mano en planta | Mejor trazabilidad sin carga extra para los operarios |
| **Administración pública y back office** | Digitalización de archivos, formularios y solicitudes en papel | Atención más ágil, archivos en los que se puede buscar |
| **Educación** | Corrección automática de respuestas numéricas en ejercicios en papel | Ahorro de tiempo al profesorado, feedback más rápido |

---

## Por qué este enfoque funciona para un equipo

- **Base reutilizable**: el mismo flujo (datos → modelo → entrenamiento → evaluación) puede reentrenarse con los documentos propios de la empresa, así que el proyecto es un punto de partida, no un callejón sin salida.
- **Experimentación rápida**: los ajustes clave están en un único archivo de configuración, lo que permite probar variantes y comparar resultados con agilidad.
- **Resultados medibles**: cada entrenamiento genera gráficas de rendimiento, útiles para informar del avance a perfiles no técnicos.
- **Baja barrera de adopción**: funciona en un portátil estándar (CPU) y aprovecha automáticamente la GPU si existe, por lo que un piloto no exige infraestructura especial.
- **Mantenible por diseño**: el código es modular y está documentado, de modo que cualquier persona nueva puede entenderlo y modificarlo sin depender del autor original.
- **Reproducible**: los modelos entrenados se guardan automáticamente, lo que permite auditar y reutilizar los resultados.

---

## De la prueba de concepto al valor real

Conviene ser claro sobre lo que este proyecto es y lo que no es:

- **Es** un punto de partida validado y bien estructurado que demuestra el enfoque de principio a fin.
- **No es**, por sí solo, un sistema listo para producción. MNIST contiene dígitos limpios, centrados y aislados. Los documentos reales tienen caligrafías distintas, ruido, escaneos de mala calidad y varios dígitos por campo.

Un camino realista hacia una solución de negocio sería:

1. **Definir el proceso** a automatizar y el coste de los errores (¿qué tasa de error es aceptable?).
2. **Recopilar una muestra de documentos reales** y etiquetarla.
3. **Reentrenar y evaluar** el modelo con esos datos y compararlo con la precisión del proceso manual actual.
4. **Añadir una revisión humana**: las lecturas con baja confianza se envían a una persona, de modo que la calidad es alta desde el primer día.
5. **Integrar** el modelo en el flujo existente (escáner, formulario, ERP, base de datos) y monitorizarlo a lo largo del tiempo.

---

## Estructura del proyecto

```text
clasificador-mnist-pytorch/
├── datos/                  # Descarga y almacenamiento del dataset
├── modelos/                # Modelos entrenados (.pth)
├── resultados/             # Gráficas e imágenes generadas
├── configuracion.py        # Hiperparámetros y ajustes globales
├── datos.py                # Carga, transformación y DataLoaders
├── modelo.py               # Arquitectura de la red neuronal
├── entrenamiento.py        # Bucle de entrenamiento y evaluación
├── utilidades.py           # Funciones auxiliares (guardado, gráficas)
├── principal.py            # Script principal de ejecución
└── requirements.txt        # Dependencias del proyecto
```

## Inicio rápido

```bash
pip install -r requirements.txt
python principal.py
```

El script descarga los datos, entrena el modelo, lo guarda en `modelos/` y genera las gráficas de rendimiento en `resultados/`.
