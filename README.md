<p align="center">
  <img src="src/img/goodreads_logo_1.png" alt="Goodreads Logo" width="350"/>
</p>

# 📚 EDA: GoodReads Books

Análisis Exploratorio de Datos (EDA) sobre el dataset de mejores libros de Goodreads, con el objetivo de identificar los factores que influyen en los ratings de los libros.

---

## 📁 Estructura del Repositorio

```
EDA-GoodReads-Books/
│
├── src/
│   ├── data/
│   │   └── goodreads_best_books.csv    # Dataset original
│   └── main.ipynb                      # Notebook principal con el análisis
│
├── Memoria/
│   └── Memoria_EDA_Goodreads.pdf       # Documento del proceso
│
├── Presentacion/
│   └── EDA_Goodreads.pptx              # Presentación de resultados
│
├── .gitignore
└── README.md
```

---

## 🎯 Objetivo

Analizar qué factores influyen en los ratings de los libros en Goodreads a través de cinco hipótesis:

1. 📖 **¿Los libros con más páginas tienen mejor rating?**
2. 📗 **¿Los libros en formato Hardcover tienen mejor rating?**
3. 📚 **¿Las series tienen mejores ratings que los libros individuales?**
4. ⭐ **¿Los autores populares concentran la mayoría de valoraciones?**
5. 🏆 **¿Los autores populares tienen más premios?**

---

## 🗂️ Dataset

- **Fuente:** [Goodreads Best Books Dataset](https://www.kaggle.com/datasets/cristaliss/goodreads-books-best-books-ever)
- **Registros originales:** 52.478 libros
- **Registros tras limpieza:** 49.036 libros
- **Variables originales:** 25 columnas

### Variables principales

| Variable | Tipo | Descripción |
|---|---|---|
| `title` | str | Título del libro |
| `series` | str | Nombre de la saga (si aplica) |
| `author` | str | Autor/es |
| `rating` | float | Valoración media (0-5) |
| `bookFormat` | str | Formato (Hardcover, Paperback...) |
| `pages` | float | Número de páginas |
| `awards` | str | Lista de premios recibidos |
| `numRatings` | int | Número total de valoraciones |
| `likedPercent` | float | % de usuarios que le gustó |

---

## 🧹 Proceso de Limpieza

- Eliminación de columnas irrelevantes: `bookId`, `description`, `isbn`, `characters`, `coverImg`, `setting`
- Eliminación de columnas con exceso de nulos: `edition` (90%), `firstPublishDate` (40%), `price` (27%)
- Conversión de `pages` a tipo numérico
- Filtrado de formatos válidos: Kindle Edition, ebook, Paperback, Mass Market Paperback, Hardcover
- Eliminación de libros recopilatorios (patrón `#n-n` en columna `series`)

---

## ⚙️ Ingeniería de Variables

| Variable creada | Descripción |
|---|---|
| `is_series` | `True` si el libro pertenece a una serie |
| `main_author` | Autor principal (sin roles secundarios) |
| `num_awards` | Número de premios recibidos |
| `es_popular` | `True` si el autor está en el Top 15 por valoraciones |

---

## 📊 Principales Resultados

- Los libros digitales (Kindle/ebook) tienen ratings ligeramente superiores a los físicos
- Las series tienen mejor rating medio que los libros individuales
- J.K. Rowling, Stephen King y Suzanne Collins concentran el mayor número de valoraciones
- Los autores populares reciben de media **2,44 premios por autor**, frente a **0,47** de los no populares

---

## 🛠️ Tecnologías Utilizadas

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![Pandas](https://img.shields.io/badge/pandas-2.x-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/seaborn-0.13-4C72B0)
![Matplotlib](https://img.shields.io/badge/matplotlib-3.x-orange)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

---

## 🚀 Cómo Ejecutar

1. Clona el repositorio:
```bash
git clone https://github.com/fgoiri/EDA-GoodReads-Books.git
```

2. Instala las dependencias:
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

3. Abre el notebook:
```bash
jupyter notebook Código/EDA_Books.ipynb
```

---

## 👤 Autora

**Fátima Goiri**  
Bootcamp The Bridge Data Analytics · Abril 2026
