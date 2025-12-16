# 🖥️ RISC-V Single Cycle Processor

![Status](https://img.shields.io/badge/Status-Educational-success)
![Architecture](https://img.shields.io/badge/Architecture-RISC--V_32-blue)
![Tool](https://img.shields.io/badge/Tool-Logisim-orange)

Bienvenido al repositorio del **Procesador Monociclo RISC-V**. Este proyecto es una implementación educativa y funcional de la arquitectura RISC-V de 32 bits, diseñada y simulada completamente en **Logisim**.

## 🚀 Características Principales

Este procesador implementa el **datapath monociclo**, lo que significa que ejecuta una instrucción completa en un solo ciclo de reloj.

* ✨ **Arquitectura Modular:** Uso de librerías (`RISCVlib`) para componentes como la ALU, unidad de control y registros.
* 🧠 **Memorias Separadas:** Arquitectura Harvard con ficheros independientes para Instrucciones (`instmem`) y Datos (`datamem`).
* ⚙️ **Set de Instrucciones Soportado:**
    * **Aritmético-Lógicas:** Sumas, restas y operaciones lógicas.
    * **Acceso a Memoria:** `LW` (Load Word) y `SW` (Store Word).
    * **Saltos Condicionales:** `BEQ` (Branch if Equal) y otros saltos relativos.
    * **Saltos Incondicionales:** `JAL` (Jump And Link).

## 📂 Estructura del Proyecto

El proyecto está organizado para facilitar la simulación y el entendimiento del hardware:

| Archivo / Carpeta | Descripción |
| :--- | :--- |
| **`SA28RISCV.circ`** | 🧠 **El Cerebro.** Circuito principal que contiene el procesador completo. |
| **`RISCVlib.circ`** | 📚 **Librería.** Contiene sub-circuitos (ALU, RegFile, Control Unit). |
| **`instmem.txt`** | 📄 **Código Máquina.** Fichero hexadecimal con el programa a ejecutar. |
| **`datamem.txt`** | 💾 **Datos.** Valores iniciales para la memoria de datos (RAM). |
| **`logisim...RV.jar`** | 🛠️ **La Herramienta.** Versión específica de Logisim requerida. |

## 🛠️ Requisitos Previos

Para abrir y simular este procesador, necesitas tener instalado Java y la versión correcta de Logisim incluida en este repo.

1.  **Java Runtime Environment (JRE):** Asegúrate de tener Java instalado.
2.  **Logisim Generic (Mod RV):** Usa el archivo `logisim-generic-2.7.1-dac1.2.5.RV.jar` proporcionado, ya que contiene módulos específicos para RISC-V.

## 🎮 Cómo Usar (Simulación)

Sigue estos pasos para ver el procesador en acción:

1.  **Abrir Logisim:**
    Ejecuta el archivo .jar incluido:
    ```bash
    java -jar logisim-generic-2.7.1-dac1.2.5.RV.jar
    ```

2.  **Cargar el Procesador:**
    Ve a `File > Open` y selecciona el archivo **`SA28RISCV.circ`**.
    *(Nota: Asegúrate de que `RISCVlib.circ` esté en la misma carpeta para que cargue las dependencias).*

3.  **Cargar Memorias:**
    * Haz clic derecho en el componente de **Memoria de Instrucciones (ROM)** -> `Load Image` -> selecciona `instmem.txt`.
    * Haz clic derecho en el componente de **Memoria de Datos (RAM)** -> `Load Image` -> selecciona `datamem.txt`.

4.  **¡Ejecutar!** ⚡
    * Usa la herramienta de "Mano" (Poke) para activar el reloj manualmente.
    * O ve al menú `Simulate > Ticks Enabled` para que corra automáticamente.

## 📝 Ejemplo de Código

El archivo `instmem.txt` incluido contiene un programa de ejemplo compilado en hexadecimal:

```text
v2.0 raw
01000093  <-- Instrucción 1
00008c63  <-- Instrucción 2 (Branch)
...
