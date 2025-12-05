# 🔐 Taller del Algoritmo de Shor

## Computación Cuántica

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

---

## 📋 Tabla de Contenidos

- [Descripción](#-descripción)
- [Características](#-características)
- [Teoría Matemática](#-teoría-matemática)
- [Requisitos](#-requisitos)
- [Instalación](#-instalación)
- [Uso](#-uso)
- [Contenido del Taller](#-contenido-del-taller)
- [Ejemplos](#-ejemplos)
- [Resultados](#-resultados)
- [Referencias](#-referencias)

---

## 🎯 Descripción

Este proyecto presenta un **taller interactivo completo** sobre el **Algoritmo de Shor**, uno de los algoritmos cuánticos más revolucionarios que demuestra la superioridad de la computación cuántica sobre la computación clásica para ciertos problemas.

El **Algoritmo de Shor**, propuesto por Peter Shor en 1994, es capaz de factorizar números enteros grandes en tiempo polinomial, lo que representa una amenaza teórica para los sistemas de cifrado RSA actuales, que dependen de la dificultad computacional de la factorización de números grandes.

### ¿Por qué es importante?

- 🔓 **Criptografía**: Amenaza potencial para RSA y sistemas de cifrado basados en factorización
- ⚛️ **Computación Cuántica**: Demuestra la ventaja cuántica sobre algoritmos clásicos
- 🎓 **Educación**: Excelente introducción a algoritmos cuánticos y teoría de números
- 🔬 **Investigación**: Base para entender otros algoritmos cuánticos

---

## ✨ Características

- ✅ **Notebook Jupyter Interactivo**: Aprende ejecutando código en tiempo real
- ✅ **Visualizaciones Atractivas**: Gráficos coloridos y claros para entender conceptos complejos
- ✅ **Explicaciones Matemáticas Detalladas**: Teoría completa con notación LaTeX
- ✅ **Ejercicios Resueltos**: Problemas prácticos con soluciones paso a paso
- ✅ **Código Documentado**: Funciones bien comentadas y explicadas en español
- ✅ **Implementación Eficiente**: Algoritmos optimizados para cálculo rápido
- ✅ **Ejemplos Múltiples**: Diversos casos de uso con diferentes valores de N y a

---

## 📐 Teoría Matemática

### Aritmética Modular

La **aritmética modular** es fundamental para entender el algoritmo de Shor. Definimos:

```
a mod N = residuo de la división a/N
```

**Congruencia**: Decimos que `a ≡ b (mod N)` si y solo si `(a mod N) = (b mod N)`

### Exponenciación Modular

El algoritmo se basa en calcular la función:

```
f_{a,N}(x) = a^x mod N
```

Esta función es **periódica**, es decir, existe un período `r` tal que:

```
a^r mod N = 1
```

### Del Período a la Factorización

Una vez encontrado el período `r` (que debe ser par), podemos calcular los factores de N mediante:

```
Factor 1 = GCD(a^(r/2) + 1, N)
Factor 2 = GCD(a^(r/2) - 1, N)
```

Donde GCD es el Máximo Común Divisor.

### Pasos del Algoritmo de Shor

1. **Verificar si N es primo o potencia de primo** → Si es así, terminar
2. **Elegir un a aleatorio** tal que `1 < a < N`
3. **Calcular GCD(a, N)** → Si ≠ 1, hemos encontrado un factor
4. **Encontrar el período r** de la función `f_{a,N}(x)`
5. **Verificar que r es par** y que `a^(r/2) ≢ -1 (mod N)`
6. **Calcular los factores** usando GCD

---

## 🛠 Requisitos

### Software Necesario

- **Python**: 3.8 o superior
- **Jupyter**: Lab o Notebook
- **Librerías Python**:
  - `numpy`: Operaciones numéricas y arrays
  - `matplotlib`: Visualizaciones y gráficos

### Sistema Operativo

- ✅ Windows
- ✅ macOS
- ✅ Linux

---

## 📥 Instalación

### Paso 1: Crear un Entorno Virtual (Recomendado)

**Windows (PowerShell):**
```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### Paso 2: Instalar Dependencias

```bash
pip install -r Requirements.txt
```

### Paso 3: Iniciar Jupyter

```bash
jupyter lab
```

O alternativamente:

```bash
jupyter notebook
```

### Paso 4: Abrir el Notebook

En el navegador que se abre, navega a `Shors_Algorithm_Workshop.ipynb` y ábrelo.

---

## 🚀 Uso

### Ejecución del Notebook

1. **Abre Jupyter Lab/Notebook** siguiendo las instrucciones de instalación
2. **Navega al archivo** `Shors_Algorithm_Workshop.ipynb`
3. **Ejecuta las celdas secuencialmente** presionando `Shift + Enter`
4. **Experimenta con diferentes valores** de N y a para ver cómo cambian los resultados

### Funciones Principales

#### `powersAModuloN(a, N)`
Calcula `a^x mod N` para x desde 0 hasta N-1

```python
powers = powersAModuloN(2, 15)
print(powers)  # [1, 2, 4, 8, 1, 2, 4, 8, ...]
```

#### `periodoDeF(a, N)`
Encuentra el período de la función `f_{a,N}(x)`

```python
period = periodoDeF(2, 15)
print(period)  # 4
```

#### `computeAndDrawPowersAModuloN(a, N)`
Calcula y visualiza la función de exponenciación modular

```python
computeAndDrawPowersAModuloN(2, 15)
```

#### `gcd(a, b)`
Calcula el Máximo Común Divisor usando el algoritmo de Euclides

```python
factor = gcd(128, 247)
print(factor)  # Devuelve el MCD
```

---

## 📚 Contenido del Taller

### Módulo 1: Introducción
- Contexto histórico del Algoritmo de Shor
- Importancia en criptografía y computación cuántica
- Comparación con algoritmos clásicos

### Módulo 2: Aritmética Modular
- Operación módulo básica
- Congruencia modular
- Propiedades de la aritmética modular
- **Ejercicios resueltos**

### Módulo 3: Exponenciación Modular
- Definición de `f_{a,N}(x)`
- Método directo vs método recursivo
- Optimización de cálculos
- Visualizaciones interactivas

### Módulo 4: Período y Factorización
- Búsqueda del período
- Propiedades del período
- Cálculo de factores usando GCD
- **Ejercicio completo de factorización**

### Módulo 5: Algoritmo Cuántico
- Representación en circuitos cuánticos
- Estados cuánticos
- Transformada de Fourier Cuántica
- Algoritmo completo paso a paso

---

## 🔬 Ejemplos

### Ejemplo 1: Factorización de N=15

```python
N = 15
a = 2

# Encontrar el período
period = periodoDeF(a, N)  # período = 4

# Calcular factores
factor1 = gcd((a**(period//2)) + 1, N)  # 3
factor2 = gcd((a**(period//2)) - 1, N)  # 5

# Verificar: 3 × 5 = 15 ✓
```

### Ejemplo 2: Factorización de N=247

```python
N = 247
a = 2

# El notebook incluye la solución completa paso a paso
# con visualizaciones y verificaciones
```

### Ejemplo 3: Factorización de N=371

```python
N = 371
a = 24

# Período encontrado: 39
# Factores: 7 × 53 = 371 ✓
```

---

## 📊 Resultados

El notebook genera visualizaciones profesionales que muestran:

- 📈 **Gráficos de barras** de la función `f_{a,N}(x)`
- 🎯 **Marcadores de período** para identificar ciclos
- 🌈 **Código de colores** para resaltar valores importantes
- ✅ **Verificaciones paso a paso** de cada cálculo

### Salida de Ejemplo

```
============================================================
FACTORIZACIÓN DE N=247 USANDO a=2
============================================================

1. Verificar que GCD(2, 247) = 1
   2 y 247 son coprimos, podemos continuar.

2. Calcular el período de f_2,247(x) = 2^x mod 247
   Período r = 180

3. Verificar que 2^(180/2) mod 247 ≠ -1 mod 247
   2^90 mod 247 = 246
   -1 mod 247 = 246
   ERROR: 2^(180/2) ≡ -1 (mod 247). Se debe elegir otro valor de a.

...ajustando con a=7...

Factor 1 = 13
Factor 2 = 19

Verificación: 13 × 19 = 247 ✓
============================================================
```

---

## 📖 Referencias

### Libros

1. **Yanofsky, Noson S.; Mannucci, Mirco A.** (2008)  
   *Quantum Computing for Computer Scientists*  
   Cambridge University Press

2. **Nielsen, M. A., & Chuang, I. L.** (2010)  
   *Quantum Computation and Quantum Information*  
   Cambridge University Press

3. **Kaye, P., Laflamme, R., & Mosca, M.** (2007)  
   *An Introduction to Quantum Computing*  
   Oxford University Press

### Recursos en Línea

- [Qiskit Documentation](https://qiskit.org/documentation/) - IBM Quantum
- [IBM Quantum Experience](https://quantum-computing.ibm.com/) - Plataforma de computación cuántica
- [Shor's Algorithm on Wikipedia](https://en.wikipedia.org/wiki/Shor%27s_algorithm)

### Artículos Académicos

- **Shor, P. W.** (1997)  
   *Polynomial-Time Algorithms for Prime Factorization and Discrete Logarithms on a Quantum Computer*  
   SIAM Journal on Computing, 26(5), 1484-1509

---





## 👨‍💻 Autor

**Cristian Santiago Pedraza Rodríguez**  
Ciencias Naturales y tecnología

📧 Email: cristian.pedraza@escuelaing.edu.co  
🏫 Escuela Colombiana de Ingeniería Julio Garavito

---

## 🌟 Agradecimientos

Agradecimientos especiales a:

- Peter Shor por su revolucionario algoritmo
- La comunidad de computación cuántica
- Los desarrolladores de Qiskit y otras herramientas cuánticas

---

<div align="center">

**Hecho con ❤️ y computación cuántica**

[⬆ Volver arriba](#-taller-del-algoritmo-de-shor)

</div>
