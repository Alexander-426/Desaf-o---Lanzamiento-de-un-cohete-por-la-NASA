# 🚀 Simulación del lanzamiento de un cohete mediante métodos numéricos

Aplicación web interactiva para estudiar el movimiento vertical de un cohete mediante métodos numéricos de resolución de ecuaciones diferenciales ordinarias (EDO).

El proyecto compara los métodos de **Euler explícito, Heun y Runge-Kutta de cuarto orden (RK4)** con una solución analítica exacta, permitiendo visualizar la trayectoria, velocidad, altura y errores de aproximación.

---

## 📌 1. Descripción del proyecto

Este proyecto nace como una aplicación práctica de los métodos numéricos en el contexto de la exploración espacial y la carrera hacia la Luna.

Se desarrolla un modelo matemático simplificado del lanzamiento vertical de un cohete, considerando tres fuerzas principales:

- **Empuje:** fuerza que impulsa el cohete hacia arriba.
- **Gravedad:** fuerza que actúa hacia abajo.
- **Resistencia del aire:** fuerza que se opone al movimiento.

A partir de la segunda ley de Newton, se construye un sistema de ecuaciones diferenciales que posteriormente se resuelve mediante distintos métodos numéricos.

La aplicación permite modificar los parámetros físicos, ejecutar simulaciones, comparar resultados y analizar la precisión de cada método.

> Nota histórica: el contexto de la NASA y la carrera espacial es una motivación educativa. El modelo no reproduce el software ni los procedimientos de cálculo utilizados en una misión histórica específica.

## 🎯 2. Objetivos

### Objetivo general

Desarrollar una aplicación web interactiva que permita resolver y visualizar un modelo matemático de lanzamiento de un cohete utilizando diferentes métodos numéricos.

### Objetivos específicos

- Aplicar la segunda ley de Newton al movimiento vertical.
- Formular un sistema de ecuaciones diferenciales ordinarias.
- Implementar los métodos de Euler, Heun y RK4.
- Obtener una solución analítica para validar los resultados.
- Comparar los métodos mediante tablas, gráficas y errores absolutos.
- Visualizar el comportamiento del cohete mediante una simulación animada.

## 🧮 3. Modelo matemático

Se considera un cohete de masa constante sometido a empuje constante, gravedad y resistencia del aire proporcional a la velocidad.

Por la segunda ley de Newton:

\[
T-mg-kv=m\frac{dv}{dt}
\]

El sistema de ecuaciones diferenciales es:

\[
\boxed{
\begin{aligned}
\frac{dv}{dt}&=\frac{T}{m}-g-\frac{k}{m}v\\
\frac{dy}{dt}&=v
\end{aligned}
}
\]

### Parámetros utilizados

| Parámetro | Valor | Unidad |
|---|---:|---|
| Masa (m) | 1000 | kg |
| Empuje (T) | 15000 | N |
| Gravedad (g) | 9.81 | m/s² |
| Resistencia (k) | 100 | kg/s |
| Velocidad inicial | 0 | m/s |
| Altura inicial | 0 | m |
| Tiempo de simulación | 20 | s |
| Paso de integración | 2 | s |

Sustituyendo los valores:

\[
\boxed{
\begin{aligned}
v'&=5.19-0.1v\\
y'&=v
\end{aligned}
}
\]

Condiciones iniciales:

\[
v(0)=0,\qquad y(0)=0
\]

## 📐 4. Métodos numéricos implementados

### 4.1. Método de Euler explícito

Utiliza la pendiente inicial de cada intervalo para aproximar el siguiente valor.

\[
X_{n+1}=X_n+hF(X_n)
\]

### 4.2. Método de Heun

También conocido como Euler mejorado. Calcula una predicción inicial y posteriormente corrige el resultado utilizando el promedio de dos pendientes.

\[
X^*=X_n+hF(X_n)
\]

\[
X_{n+1}=X_n+\frac{h}{2}
[F(X_n)+F(X^*)]
\]

### 4.3. Método de Runge-Kutta de cuarto orden (RK4)

Utiliza cuatro evaluaciones de la función para obtener una aproximación de mayor precisión.

\[
X_{n+1}=X_n+\frac{h}{6}
(K_1+2K_2+2K_3+K_4)
\]

### 4.4. Solución analítica

Para validar los métodos numéricos se obtiene la solución exacta del modelo:

**Velocidad:**

\[
v(t)=51.9(1-e^{-0.1t})
\]

**Altura:**

\[
y(t)=51.9t-519(1-e^{-0.1t})
\]

## 📊 5. Resultados y validación

Para un tiempo de simulación de 20 segundos y un paso de integración de 2 segundos, se obtienen los siguientes resultados:

### Comparación de resultados

| Método | Velocidad (m/s) | Altura (m) |
|---|---:|---:|
| Euler | 46.327280 | 574.727201 |
| Heun | 44.766447 | 590.335528 |
| RK4 | 44.875877 | 589.241226 |
| Analítica | 44.876099 | 589.239012 |

### Comparación de errores absolutos

| Método | Error velocidad (m/s) | Error altura (m) |
|---|---:|---:|
| Euler | 1.451181 | 14.511811 |
| Heun | 0.109652 | 1.096516 |
| RK4 | 0.000221 | 0.002214 |

### Interpretación

Los resultados muestran que:

- Euler presenta el mayor error para el paso utilizado.
- Heun mejora considerablemente la aproximación.
- RK4 presenta el menor error absoluto.
- Al disminuir el tamaño del paso de Euler, sus resultados se aproximan a la solución analítica.

Por tanto, RK4 ofrece la mayor precisión en este experimento, considerando los parámetros y el intervalo de simulación utilizados.

## 💻 6. Tecnologías utilizadas

- **HTML5:** estructura de la aplicación.
- **CSS3:** diseño visual y estilos.
- **JavaScript:** implementación de los métodos numéricos y simulación.
- **Chart.js:** generación de gráficas interactivas.
- **SVG / CSS:** elementos gráficos y animación del cohete.

La aplicación se ejecuta directamente en el navegador, sin necesidad de instalar un servidor o configurar un entorno de desarrollo.

## 🚀 7. Instalación y ejecución

### Opción 1. Ejecución local

1. Clonar el repositorio:

```bash
git clone URL_DE_TU_REPOSITORIO
```

2. Abrir el archivo HTML principal:

```text
index.html
```

También puedes abrirlo directamente desde el explorador de archivos con Google Chrome, Firefox o Microsoft Edge.

### Opción 2. GitHub Pages

Ingresar al siguiente enlace de GitHub Pages: "enlace"

**Nota:** la biblioteca Chart.js se carga mediante CDN, por lo que se necesita conexión a Internet para utilizar las gráficas.


## 🧪 9. Funcionalidades de la aplicación

- Configuración de parámetros físicos.
- Selección del método numérico.
- Modificación del paso de integración.
- Cálculo de velocidad y altura.
- Desarrollo de resultados numéricos.
- Comparación con la solución analítica.
- Gráficas de velocidad y altura.
- Tablas de resultados y errores.
- Simulación animada del lanzamiento.
- Exportación de resultados en formato CSV.

## ⚠️ 10. Limitaciones del modelo

El modelo utilizado tiene una finalidad académica y simplificada.

Se consideran constantes la masa, el empuje, la gravedad y el coeficiente de resistencia del aire.

No se consideran:

- Consumo de combustible.
- Variación de masa durante el lanzamiento.
- Variaciones de empuje del motor.
- Cambios de densidad atmosférica.
- Resistencia aerodinámica cuadrática.
- Movimiento horizontal ni dinámica orbital.

Por esta razón, los resultados no deben interpretarse como predicciones de un lanzamiento espacial real.

## 📚 11. Referencias bibliográficas

- Chapra, S. C. y Canale, R. P. *Métodos numéricos para ingenieros*. McGraw-Hill.
- Butcher, J. C. *Numerical Methods for Ordinary Differential Equations*. Wiley.
- Material de clase de la asignatura de Métodos Numéricos.

## 👨‍🎓 12. Autoría

**Proyecto académico:** Simulación del lanzamiento de un cohete mediante métodos numéricos.

**Autor:** Cristian Alexander Quispe Espinal

**Asignatura:** Métodos Numéricos

**Docente:** Brigida Carvajal Blanco

**Año:** 2026

---

⭐ Proyecto desarrollado con fines educativos para demostrar la aplicación de ecuaciones diferenciales y métodos numéricos en la simulación de fenómenos físicos.
