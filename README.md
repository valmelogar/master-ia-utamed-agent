# 🎓 Asistente Multi-Agente — Máster en Inteligencia Artificial (UTAMED)

Repositorio con un sistema de **agentes especializados (_skills_)** y un orquestador académico diseñado para acompañar a los estudiantes del **Máster en Inteligencia Artificial de UTAMED**.

Su enfoque no es simplemente dar respuestas rápidas, sino **potenciar el aprendizaje real**: ayudarte a comprender el temario paso a paso, resolver dudas teóricas, guiarte en el desarrollo de prácticas y trabajos, y preparar exámenes apoyándose directamente en tus propios apuntes locales.

---

## ✨ Características principales

- **Orquestación inteligente (`agents.md`):** Enruta automáticamente cada consulta al profesor especialista correspondiente o combina varias materias en proyectos transversales.
- **10 profesores especializados (`.agent/skills/`):** Cada asignatura cuenta con su propio archivo `SKILL.md` adaptado a su enfoque técnico y pedagógico.
- **Basado en tu temario real:** Los agentes consultan de forma prioritaria los PDFs, diapositivas y enunciados que guardes en tu carpeta local `temario/`.
- **Privacidad y respeto a los derechos de autor:** La carpeta `temario/` está configurada en `.gitignore` para que tus apuntes nunca se suban accidentalmente a GitHub.

---

## 📁 Estructura del repositorio

```text
master-ia-utamed-agent/
├── .agent/
│   └── skills/                                 # Agentes especializados (cada uno con su SKILL.md)
│       ├── profesor-agentes-inteligentes/
│       ├── profesor-aplicaciones-de-ia/
│       ├── profesor-data-science/
│       ├── profesor-deep-learning/
│       ├── profesor-etica-e-ia/
│       ├── profesor-fundamentos-ia/
│       ├── profesor-machine-learning-i/
│       ├── profesor-machine-learning-ii/
│       ├── profesor-matematicas-y-estadistica/
│       └── profesor-pln/
├── temario/                                    # Carpeta LOCAL para tus apuntes y PDFs (ignorada en Git)
│   ├── agentes-inteligentes/
│   ├── aplicaciones-de-ia/
│   ├── data-science/
│   ├── deep-learning/
│   ├── etica-e-ia/
│   ├── fundamentos-ia/
│   ├── machine-learning-i/
│   ├── machine-learning-ii/
│   ├── matematicas-1/
│   ├── matematicas-2/
│   └── pln/
├── agents.md                                   # Reglas globales de orquestación y pedagogía
├── setup_repo.py                               # Script auxiliar para inicializar la estructura
├── requirements.txt                            # Dependencias recomendadas de Python
├── .gitignore                                  # Reglas de exclusión de Git
└── README.md                                   # Documentación del proyecto
```

---

## 🚀 Guía de inicio rápido

### 1. Clona el repositorio

```bash
git clone https://github.com/valmelogar/master-ia-utamed-agent.git
cd master-ia-utamed-agent
```

### 2. Sube tu propio temario en local (⚠️ Paso imprescindible)

Por motivos de derechos de autor y peso del repositorio, **este proyecto no incluye los apuntes, PDFs ni materiales oficiales del máster**. Para que los agentes respondan basándose exactamente en el contenido de tus asignaturas:

1. Descarga el material de cada materia desde el campus virtual (temas en PDF, presentaciones, boletines de ejercicios, rúbricas o enunciados de prácticas).
2. Coloca cada archivo dentro de su subcarpeta correspondiente en `temario/` (por ejemplo, `temario/deep-learning/` o `temario/fundamentos-ia/`).
3. **No elimines los archivos `.gitkeep`** si planeas contribuir o mantener la estructura de carpetas en Git.
4. **No te preocupes por Git:** Los archivos que añadas dentro de `temario/` serán ignorados automáticamente por `.gitignore` y permanecerán únicamente en tu ordenador.

> **Nota sobre Matemáticas y Estadística:** La skill `profesor-matematicas-y-estadistica` está configurada para consultar automáticamente tanto `temario/matematicas-1/` como `temario/matematicas-2/`.

### 3. Configura el entorno de Python (opcional)

Si vas a ejecutar notebooks, scripts de apoyo o herramientas para extraer texto de tus PDFs en local:

```bash
python -m venv .venv

# En Windows:
.venv\Scripts\activate

# En macOS / Linux:
source .venv/bin/activate

pip install -r requirements.txt
```

### 4. Empieza a estudiar con tu asistente

Abre la carpeta raíz del proyecto en tu IDE o herramienta CLI compatible con agentes (`agents.md` y `.agent/skills/`), como **Gemini CLI**, **Cursor** o **Codex**, y formula tu consulta indicando la asignatura o el tema.

---

## 📚 Mapa de asignaturas y carpetas

| Asignatura                                   | Skill activa (`.agent/skills/`)      | Dónde guardar tu temario                            |
| :------------------------------------------- | :----------------------------------- | :-------------------------------------------------- |
| **Fundamentos de IA**                        | `profesor-fundamentos-ia`            | `temario/fundamentos-ia/`                           |
| **Ética e IA**                               | `profesor-etica-e-ia`                | `temario/etica-e-ia/`                               |
| **Matemáticas y Estadística**                | `profesor-matematicas-y-estadistica` | `temario/matematicas-1/` y `temario/matematicas-2/` |
| **Data Science**                             | `profesor-data-science`              | `temario/data-science/`                             |
| **Machine Learning I**                       | `profesor-machine-learning-i`        | `temario/machine-learning-i/`                       |
| **Machine Learning II**                      | `profesor-machine-learning-ii`       | `temario/machine-learning-ii/`                      |
| **Deep Learning**                            | `profesor-deep-learning`             | `temario/deep-learning/`                            |
| **Procesamiento del Lenguaje Natural (PLN)** | `profesor-pln`                       | `temario/pln/`                                      |
| **Aplicaciones de IA**                       | `profesor-aplicaciones-de-ia`        | `temario/aplicaciones-de-ia/`                       |
| **Agentes Inteligentes**                     | `profesor-agentes-inteligentes`      | `temario/agentes-inteligentes/`                     |

---

## 💡 Ejemplos de cómo usar el agente

- **Comprender teoría:** _"Explícame el mecanismo de atención en Transformers usando el temario de `deep-learning` y ponme un ejemplo intuitivo antes de ver las fórmulas."_
- **Guía en prácticas y trabajos:** _"He guardado el enunciado de la práctica en `temario/machine-learning-i/`. Ayúdame a desglosar los requisitos y a diseñar la estructura del notebook paso a paso."_
- **Preparar exámenes:** _"Hazme un test de 10 preguntas sobre el tema 3 de `etica-e-ia` basado en mis PDFs y corrígeme las respuestas explicando el porqué."_
- **Depurar código:** _"Este script de `data-science` me da un error al hacer el merge de DataFrames; explícame qué está fallando antes de corregirlo."_

---

## ⚖️ Aviso sobre derechos de autor y uso responsable

- Este repositorio contiene únicamente la arquitectura de agentes e instrucciones pedagógicas. **No incluye ni distribuye material protegido por derechos de autor** perteneciente a UTAMED ni a terceros.
- Cada usuario es responsable de utilizar exclusivamente el material al que tenga acceso legítimo y de mantenerlo en local sin subirlo a repositorios públicos.
- Los agentes están diseñados como herramienta de apoyo al estudio y mentoría; el objetivo es facilitar la comprensión real de la materia y no sustituir el trabajo original del estudiante.
