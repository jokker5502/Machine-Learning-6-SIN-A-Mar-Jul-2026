# Machine-Learning-6-SIN-A-Mar-Jul-2026

## Integrantes
- Bryan Montaguano
- Mateo Villacreses

## Dataset
**Wine Quality — Red Wine (UCI Machine Learning Repository)**
- Fuente: https://archive.ics.uci.edu/dataset/186/wine+quality
- 1 599 instancias, 11 features fisicoquímicas
- **Target regresión:** `quality` (puntaje numérico 0–10)
- **Target clasificación:** `is_good` (binario: 1 si quality ≥ 7, 0 en caso contrario)

## Justificación de herramientas

Se eligió **Pandas** para el manejo y wrangling de datos porque ofrece estructuras de datos tabulares (DataFrame) optimizadas para datasets de tamaño mediano, con una API intuitiva para carga, limpieza y exploración que discutimos en clase. Se eligió **Scikit-learn** como framework de modelado porque proporciona una interfaz unificada (`fit` / `predict`) para regresión lineal y logística, incluye la clase `Pipeline` que evita *data leakage* entre entrenamiento y prueba, y cuenta con todas las métricas requeridas por el trabajo. Ambas bibliotecas están mantenidas activamente, tienen documentación extensa y son el estándar de la industria para proyectos de Machine Learning clásico a escala moderada. Descartamos PyTorch/TensorFlow porque la complejidad de redes neuronales no es justificable para un sprint de un día con dos modelos lineales.

## Instrucciones para reproducir

```bash
# 1. Clonar el repositorio (rama p2)
git clone -b p2 https://github.com/jokker5502/Machine-Learning-6-SIN-A-Mar-Jul-2026.git

# 2. Abrir en VS Code y seleccionar "Reopen in Container"
#    (DevContainers instala todas las dependencias automáticamente)

# 3. Ejecutar el notebook de arriba a abajo
jupyter nbconvert --to notebook --execute notebooks/main.ipynb
```

> ⚠️ **No usar** `!pip install` ni `!curl` dentro del cuaderno. Todo está declarado en `pyproject.toml` y bloqueado en `uv.lock`.

## Resultados

| Modelo | Métrica | Valor |
|--------|---------|-------|
| Regresión Lineal | R² | 0.4032 |
| Regresión Lineal | MAE | 0.5035 |
| Regresión Lineal | RMSE | 0.6245 |
| Regresión Logística (L2) | Accuracy | 0.8656 |
| Regresión Logística (L2) | Precision | 0.5909 |
| Regresión Logística (L2) | Recall | 0.2766 |
| Regresión Logística (L2) | F1-Score | 0.3768 |
| Regresión Logística (L2) | ROC-AUC | 0.8874 |

## Uso de IA

Utilizamos **Claude (Anthropic)** como apoyo durante el desarrollo: nos ayudó a entender cómo estructurar el pipeline de Scikit-learn, a interpretar las métricas de los modelos y a revisar la redacción de los párrafos de interpretación. Todo el código fue revisado y explicado entre los dos integrantes del equipo.
