# 🧩 Laboratorio 7 — Ensambles de Votación: *¡Atrapa el mejor modelo!*

**Curso:** Aprendizaje Automático – Facultad de Ciencias, UNAM  
**Duración:** 2 horas  
**Formato:** Equipos de 4 integrantes con dos computadoras fijas

---

## 🎯 Objetivo
En este laboratorio, los equipos implementarán tres tipos de **ensambles de votación** aplicados a un problema de clasificación binaria basado en datos de Pokémon.  
Los estudiantes deberán:
- Consumir la **PokéAPI** para generar su propio dataset (500 registros mínimos).  
- Entrenar modelos base utilizando `scikit-learn`.  
- Construir tres votadores desde cero (sin usar los métodos de ensamble de `sklearn`).  
- Entregar un repositorio público con todo su trabajo, así como un archivo de predicciones final para el ranking de competencia.

---

## ⚙️ Instrucciones generales
1. Clona este repositorio en tu máquina local:
   ```bash
   git clone https://github.com/JAlbertoAlonso/poke-ensambles.git
   ```
2. El repositorio es **de solo lectura**. No realices *push*, *commits* ni *pull requests* sobre el original.
3. Crea un repositorio propio (público) para tu equipo y sube ahí tu trabajo final.
4. En la carpeta `docs/` encontrarás el archivo oficial de la práctica:
   ```
   Lab_ML_P7.pdf
   ```
5. En la carpeta `notebooks/` está disponible la plantilla del cuaderno:
   ```
   nb_template.ipynb
   ```
6. El conjunto de prueba (`testset.csv`) se encuentra en la carpeta `data/`.  
   Este archivo se usará para evaluar tu ensamble final.

---

## 📂 Estructura del repositorio

```
poke-ensambles/
├── data/
│   ├── testset.csv
│   └── example_dataset.csv
├── notebooks/
│   └── nb_template.ipynb
├── docs/
│   └── Lab_ML_P7.pdf
└── README.md
```

---

## 🌐 Recursos útiles
- PokéAPI: [https://pokeapi.co/api/v2/pokemon/](https://pokeapi.co/api/v2/pokemon/)
- Documentación oficial de scikit-learn: [https://scikit-learn.org/stable/](https://scikit-learn.org/stable/)

---

## ⚠️ Importante
- Los modelos base **no pueden ser ensambles potenciadores** (Boosting).  
- Todos los integrantes deben rotarse por ambas computadoras durante el laboratorio.  
- Los puntos extra se otorgarán por el **mejor README (+20 pts)** y el **mejor cuaderno (+30 pts)**.

---

© 2025 | José Alberto Alonso González  
Facultad de Ciencias – UNAM
