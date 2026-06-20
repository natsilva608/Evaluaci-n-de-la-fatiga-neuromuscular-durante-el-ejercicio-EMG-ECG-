# EVALUACION DE LA FATIGA NEUROMUSCULAR DURANTE EL EJERCICIO (EMG+ECG)

## Descripción

Este proyecto tiene como objetivo evaluar la fatiga neuromuscular durante una contracción isométrica sostenida mediante el análisis simultáneo de señales de Electromiografía (EMG) y Electrocardiografía (ECG). El programa fue desarrollado en Python y utiliza archivos obtenidos con un sistema de BIOPAC.

La aplicación procesa ambas señales en tiempo real a partir de un archivo con extensión `.acq` calculando la evolución de la Frecuencia Mediana (MDF) de la señal EMG y la Frecuencia Cardíaca (BPM) obtenida del ECG. Cuando se detecta una disminución significativa de la MDF, mientras la frecuencia cardíaca permanece elevada, el sistema genera una alerta indicando la presencia de fatiga muscular.

## Requisitos del sistema
- Python
- Sistema operativo Windows
- Archivo de adquisición BIOPAC (.acq) que contenga:
  - Un canal de EMG de superficie
  - Un canal de ECG (Derivación 1).

## Librerías necesarias
Antes de ejecutar el programa es necesario instalar las siguientes librerías de Python:

```bash
pip install numpy
pip install scipy
pip install matplotlib
pip install pyqt5
pip install bioread
```

Las librerías utilizadas son:
- **numpy:** procesamiento y manejo de arreglos numéricos.
- **scipy.signal:** cálculo de la densidad espectral mediante Welch y detección de picos del ECG.
- **matplotlib:** generación de las gráficas de MDF y BPM.
- **PyQt5:** desarrollo de la interfaz gráfica de usuario.
- **bioread:** lectura de archivos generados por BIOPAC (.acq).

## Ejecución del programa
1. Abrir una terminal.
2. Ubicarse en la carpeta donde se encuentra el archivo:

```
ProyectoFinal (1).py
```

3. Ejecutar el programa mediante:

```bash
python "ProyectoFinal (1).py"
```

4. Al iniciar la interfaz gráfica:
- Seleccionar **"Cargar Archivo BIOPAC (.acq)"**.
- Elegir el archivo que contiene las señales EMG y ECG.
- Presionar **"Iniciar Análisis"** para comenzar el procesamiento.

## Funcionamiento del programa
Durante la ejecución, el software realiza las siguientes tareas:
- Lee automáticamente los canales de EMG y ECG del archivo BIOPAC.
- Obtiene las frecuencias de muestreo correspondientes.
- Procesa la señal EMG en ventanas de un segundo utilizando el método de Welch para estimar la Frecuencia Mediana (MDF).
- Detecta los picos R del ECG para calcular la frecuencia cardíaca instantánea (BPM).
- Actualiza continuamente las gráficas de MDF y BPM.
- Evalúa el estado fisiológico del usuario mediante una lógica de detección de fatiga.

Si la MDF disminuye aproximadamente un 15 % respecto al valor inicial y, simultáneamente, la frecuencia cardíaca permanece elevada o continúa aumentando, el sistema mostrará el mensaje: **¡FATIGA MUSCULAR DETECTADA!**
En caso contrario, el sistema indicará que el ejercicio continúa dentro de parámetros normales.

## Salida del programa
La interfaz gráfica presenta:
  - Evolución temporal de la Frecuencia Mediana (MDF).
  - Evolución temporal de la Frecuencia Cardíaca (BPM).
  - Indicadores numéricos actualizados en tiempo real.
  - Estado del análisis mediante alertas visuales.

![image alt](https://github.com/natsilva608/Evaluaci-n-de-la-fatiga-neuromuscular-durante-el-ejercicio-EMG-ECG-/blob/f9bc70a07889178fb288a980c41aeb18611b26a7/img1.png)

![image alt](https://github.com/natsilva608/Evaluaci-n-de-la-fatiga-neuromuscular-durante-el-ejercicio-EMG-ECG-/blob/634c7df4023887d5472458051bce257e772e43fe/img2.png)
