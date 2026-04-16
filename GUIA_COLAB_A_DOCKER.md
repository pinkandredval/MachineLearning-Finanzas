# 🔄 Guía: De Google Colab a Docker

## ¿Por qué hacer esto?

| En Colab | En Docker |
|----------|-----------|
| Trabajaste en clase | Entregas profesionalmente |
| Dependes de internet | Funciona offline |
| Guardado en Drive | Todo empaquetado |

---

## Pasos (10 minutos)

### 1️⃣ Descargar tu notebook de Colab

1. En Colab: `Archivo → Descargar → Descargar .ipynb`
2. Guarda el archivo en tu computador

### 2️⃣ Clonar el repositorio (si no lo tienes)

```bash
git clone https://github.com/USUARIO/ml_vuelos.git
cd ml_vuelos
```

### 3️⃣ Reemplazar el notebook

1. Copia tu `.ipynb` descargado
2. Pégalo en la carpeta `notebooks/`
3. (Opcional) Renómbralo para identificarlo

### 4️⃣ Ajustar la ruta de datos

Abre tu notebook y cambia la primera celda:

```python
# ANTES (Colab)
RUTA_DATOS = '/content/drive/MyDrive/ML_Vuelos/data/'

# DESPUÉS (Docker)
RUTA_DATOS = '../data/'
```

**💡 Tip:** El código ya detecta automáticamente si estás en Colab o Docker, así que esto debería funcionar sin cambios.

### 5️⃣ Iniciar Docker

```bash
docker-compose up
```

Espera a que aparezca:
```
Jupyter Server is running at:
http://127.0.0.1:8888/lab?token=ml2026
```

### 6️⃣ Abrir en el navegador

- URL: `http://localhost:8888`
- Token: `ml2026`

### 7️⃣ Ejecutar tu notebook

1. Navega a `work/notebooks/`
2. Abre tu notebook
3. `Kernel → Restart and Run All`
4. Verifica que todo corra sin errores

### 8️⃣ ¡Listo para presentar!

Ahora tienes tu trabajo corriendo en Docker, listo para mostrar al CEO 🎯

---

## Checklist Final

- [ ] Docker Desktop está corriendo
- [ ] `docker-compose up` no muestra errores
- [ ] Puedo acceder a `localhost:8888`
- [ ] Mi notebook corre completo sin errores
- [ ] Las gráficas y tablas se ven correctamente

---

## Problemas Comunes

### "El puerto 8888 está ocupado"

```bash
# Cambiar puerto en docker-compose.yml
ports:
  - "8889:8888"  # Usa 8889 en lugar de 8888
```

### "No encuentra el archivo de datos"

Verifica que `flights_2015_full.csv` esté en la carpeta `data/`

### "Spark se queda sin memoria"

Edita `docker-compose.yml`:
```yaml
environment:
  - SPARK_DRIVER_MEMORY=6g
```

---

**¿Problemas?** Pregunta en clase o contacta a la profesora.
