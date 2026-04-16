# 🛫 Predicción de Retrasos Aéreos
## Machine Learning con PySpark | USTA 2026-I

---

## 📦 Contenido del Repositorio

```
├── data/
│   └── flights_2015_full.csv    # 5.3M vuelos reales (2015)
├── notebooks/
│   ├── Modulo1_Exploracion.ipynb
│   ├── Modulo2_Preparacion.ipynb
│   ├── Modulo3_Modelos.ipynb
│   └── Modulo4_Evaluacion.ipynb
├── misiones/
│   └── Misiones_Departamentos.pdf
├── docker-compose.yml
├── README.md
└── GUIA_COLAB_A_DOCKER.md
```

---

## 🚀 Opción 1: Google Colab (En clase)

### Paso 1: Copiar datos a tu Drive
1. Descarga la carpeta `data/` de este repositorio
2. Súbela a tu Google Drive en: `Mi Drive/ML_Vuelos/data/`

### Paso 2: Abrir notebooks
1. Abre cada notebook en Google Colab
2. Ejecuta la primera celda (monta Drive automáticamente)
3. ¡Trabaja!

---

## 🐳 Opción 2: Docker (Entrega final)

### Requisitos
- Docker Desktop instalado
- 8GB RAM mínimo

### Paso 1: Clonar repositorio
```bash
git clone https://github.com/TU_USUARIO/ml_vuelos.git
cd ml_vuelos
```

### Paso 2: Iniciar contenedor
```bash
docker-compose up
```

### Paso 3: Abrir Jupyter
- URL: http://localhost:8888
- Token: `ml2026`

### Paso 4: Navegar a notebooks
- Ir a `work/notebooks/`
- Ejecutar módulos en orden

---

## 📚 Módulos

| # | Módulo | Objetivo | Tiempo |
|---|--------|----------|--------|
| 1 | Exploración | Conocer datos, calcular tasas | 15 min |
| 2 | Preparación | StringIndexer, VectorAssembler | 15 min |
| 3 | Modelos | Entrenar Árbol y Random Forest | 30 min |
| 4 | Evaluación | Métricas, matriz de confusión | 30 min |

---

## 🎯 Tu Misión

Cada grupo tiene una misión específica. Consulta `misiones/Misiones_Departamentos.pdf` para ver:
- Las preguntas de tu departamento
- El entregable esperado
- La recomendación para el CEO

---

## 📊 Dataset

- **Fuente**: Bureau of Transportation Statistics (USA)
- **Año**: 2015
- **Registros**: 5,332,914 vuelos
- **Tasa de retrasos**: 18.7%

### Variables

| Variable | Descripción |
|----------|-------------|
| MONTH | Mes (1-12) |
| DAY_OF_WEEK | Día (1=Lun, 7=Dom) |
| AIRLINE | Código aerolínea |
| ORIGIN | Aeropuerto origen |
| DEST | Aeropuerto destino |
| DEP_HOUR | Hora de salida (0-23) |
| DISTANCE | Distancia en millas |
| **DEP_DEL15** | **1=Retrasado ≥15min, 0=Puntual** |

---

## ❓ Problemas Comunes

### "No encuentra el archivo CSV"
- En Colab: Verifica que la ruta sea `/content/drive/MyDrive/ML_Vuelos/data/`
- En Docker: Verifica que el CSV esté en la carpeta `data/`

### "Docker no inicia"
- Verifica que Docker Desktop esté corriendo
- En Windows: Habilita WSL2

### "Spark se queda sin memoria"
- Cierra otras aplicaciones
- Usa una muestra: `df.sample(0.1)`

---

## 👩‍🏫 Contacto

Luz Adriana Gutiérrez Rodríguez  
USTA - Estadística  
2026-I
