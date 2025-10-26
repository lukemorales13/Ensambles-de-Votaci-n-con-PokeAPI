# Laboratorio ML P7 — ¡Atrapa el mejor modelo!

## Descripción del proyecto

Este trabajo forma parte del **Laboratorio 7 de la materia de Aprendizaje Automático**, cuyo objetivo fue desarrollar un **modelo predictivo capaz de determinar si un Pokémon es fuerte**, utilizando datos obtenidos desde la **PokeAPI** y aplicando diferentes **técnicas de ensamble por votación**.

El proyecto se dividió en dos fases principales:

- **Computadora A (Infraestructura):** construcción del dataset mediante la extracción de datos desde la PokeAPI y generación de la etiqueta `strong`.
- **Computadora B (Modelado):** entrenamiento de clasificadores base, implementación manual de los tres tipos de votación (dura, suave y ponderada), y evaluación comparativa de desempeño.

Todo el flujo completo se integró en un solo cuaderno: **`nb_template.ipynb`**, que también incluye un bloque final con preguntas teóricas sobre el tema de ensambles.

Repositorio del equipo: [lukemorales13/Ensambles-de-Votaci-n-con-PokeAPI](https://github.com/lukemorales13/Ensambles-de-Votaci-n-con-PokeAPI)

---

## Estructura general del notebook

| Sección | Descripción |
|----------|-------------|
| **1. Construcción del dataset (Computadora A)** | Obtención de Pokémon desde la API, cálculo de atributos y generación de la etiqueta `strong`. |
| **2. Preparación de datos** | Codificación con `OneHotEncoder`, escalado con `StandardScaler` y división en conjuntos `train` y `valid`. |
| **3. Modelos base** | Entrenamiento de cuatro clasificadores: Regresión Logística, Árbol de Decisión, KNN y SVM. |
| **4. Evaluación individual** | Cálculo de métricas: Accuracy, Precision, Recall, F1. |
| **5. Ensambles** | Implementación manual de los tres votadores: dura, suave y ponderada. |
| **6. Comparación de ensambles** | Evaluación, comparación de resultados y selección del modelo final. |
| **7. Reentrenamiento y predicciones** | Entrenamiento en todo el conjunto de datos y generación del archivo final de competencia. |
| **8. Cuestionario teórico** | Respuestas sobre conceptos teóricos de ensambles y combinación de clasificadores. |

---

## Dataset

El dataset se construyó consultando la API pública:

```
https://pokeapi.co/api/v2/pokemon/{id}
```

### Variables utilizadas

**Features empleadas por el modelo:**
- `height`
- `weight`
- `base_experience`
- `type_main`

**Variables ocultas para generar la etiqueta:**
- `hp`, `attack`, `defense`, `special_attack`, `special_defense`, `speed`

**Variables derivadas:**
- `power_score = (hp + attack + defense + special_attack + special_defense + speed) / 6`
- `strong = 1` si `power_score` está por encima del percentil 75, `0` en otro caso.

---

## Modelos implementados

Cuatro clasificadores se entrenaron utilizando **scikit-learn**, cada uno dentro de un `Pipeline` con preprocesamiento:

| Modelo | Accuracy | Precision | Recall | F1 |
|---------|-----------|------------|--------|----|
| Árbol de Decisión (`tree`) | 1.00 | 1.00 | 1.00 | 1.00 |
| KNN (`knn`) | 1.00 | 1.00 | 1.00 | 1.00 |
| SVM (`svm`) | 0.93 | 1.00 | 0.72 | 0.84 |
| Regresión Logística (`logreg`) | 0.91 | 0.90 | 0.72 | 0.80 |

**Pesos de exactitud utilizados para la votación ponderada:**

```python
{'tree': 0.98, 'svm': 0.92, 'logreg': 0.91, 'knn': 0.89}
```

---

## Ensambles de votación

Se implementaron manualmente tres votadores:

| Votador | Accuracy | Precision | Recall | F1 |
|----------|-----------|------------|--------|----|
| **Votación Suave** | 0.96 | 1.00 | 0.84 | 0.91 |
| **Votación Ponderada** | 0.96 | 1.00 | 0.84 | 0.91 |
| **Votación Dura** | 0.92 | 1.00 | 0.68 | 0.81 |

El **votador ponderado** fue seleccionado como modelo final por su estabilidad y capacidad de integrar los desempeños individuales según su exactitud.

---

## Archivo de predicciones

El cuaderno genera el archivo:

```
data/predicciones_competencia.csv
```

Formato de salida:

```
id,y_pred,EquipoNombre,VotacionTipo
0,1,EquipoPokeAPI,VotacionPonderada
1,0,,
2,1,,
...
```

---

## Conclusiones

- Se logró construir un dataset funcional directamente desde la PokeAPI.  
- Los modelos individuales alcanzaron desempeños altos, con árboles y KNN mostrando posible sobreajuste.  
- Los ensambles mejoraron la estabilidad general, destacando la votación ponderada.  
- El flujo completo se implementó sin el uso de `VotingClassifier`, validando el funcionamiento de los ensambles desde cero.  
- Las respuestas teóricas finales discuten la relación entre diversidad de modelos y reducción de varianza.

---

## Dependencias

```bash
pip install pandas numpy scikit-learn matplotlib
```

---

## Integrantes del equipo

- **Luis Enrique Morales Flores** — [lukemorales13](https://github.com/lukemorales13)
- **Emil Ehecatl Sánchez Olsen** — [Emilehecatlsanchez](https://github.com/Emilehecatlsanchez)
- **Fabián Herrera Barrón** — [FabianHeBa](https://github.com/FabianHeBa)
- **Vania Janet Raya Ríos** — [Vania-Janet](https://github.com/Vania-Janet)

---

## Archivos incluidos

```
nb_template.ipynb
README.md
predicciones_competencia.csv
```
