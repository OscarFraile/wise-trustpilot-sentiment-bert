# Análisis de Reseñas Trustpilot — Wise.com con BERT

Análisis de sentimiento y topic modeling sobre reseñas de Wise.com en Trustpilot, comparado contra 69 competidores del sector Money & Insurance. Modelo BERT para clasificar sentimiento (1-5 estrellas) e identificar los temas que generan satisfacción e insatisfacción.

## Tecnologías

Python · Transformers (BERT) · HuggingFace · Pandas · Matplotlib · Jupyter Notebook

## Estructura del repositorio

```
wise-trustpilot-sentiment-bert/
├── 01_Documentos/
│   └── Wise_Analisis_Negocio_Presentacion.pdf   # Presentación de resultados
├── 02_Datos/
│   └── emp_100_reviews_xlsx.csv                 # Dataset: 100 reseñas Wise + sector
├── 03_Notebooks/
│   └── Wise_Analisis_Negocio_Notebook.ipynb     # Notebook principal
├── 99_Data/                                     # Imágenes y fuentes de la presentación
├── .gitignore
├── requirements.txt
└── README.md
```

## El problema

Wise.com tiene miles de reseñas públicas en Trustpilot. La pregunta: ¿en qué temas específicos Wise gana y pierde frente a su competencia? El análisis va más allá del sentimiento global — identifica dónde están las fricciones operativas concretas.

## Dataset

- 100 reseñas de Wise.com en Trustpilot
- 5.729 reseñas del sector Money & Insurance
- 69 empresas competidoras analizadas
- Fuente: Trustpilot Reviews 123k (dataset del sector)

## Pipeline

**1. Análisis de sentimiento**
Modelo BERT `nlptown/bert-base-multilingual-uncased-sentiment` — clasifica cada reseña de 1 a 5 estrellas agrupadas en positivo, neutro y negativo.

Resultado en Wise:
- 49% negativas
- 35% positivas
- 16% neutras

**2. Topic modeling**
Modelo entrenado sobre todas las reseñas del sector para mayor robustez. Topics con presencia en Wise:
- 19% Divisas y Comisiones
- 11% Tiempos de espera
- 11% Productos y Transferencias
- 4% Facilidad de uso
- 2% Verificación de identidad

**3. Análisis competitivo**
Comparativa de sentimiento positivo por topic entre Wise y la media del sector.

## Resultados

**Posición de Wise: 53 de 70 empresas — 12 puntos por debajo de la media del sector (47%).**

Dónde Wise supera al sector:
- Procesos fáciles y rápidos: +15%
- Transferencias internacionales: +8%

Dónde Wise está por debajo:
- Verificación de identidad: 0% positivo vs 12% sector
- Comisiones/fees: -10%
- Tiempos de respuesta: -15%

**Insight clave:** el producto core funciona bien. Los problemas están en fricciones operativas — KYC, soporte y comunicación.

## Cómo ejecutarlo

```bash
pip install -r requirements.txt

# Ejecutar: 03_Notebooks/Wise_Analisis_Negocio_Notebook.ipynb
```

---

Proyecto académico desarrollado durante el Master en Data Science de Evolve.
