# Ensambles de Votación con PokeAPI
## Laboratorio ML P7 — ¡Atrapa el mejor modelo!

<div align="center">

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3+-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Completado-success.svg)

**Equipo Charmander** 🔥

[Características](#-características) •
[Instalación](#-instalación) •
[Uso](#-uso) •
[Resultados](#-resultados) •
[Contribuir](#-cómo-contribuir)

</div>

---

## Tabla de Contenidos

- [Descripción](#-descripción)
- [Características](#-características)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Uso](#-uso)
- [Dataset](#-dataset)
- [Modelos](#-modelos-implementados)
- [Ensambles](#-ensambles-de-votación)
- [Resultados](#-resultados)
- [Pruebas](#-pruebas)
- [Roadmap](#-roadmap)
- [Contribuir](#-cómo-contribuir)
- [Autores](#-autores)
- [Licencia](#-licencia)
- [Agradecimientos](#-agradecimientos)

---

## Descripción

Este proyecto forma parte del **Laboratorio 7 de la materia de Aprendizaje Automático** y tiene como objetivo desarrollar un **modelo predictivo basado en ensambles de votación** para determinar si un Pokémon es "fuerte" (`strong`).

### 🎯 ¿Qué problema resuelve?

Clasificar Pokémon según su fuerza combinando múltiples algoritmos de Machine Learning mediante técnicas de ensamble (votación dura, suave y ponderada), demostrando cómo los ensambles pueden mejorar la estabilidad y precisión de las predicciones individuales.

### 🔬 Metodología

El proyecto se divide en dos fases principales:

- **Fase A - Infraestructura:** Construcción del dataset mediante extracción de datos desde la [PokeAPI](https://pokeapi.co/) y generación de la etiqueta objetivo `strong` basada en estadísticas base.
- **Fase B - Modelado:** Entrenamiento de clasificadores base (Regresión Logística, Árbol de Decisión, KNN, SVM), implementación **manual** de tres tipos de votación, y evaluación comparativa de desempeño.

Todo el flujo se integra en un cuaderno Jupyter: **`Charmander_Practica7_ML.ipynb`**, que incluye experimentación, análisis de resultados y un cuestionario teórico sobre ensambles.

📦 **Repositorio:** [lukemorales13/Ensambles-de-Votaci-n-con-PokeAPI](https://github.com/lukemorales13/Ensambles-de-Votaci-n-con-PokeAPI)

---

## Características

- **Extracción automatizada de datos** desde PokeAPI
- **4 algoritmos de clasificación** implementados y evaluados
- **3 métodos de votación** implementados desde cero (sin `VotingClassifier`)
- **Análisis comparativo completo** con métricas de evaluación
- **Visualizaciones** de desempeño y resultados
- **Documentación teórica** sobre ensambles de modelos
- **Pipeline de ML completo**: desde adquisición de datos hasta predicción final
- **Reproducibilidad total** con notebook autocontenido

---

## 📁 Estructura del Proyecto

```
Ensambles-de-Votación-con-PokeAPI/
│
├── README.md                           # Este archivo
├── data/
│   ├── dataset.csv                     # Dataset de entrenamiento
│   ├── example_dataset.csv             # Ejemplo de datos
│   └── testset.csv                     # Datos de prueba para competencia
│
├── docs/                               # Documentación adicional
│
└── notebooks/
    ├── Charmander_Practica7_ML.ipynb   # Notebook principal del proyecto
    ├── predicciones_competencia.csv    # Predicciones finales
    └── requirements.txt                # Dependencias del proyecto
```

---

## 🛠️ Requisitos

### Requisitos del Sistema
- **Python:** 3.8 o superior
- **Sistema Operativo:** Windows, macOS o Linux
- **RAM:** Mínimo 4GB recomendado

### Dependencias de Python

El proyecto utiliza las siguientes bibliotecas principales:

```txt
pandas>=2.0.0          # Manipulación de datos
numpy>=1.24.0          # Cálculos numéricos
scikit-learn>=1.3.0    # Algoritmos de ML
matplotlib>=3.7.0      # Visualización
seaborn>=0.12.0        # Visualización estadística
requests>=2.31.0       # Peticiones HTTP a la API
jupyter>=1.0.0         # Entorno de notebooks
```

Ver [`requirements.txt`](notebooks/requirements.txt) para la lista completa.

---

## 🚀 Instalación

### 1️⃣ Clonar el repositorio

```bash
git clone https://github.com/lukemorales13/Ensambles-de-Votaci-n-con-PokeAPI.git
cd Ensambles-de-Votaci-n-con-PokeAPI
```

### 2️⃣ Crear un entorno virtual (recomendado)

```bash
# En macOS/Linux
python3 -m venv venv
source venv/bin/activate

# En Windows
python -m venv venv
venv\Scripts\activate
```

### 3️⃣ Instalar dependencias

```bash
pip install -r notebooks/requirements.txt
```

### 4️⃣ Verificar instalación

```bash
python -c "import sklearn, pandas, numpy; print('✅ Instalación exitosa')"
```

---

## Uso

### Ejecución del Notebook

1. **Iniciar Jupyter Notebook:**

```bash
cd notebooks
jupyter notebook
```

2. **Abrir el notebook principal:**
   - Navega a `Charmander_Practica7_ML.ipynb`
   - Ejecuta las celdas en orden secuencial

### Flujo de Trabajo

El notebook sigue esta estructura:

| Paso | Sección | Descripción |
|------|---------|-------------|
| 1️⃣ | **Construcción del Dataset** | Obtención de Pokémon desde la API y generación de features |
| 2️⃣ | **Preparación de Datos** | Codificación, escalado y división train/valid |
| 3️⃣ | **Modelos Base** | Entrenamiento de 4 clasificadores individuales |
| 4️⃣ | **Evaluación Individual** | Cálculo de métricas (Accuracy, Precision, Recall, F1) |
| 5️⃣ | **Ensambles** | Implementación manual de votación dura, suave y ponderada |
| 6️⃣ | **Comparación** | Análisis comparativo de todos los modelos |
| 7️⃣ | **Predicción Final** | Generación de predicciones para competencia |
| 8️⃣ | **Cuestionario Teórico** | Respuestas sobre conceptos de ensambles |

### Ejemplo de Uso Rápido

```python
# Importar librerías necesarias
import pandas as pd
from sklearn.model_selection import train_test_split

# Cargar dataset
df = pd.read_csv('../data/dataset.csv')

# Entrenar modelos y ensambles (ver notebook completo)
# ...

# Generar predicciones
predictions = weighted_voting_predict(X_test)
```



---

## Dataset

### Fuente de Datos

Los datos se obtienen de la API pública de Pokémon:

```
https://pokeapi.co/api/v2/pokemon/{id}
```

### Variables del Modelo

#### Features (Variables de Entrada)

Estas son las variables utilizadas para entrenar el modelo:

| Variable | Tipo | Descripción |
|----------|------|-------------|
| `height` | Numérica | Altura del Pokémon |
| `weight` | Numérica | Peso del Pokémon |
| `base_experience` | Numérica | Experiencia base |
| `type_main` | Categórica | Tipo principal del Pokémon |

#### Variable Objetivo

- **`strong`**: Variable binaria (0 o 1) que indica si un Pokémon es "fuerte"

#### Proceso de Generación de la Etiqueta

La etiqueta `strong` se genera mediante:

1. **Cálculo de Power Score:**
   ```python
   power_score = (hp + attack + defense + special_attack + 
                  special_defense + speed) / 6
   ```

2. **Umbral de clasificación:**
   - `strong = 1` si `power_score` > percentil 75
   - `strong = 0` en caso contrario

> **Nota:** Las estadísticas base (hp, attack, defense, etc.) se usan **únicamente** para generar la etiqueta, **no** como features del modelo, evitando así data leakage.



---

## Modelos Implementados

Se entrenaron **cuatro clasificadores** usando scikit-learn, cada uno integrado en un `Pipeline` con preprocesamiento:

### Resultados de Modelos Individuales

| Modelo | Accuracy | Precision | Recall | F1-Score | Observaciones |
|--------|----------|-----------|--------|----------|---------------|
| **Árbol de Decisión** | 1.00 | 1.00 | 1.00 | 1.00 |
| **KNN** | 1.00 | 1.00 | 1.00 | 1.00 |
| **SVM** | 0.93 | 1.00 | 0.72 | 0.84 |
| **Regresión Logística** | 0.91 | 0.90 | 0.72 | 0.80 |

### Preprocesamiento

Cada modelo incluye:

1. **OneHotEncoder** para variables categóricas (`type_main`)
2. **StandardScaler** para normalización de variables numéricas
3. **Pipeline de scikit-learn** para garantizar consistencia

### Pesos para Votación Ponderada

Los pesos se calcularon basándose en la exactitud de validación:

```python
weights = {
    'tree': 0.98,
    'svm': 0.92,
    'logreg': 0.91,
    'knn': 0.89
}
```



---

## Ensambles de Votación

Se implementaron **manualmente** (sin usar `VotingClassifier` de scikit-learn) tres métodos de votación:

### Tipos de Votación

#### 1. Votación Dura (Hard Voting)
- **Concepto:** Voto por mayoría simple
- **Implementación:** Cada modelo vota por una clase, gana la clase con más votos

#### 2. Votación Suave (Soft Voting)
- **Concepto:** Promedio de probabilidades
- **Implementación:** Se promedian las probabilidades de clase y se elige la de mayor valor

#### 3. Votación Ponderada (Weighted Voting)
- **Concepto:** Voto ponderado por desempeño
- **Implementación:** Se ponderan las probabilidades según el accuracy de cada modelo

### Resultados Comparativos

| Método de Votación | Accuracy | Precision | Recall | F1-Score |
|-------------------|----------|-----------|--------|----------|
| 🥇 **Votación Suave** | **0.96** | **1.00** | **0.84** | **0.91** |
| 🥈 **Votación Ponderada** | **0.96** | **1.00** | **0.84** | **0.91** |
| 🥉 **Votación Dura** | 0.92 | 1.00 | 0.68 | 0.81 |

### Modelo Final Seleccionado

**🏆 Votación Ponderada**

**Razones de la selección:**
- Mejor balance entre precisión y recall
- Incorpora el desempeño individual de cada modelo
- Mayor estabilidad en predicciones



---

## Resultados

### Métricas Finales

El modelo de **Votación Ponderada** alcanzó los siguientes resultados en el conjunto de validación:

- **Accuracy:** 96%
- **Precision:** 100%
- **Recall:** 84%
- **F1-Score:** 91%

### Archivo de Predicciones

El notebook genera automáticamente el archivo de predicciones para competencia:

**Ubicación:** `notebooks/predicciones_competencia.csv`

**Formato:**
```csv
id,y_pred,EquipoNombre,VotacionTipo
0,1,EquipoCharmander,VotacionPonderada
1,0,EquipoCharmander,VotacionPonderada
2,1,EquipoCharmander,VotacionPonderada
...
```

### Conclusiones Principales

**Dataset funcional:** Se construyó exitosamente desde PokeAPI sin datasets precargados

**Alto desempeño individual:** Los modelos base mostraron excelentes métricas 

**Mejora mediante ensambles:** La votación ponderada mejoró la estabilidad sin sacrificar precisión

**Implementación desde cero:** Se validó el funcionamiento manual de los ensambles sin usar `VotingClassifier`

**Diversidad = reducción de varianza:** Los ensambles demostraron menor varianza que modelos individuales

---

## Pruebas

### Validación del Modelo

El proyecto incluye:

- **División train/validation:** 80/20 con `random_state=42` para reproducibilidad
- **Evaluación con múltiples métricas:** Accuracy, Precision, Recall, F1
- **Validación cruzada implícita:** A través de diferentes conjuntos de validación

### Cómo Ejecutar las Pruebas

1. Ejecutar todas las celdas del notebook en orden
2. Verificar que las métricas coincidan con las reportadas
3. Comprobar que se genera `predicciones_competencia.csv`

### Reproducibilidad

Para garantizar resultados consistentes:
- Se utiliza `random_state=42` en todas las operaciones aleatorias
- Las versiones de librerías están especificadas en `requirements.txt`
- El proceso completo está documentado paso a paso

---

## Roadmap

### ✅ Completado

- [x] Extracción de datos desde PokeAPI
- [x] Generación de variable objetivo `strong`
- [x] Implementación de 4 clasificadores base
- [x] Implementación manual de 3 tipos de votación
- [x] Evaluación y comparación de modelos
- [x] Generación de predicciones finales
- [x] Documentación completa del proyecto

### Estado Actual

**Proyecto Completado**

El proyecto cumplió todos los objetivos del Laboratorio 7.

### Mejoras Futuras

- [ ] Implementar técnicas adicionales de ensamble (Bagging, Boosting)
- [ ] Agregar validación cruzada estratificada
- [ ] Experimentar con más features de la PokeAPI
- [ ] Optimización de hiperparámetros con GridSearch
- [ ] Dashboard interactivo con Streamlit o Dash
- [ ] API REST para predicciones en tiempo real
- [ ] Dockerización del proyecto

---

## 🤝 Cómo Contribuir

Aunque este es un proyecto académico completado, las contribuciones son bienvenidas para mejoras educativas.

### Proceso de Contribución

1. **Fork** el repositorio
2. **Crea una rama** para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** tus cambios (`git commit -m 'Add: nueva característica'`)
4. **Push** a la rama (`git push origin feature/AmazingFeature`)
5. **Abre un Pull Request**

### Guías de Contribución

- Mantén el código limpio y comentado
- Sigue las convenciones de PEP 8 para Python
- Actualiza la documentación si es necesario
- Asegúrate de que el código sea reproducible

### Reportar Problemas

Si encuentras algún bug o tienes sugerencias:

1. Revisa si ya existe un issue similar
2. Crea un nuevo issue con:
   - Descripción clara del problema
   - Pasos para reproducirlo
   - Comportamiento esperado vs actual
   - Screenshots si es aplicable

---

## 👥 Autores

**Equipo Charmander** 🔥

| Miembro | GitHub | Rol |
|---------|--------|-----|
| **Luis Enrique Morales Flores** | [@lukemorales13](https://github.com/lukemorales13) | Líder del equipo, desarrollo principal |
| **Emil Ehecatl Sánchez Olsen** | [@Emilehecatlsanchez](https://github.com/Emilehecatlsanchez) | Implementación de ensambles |
| **Fabián Herrera Barrón** | [@FabianHeBa](https://github.com/FabianHeBa) | Implementación de ensambles |
| **Vania Janet Raya Ríos** | [@Vania-Janet](https://github.com/Vania-Janet) | Análisis de datos y teoría de ensambles |

---

## 📄 Licencia

Este proyecto se distribuye bajo la **Licencia MIT**. Ver el archivo `LICENSE` para más detalles.

```
MIT License

Copyright (c) 2025 Equipo Charmander

Se concede permiso, de forma gratuita, a cualquier persona que obtenga una copia
de este software y archivos de documentación asociados (el "Software"), para usar
el Software sin restricciones, incluyendo sin limitación los derechos de usar,
copiar, modificar, fusionar, publicar, distribuir, sublicenciar y/o vender copias
del Software, sujeto a las siguientes condiciones:

El aviso de copyright anterior y este aviso de permiso se incluirán en todas las
copias o porciones sustanciales del Software.
```

---

**⭐ Si este proyecto te resultó útil, considera darle una estrella ⭐**

Hecho con ❤️ por **Equipo Charmander** 🔥

[Volver arriba](#-ensambles-de-votación-con-pokeapi)

</div>
