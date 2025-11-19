# 🧠 Autoencoders y Clasificadores Convolucionales sobre Fashion-MNIST

Análisis experimental de arquitecturas de Redes Neuronales y la **Optimización de Hiperparámetros** para tareas de reconstrucción y clasificación de imágenes.

---
[Aquí puedes insertar una imagen como la Figura 1 (esquema del autoencoder) para hacerlo visualmente atractivo. Si la subes a GitHub, el enlace será local.]

## 📝 Resumen del Proyecto

Este proyecto implementa y compara distintos tipos de **Autoencoders** (Lineal y Convolucionales) y **Clasificadores** sobre el conjunto de datos **Fashion-MNIST**. El objetivo principal es reflexionar sobre la elección de **hiperparámetros** (épocas, tamaño de lote, tasa de aprendizaje, dropout) y su impacto en el rendimiento.

### 🎯 Conclusiones Clave

* **Superioridad Convolucional:** Las Redes Convolucionales demostraron ser **superiores** a las *feed-forward* (Lineales) para este conjunto de datos, tanto para comprimir y reconstruir imágenes como para clasificarlas.
* **Reconstrucción (Autoencoders):** Aumentar el tamaño de la capa oculta mejoró la reconstrucción. El modelo **Raschka (n=128)** alcanzó un error comparable al Lineal (n=512) pero en solo **14 épocas** (vs. 60 épocas).
* **Optimización por Arquitectura:** La elección de hiperparámetros depende del tipo de red:
    * **Redes Convolucionales** (Consigna, Raschka) aprendieron mejor con **lotes pequeños (32)** y tasas de aprendizaje **bajas (0.0005)**.
    * **Redes Lineales** (*Feed-Forward*) funcionaron mejor con **lotes grandes (1000)** y tasas de aprendizaje **altas (0.001)**.
* **Estrategias de Regularización:** El *Dropout* fue más efectivo en la red Lineal, mientras que el *Pooling* ayudó a la generalización en las convolucionales.
* **Clasificación:** Se aplicó **Feature Extraction** (Transfer Learning) sobre el clasificador "Consigna" para mitigar la dependencia de valores iniciales, obteniendo mejores resultados.

## 🛠️ Modelos Implementados

| Modelo | Tipo | Capa Oculta | Épocas | Tasa de Aprendizaje | Dropout |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Autoencoder Lineal** | Feed-Forward | 512 | 60 | 0.001 | 0.1 |
| **Autoencoder Raschka** | Convolucional | 128 | 14 | 0.0005 | 0 |
| **Clasificador Consigna FE** | Convolucional | 128 | 26 | 0.0005 | 0.8 |

## 📁 Estructura del Repositorio

Asegúrate de que tu repositorio contenga los siguientes archivos para que el proyecto esté completo:

* `Tiago_Bruno_tfi_2023.pdf` (Tu informe de investigación)
* `autoencoder_lineal.py` (O el nombre del archivo con tu autoencoder lineal)
* `autoencoder_consigna.py` (O el nombre del archivo con tu autoencoder convolucional 'consigna')
* `autoencoder_raschka.py` (O el nombre del archivo con tu autoencoder convolucional 'raschka')
* `clasificador.py` (O el archivo que contiene el código de tus clasificadores)
* `requirements.txt` (Una lista de las librerías necesarias: `torch`, `numpy`, `matplotlib`, etc.)

---
## 🚀 Cómo Ejecutar el Código (Pendiente de tu código)

[Una vez que subas los archivos de código, puedes indicar los pasos exactos aquí, por ejemplo:]
1. Clonar el repositorio: `git clone https://github.com/TiagoBruno00/Redes_Neuronales.git`
2. Instalar dependencias: `pip install -r requirements.txt`
3. Ejecutar el entrenamiento del clasificador: `python clasificador.py`
