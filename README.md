# Trabajo_3
Algoritmo Random Forest y Regresión logística que permite predecir que equipos llegaran a cuartos de final del mundial
# ⚽ Predicción de Cuartos de Final — FIFA World Cup 2026

Proyecto de análisis predictivo desarrollado para estimar la probabilidad de que cada selección nacional clasifique a los **Cuartos de Final** del Mundial FIFA 2026, utilizando datos históricos de torneos anteriores (2002–2022).

---

## 📌 Descripción del proyecto

Se construyó un modelo de clasificación supervisada usando datos a nivel de equipo por edición del torneo. El análisis incluye:

- Exploración y análisis descriptivo del dataset
- Tratamiento de valores nulos mediante imputación con mediana
- Feature engineering para enriquecer las variables originales
- Entrenamiento de modelos: Random Forest y Logistic Regression
- Ensemble de modelos ponderado
- Evaluación con validación cruzada estratificada (AUC-ROC)
- Explicabilidad del modelo con valores SHAP
- Predicciones de probabilidad para los 48 equipos del Mundial 2026

---

## 📁 Estructura del repositorio

```
fifa-worldcup-2026-prediction/
│
├── trabajo_3.ipynb         # Notebook principal con todo el análisis
├── train.csv               # Dataset de entrenamiento (2002–2022)
├── test.csv                # Dataset de prueba (2026)
├── requirements.txt        # Librerías necesarias
└── README.md               # Este archivo
```

---

## 🗂️ Dataset

**Fuente:** [FIFA World Cup Team Dataset — Kaggle](https://www.kaggle.com/datasets/harrachimustapha/fifa-world-cup-team-dataset)

- **Train:** 192 registros · 6 ediciones (2002, 2006, 2010, 2014, 2018, 2022)
- **Test:** 48 registros · Mundial 2026
- **Variable objetivo:** `quarter_finalist` (1 = llegó a cuartos, 0 = no llegó)

### Variables principales

| Variable | Descripción |
|----------|-------------|
| `fifa_rank_pre_tournament` | Ranking FIFA antes del torneo |
| `squad_total_market_value_eur` | Valor de mercado de la plantilla (€) |
| `quarterfinals_before` | Veces que llegó a cuartos históricamente |
| `wins_last_4y` | Partidos ganados en los últimos 4 años |
| `world_cup_titles_before` | Títulos mundiales previos |
| `quarter_finalist` | Variable objetivo (binaria) |

---

## ⚙️ Instrucciones para correr el proyecto

### Opción A — Google Colab (recomendado)

1. Abre [Google Colab](https://colab.research.google.com)
2. Ve a **Archivo → Subir notebook** y sube `trabajo_3.ipynb`
3. Ejecuta la primera celda para instalar dependencias:
```bash
!pip install -r requirements.txt
```
4. Cuando se solicite, sube `train.csv` y `test.csv`
5. Ejecuta todas las celdas en orden con **Runtime → Run all**

### Opción B — Entorno local

```bash
# 1. Clonar el repositorio
git clone https://github.com/TU_USUARIO/fifa-worldcup-2026-prediction.git
cd fifa-worldcup-2026-prediction

# 2. Instalar dependencias
pip install -r requirements.txt

# 3. Abrir el notebook
jupyter notebook trabajo_3.ipynb
```

---

## 🧠 Modelos utilizados

| Modelo | AUC-ROC (CV) |
|--------|-------------|
| Random Forest | 0.719 |
| Logistic Regression | 0.799 |
| **Ensemble (ponderado)** | **~0.76** |

---

## 🏆 Top 5 predicciones — Mundial 2026

| # | Equipo | Probabilidad |
|---|--------|-------------|
| 1 | Argentina | Alta |
| 2 | Francia | Alta |
| 3 | España | Alta |
| 4 | Inglaterra | Alta |
| 5 | Alemania | Media-Alta |

---

## 🤖 Uso de IA

Este proyecto utilizó **Claude (Anthropic)** como asistente técnico para la generación de código, visualizaciones y estructura del análisis. Todas las decisiones analíticas, interpretaciones y validaciones fueron realizadas por la autora. Ver celda de documentación de IA en el notebook.

---

## 👩‍💻 Autores

**Maribel Ramírez Gaviria**  
**Jaider Andres Cataño Ospina**  
Curso III — Análisis de Datos  
Junio 2026
