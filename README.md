# 🔍 Predicción de Churn de Clientes

Este proyecto de machine learning tiene como objetivo predecir la pérdida de clientes (*churn*) en una empresa utilizando modelos de clasificación. Se aplican técnicas de preprocesamiento, balanceo de clases, entrenamiento de modelos y comparación de métricas para identificar la mejor solución predictiva.


## 📁 Estructura del Proyecto
├── churn_prediction.ipynb # Notebook principal del análisis
├── data/
│ └── WA_Fn-UseC_-Telco-Customer-Churn.csv 
├── notebook/
│ └── Prediccion_churn_clientes.ipynb 
└── README.md 


## 🧠 Objetivos del Proyecto

- Analizar un conjunto de datos de clientes y su comportamiento.
- Preprocesar y balancear los datos para abordar el problema de clases desbalanceadas.
- Evaluar distintos modelos de clasificación:
  - Regresión Logística
  - Random Forest
  - XGBoost
- Comparar el desempeño de los modelos con y sin técnicas de balanceo (`class_weight`, SMOTE).
- Extraer conclusiones basadas en métricas de clasificación.



## 🛠️ Librerías

- Pandas, NumPy
- Scikit-learn
- XGBoost
- imbalanced-learn
- Matplotlib, Seaborn



## 📊 Comparativa de Modelos

| Modelo                       | Accuracy | Precision | Recall | F1-score |
|-----------------------------|----------|-----------|--------|----------|
| Reg. Logística              | 0.806    | 0.656     | 0.567  | 0.608    |
| Reg. Logística (balanced)   | 0.737    | 0.504     | 0.795  | 0.617    |
| Reg. Logística + SMOTE      | 0.745    | 0.514     | 0.740  | 0.606    |
| Random Forest               | 0.787    | 0.628     | 0.488  | 0.550    |
| Random Forest + SMOTE       | 0.759    | 0.542     | 0.611  | 0.575    |
| XGBoost                     | 0.780    | 0.603     | 0.508  | 0.551    |
| XGBoost + SMOTE             | 0.764    | 0.548     | 0.645  | 0.593    |


## 🔎 Evaluación de Resultados

- **Modelos sin balanceo**, como la regresión logística original, obtienen mayor **accuracy**, pero sacrifican recall, que es clave en problemas de churn.
- **Modelos balanceados**, como `class_weight` o SMOTE, **aumentan significativamente el recall**, lo que permite identificar mejor a los clientes que abandonan, aunque a costa de una leve pérdida de precisión.
- **Conclusión**: si el objetivo del negocio es **anticipar el abandono** de la mayoría de los clientes posibles, el modelo más recomendable es la **regresión logística balanceada** o con SMOTE, debido a su alto **recall y F1-score**, aun cuando su accuracy no sea el más alto.


