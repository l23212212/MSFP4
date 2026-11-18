[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=l23212212/MSFP4)

# Práctica 4: Sistema Endocrino

Repositorio académico de la asignatura **Modelado de Sistemas Fisiológicos**, correspondiente al programa de **Ingeniería Biomédica** del Tecnológico Nacional de México / Instituto Tecnológico de Tijuana.

Esta práctica aborda el modelado matemático y la simulación computacional de un sistema endocrino mediante un circuito eléctrico RLC de segundo orden, integrando herramientas de análisis matemático, programación y modelado fisiológico. Se emplean MATLAB, Simulink, Simscape y Python para desarrollar y comparar las representaciones del sistema, así como recursos gráficos para ilustrar los procesos de secreción, transporte y respuesta hormonal.

El propósito es comprender el comportamiento dinámico y los mecanismos de regulación del sistema endocrino mediante su representación matemática, analizar los parámetros involucrados en condiciones normales y alteradas, y evaluar el desempeño de un controlador PID en lazo cerrado.

---

## Información del estudiante

**Estudiante:** Diego Macias Armenta  
**Número de control:** 23212212  
**Correo institucional:** l23212212@tectijuana.edu.mx  
**Docente:** Dr. Paul Antonio Valle Trujillo  
**Correo del docente:** paul.valle@tectijuana.edu.mx  
**Asignatura:** Modelado de Sistemas Fisiológicos  
**Programa:** Ingeniería Biomédica  
**Departamento:** Ingeniería Eléctrica y Electrónica  
**Institución:** Tecnológico Nacional de México / Instituto Tecnológico de Tijuana

---

## Contenido

1. [Resumen](#1-resumen)
2. [Competencia y objetivos](#2-competencia-y-objetivos)
3. [Relación con el temario](#3-relación-con-el-temario)
4. [Modelo fisiológico y circuito equivalente](#4-modelo-fisiológico-y-circuito-equivalente)
5. [Parámetros del circuito equivalente](#5-parámetros-del-circuito-equivalente)
6. [Análisis matemático](#6-análisis-matemático)
7. [Cálculo del error en estado estable](#7-cálculo-del-error-en-estado-estable)
8. [Evaluación de la estabilidad en lazo abierto](#8-evaluación-de-la-estabilidad-en-lazo-abierto)
9. [Modelo en Simulink y Simscape](#9-modelo-en-simulink-y-simscape)
10. [Ejecución mediante MATLAB](#10-ejecución-mediante-matlab)
11. [Diseño y ajuste del controlador PID](#11-diseño-y-ajuste-del-controlador-pid)
12. [Desarrollo complementario en Python](#12-desarrollo-complementario-en-python)
13. [Representación biológica en BioRender](#13-representación-biológica-en-biorender)
14. [Discusión final](#14-discusión-final)
15. [Secuencia de trabajo](#15-secuencia-de-trabajo)
16. [Requisitos para reproducir la práctica](#16-requisitos-para-reproducir-la-práctica)
17. [Fuentes consultadas](#17-fuentes-consultadas)
18. [Uso académico](#uso-académico)

---

## 1. Resumen

La práctica tiene como finalidad estudiar el comportamiento dinámico de un sistema endocrino mediante herramientas de modelado matemático y simulación computacional. Para ello, se utilizan los conocimientos de la asignatura Modelado de Sistemas Fisiológicos, relacionando los principios de circuitos eléctricos de segundo orden y teoría de control con los procesos de secreción, difusión, almacenamiento y respuesta hormonal en órganos diana.

El desarrollo contempla la deducción de las ecuaciones integro-diferenciales, la ecuación diferencial ordinaria de segundo orden y la función de transferencia del sistema, así como la implementación de simulaciones en MATLAB, Simulink, Simscape y Python. Ambas plataformas permiten comparar la respuesta de un individuo sano (control) frente a una condición alterada (caso) y diseñar un controlador PID capaz de eliminar el error en estado estacionario.

Asimismo, se incorporan recursos gráficos para complementar la interpretación fisiológica del modelo y facilitar la comprensión de los elementos que conforman el sistema endocrino analizado.

**Palabras clave:** sistema endocrino; circuito RLC; modelado fisiológico; análisis matemático; controlador PID; MATLAB; Python; Ingeniería Biomédica.

---

## 2. Competencia y objetivos

### Competencia a desarrollar

Aplicar herramientas de modelado matemático y simulación computacional para representar y analizar sistemas fisiológicos, relacionando sus parámetros y comportamiento dinámico con los principios fundamentales de la Ingeniería Biomédica.

### Objetivo general

Desarrollar y analizar un modelo matemático de un sistema endocrino mediante un circuito equivalente de segundo orden utilizando MATLAB y Python, evaluando su respuesta transitoria, estabilidad en lazo abierto, error en estado estable y compensación mediante un controlador PID.

### Objetivos específicos

- Identificar los elementos fisiológicos involucrados en la secreción, transporte, almacenamiento y acción hormonal sobre el órgano diana.
- Obtener el modelo de ecuaciones integro-diferenciales, la ecuación diferencial de segundo orden y la función de transferencia del sistema endocrino.
- Analizar la influencia de los parámetros fisiológicos equivalentes ($R_2$ y $C$) sobre la rapidez, amortiguamiento y ganancia estacionaria del sistema.
- Implementar y validar el modelo mediante circuito eléctrico (Simscape), función de transferencia y ecuaciones integro-diferenciales en Simulink.
- Diseñar y sintonizar un controlador PID en lazo cerrado para corregir la respuesta del caso patológico respecto al control.
- Reproducir el análisis y las simulaciones mediante programación en Python.
- Comparar e interpretar los resultados obtenidos en ambas herramientas computacionales desde una perspectiva fisiológica y matemática.

---

## 3. Relación con el temario

La práctica integra conocimientos de modelado matemático, análisis de sistemas fisiológicos y herramientas computacionales, permitiendo aplicar los fundamentos de Ingeniería de Control y simulación al estudio del sistema endocrino.

| Área de conocimiento | Aplicación en la práctica |
|---|---|
| Modelado matemático | Representación del sistema endocrino mediante un circuito eléctrico RLC de segundo orden. |
| Análisis matemático | Deducción de ecuaciones integro-diferenciales, EDO, función de transferencia, polos y error estacionario. |
| Sistemas fisiológicos | Interpretación de la secreción glandular, difusión sanguínea, almacenamiento tisular y respuesta del órgano diana. |
| MATLAB y Simulink | Simulación multicominio (Simscape, bloques de transferencia, EID) y sintonización del controlador PID. |
| Python | Desarrollo de una implementación computacional alternativa para verificación numérica. |
| Análisis de resultados | Comparación e interpretación de las respuestas transitorias y estacionarias en lazo abierto y cerrado. |

---

## 4. Modelo fisiológico y circuito equivalente

### Descripción fisiológica y analogía eléctrica

El sistema endocrino regula diversas funciones fisiológicas mediante la liberación de hormonas al torrente sanguíneo, las cuales viajan hacia órganos diana (como la glándula suprarrenal o la tiroides) para inducir respuestas específicas. Esta dinámica se aproxima mediante un circuito eléctrico RLC de segundo orden bajo las siguientes equivalencias:

| Elemento / Variable | Interpretación fisiológica dentro del modelo |
|---|---|
| $V_e(t)$ | Estímulo inicial o señal homeostática/neural que desencadena la secreción hormonal desde una glándula (hipófisis o hipotálamo) |
| $R_1$ | Resistencia asociada al retraso y pérdida de señal hormonal durante su liberación y difusión en el torrente sanguíneo |
| $C$ | Capacitancia que representa el almacenamiento o acumulación temporal de hormonas en tejidos o compartimentos intermedios |
| $R_2$ | Resistencia al cambio hormonal en el tejido del órgano diana |
| $L$ | Inductancia asociada a la inercia de la respuesta biológica del órgano diana |
| $F_e(t)$ | Flujo de secreción hormonal en la malla principal |
| $F_s(t)$ | Flujo de absorción hormonal en la rama del órgano diana |
| $F_c(t)$ | Flujo de acumulación hormonal hacia el compartimento capacitativo |
| $V_s(t)$ | Voltaje en el nodo de unión; representa la **respuesta hormonal efectiva observada** en el organismo |

**Variable de salida considerada:** tanto el análisis analítico como las simulaciones computacionales toman $V_s(t)$ como variable de salida. Al ser un modelo basado en analogía eléctrica, la función de transferencia estudiada es $G(s)=V_s(s)/V_e(s)$ y las señales simuladas se expresan en voltios (V).

### Estructura del circuito RLC

El circuito se organiza en dos mallas acopladas en el nodo de salida $V_s(t)$:

- **Malla principal ($M_1$):** contiene la fuente de voltaje de entrada $V_e(t)$ conectada en serie con el resistor $R_1$, por donde circula el flujo de secreción hormonal $F_e(t)$ hacia el nodo $V_s(t)$.
- **Malla secundaria ($M_2$):** conectada entre el nodo $V_s(t)$ y referencia (tierra), conformada por dos ramas en paralelo:
  - Una rama con el capacitor $C$, que recibe el flujo $F_c(t)$.
  - Una rama serie integrada por el resistor $R_2$ y el inductor $L$, por donde circula el flujo de absorción hormonal $F_s(t)$.

---

## 5. Parámetros del circuito equivalente

| Parámetro | Control: individuo sano | Caso: alteración endocrina simulada |
|---|---:|---:|
| Amplitud del escalón de entrada $V_e$ | 1 V | 1 V |
| $R_1$ | 1 kΩ | 1 kΩ |
| $L$ | 100 mH | 100 mH |
| $R_2$ | 100 kΩ | 1 kΩ |
| $C$ | 1 µF | 1000 µF |

Entre la condición de control y el caso de estudio, la resistencia del órgano diana $R_2$ disminuye cien veces (de $100\text{ k}\Omega$ a $1\text{ k}\Omega$) y la capacitancia de almacenamiento $C$ aumenta mil veces (de $1\ \mu\text{F}$ a $1000\ \mu\text{F}$). Fisiológicamente, esto refleja una menor efectividad sostenida en el tejido blanco acompañada de un secuestro o acumulación excesiva en compartimentos intermedios, lo que reduce la amplitud de respuesta hormonal y vuelve considerablemente más lenta su estabilización.

---

## 6. Análisis matemático

### Leyes de Kirchhoff y ecuaciones constitutivas

Aplicando la ley de voltajes de Kirchhoff (LVK) en la malla principal se obtiene la expresión para el flujo de secreción hormonal:

$$
V_e(t) = R_1 F_e(t) + V_s(t) \implies F_e(t) = \frac{V_e(t) - V_s(t)}{R_1}.
$$

Aplicando la ley de corrientes de Kirchhoff (LCK) en el nodo $V_s(t)$:

$$
F_e(t) = F_s(t) + F_c(t), \qquad \text{donde } F_c(t) = C\frac{dV_s(t)}{dt}.
$$

Por su parte, la caída de voltaje en la rama del órgano diana ($R_2\text{--}L$) está dada por:

$$
V_s(t) = V_{R_2}(t) + V_L(t) = R_2 F_s(t) + L\frac{dF_s(t)}{dt}.
$$

### Sistema de ecuaciones integro-diferenciales (EID)

Despejando las variables de flujo y voltaje en forma integral y diferencial se obtiene el sistema implementado en los subsistemas `Fs(t)_EID` de Simulink:

$$
\begin{aligned}
V_s(t) &= \frac{1}{C}\int \left[F_e(t) - F_s(t)\right] dt, \\[6pt]
F_e(t) &= \frac{1}{R_1}\left(V_e(t) - \frac{1}{C}\int \left[F_e(t) - F_s(t)\right] dt\right), \\[6pt]
F_s(t) &= \frac{1}{R_2}\left(\frac{1}{C}\int \left[F_e(t) - F_s(t)\right] dt - L\frac{dF_s(t)}{dt}\right).
\end{aligned}
$$

### Ecuación diferencial ordinaria de segundo orden

Sustituyendo $F_s(t) = \dfrac{V_e(t) - V_s(t)}{R_1} - C\dfrac{dV_s(t)}{dt}$ y su derivada respecto al tiempo dentro de la ecuación de la rama $R_2\text{--}L$, y multiplicando ambos miembros por $R_1$, se llega a la ecuación diferencial de segundo orden del sistema:

$$
R_1 L C \frac{d^2 V_s(t)}{dt^2} + (R_1 R_2 C + L)\frac{dV_s(t)}{dt} + (R_1 + R_2)V_s(t) = L\frac{dV_e(t)}{dt} + R_2 V_e(t).
$$

### Función de transferencia resultante

Aplicando la transformada de Laplace con condiciones iniciales nulas:

$$
\left[R_1 L C s^2 + (R_1 R_2 C + L)s + (R_1 + R_2)\right]V_s(s) = (Ls + R_2)V_e(s),
$$

de donde se obtiene la función de transferencia general:

$$
\boxed{G(s) = \frac{V_s(s)}{V_e(s)} = \frac{Ls + R_2}{R_1 L C s^2 + (R_1 R_2 C + L)s + (R_1 + R_2)}.}
$$

Al sustituir los valores de cada escenario se obtienen las siguientes expresiones (en forma directa de circuito y en forma mónica normalizada):

| Condición | Función de transferencia directa | Función de transferencia normalizada |
|---|---|---|
| Control | $G_{control}(s)=\dfrac{0.1s + 100000}{0.0001s^2 + 100.1s + 101000}$ | $G_{control}(s)=\dfrac{1000s + 1\times 10^9}{s^2 + 1001000s + 1.01\times 10^9}$ |
| Caso | $G_{caso}(s)=\dfrac{0.1s + 1000}{0.1s^2 + 1000.1s + 2000}$ | $G_{caso}(s)=\dfrac{s + 10000}{s^2 + 10001s + 20000}$ |

---

## 7. Cálculo del error en estado estable

El error estacionario $e(t) = V_e(t) - V_s(t)$ se evaluó ante una entrada **escalón unitario** $V_e(s) = \dfrac{1}{s}$ aplicando el teorema del valor final:

$$
e_{ss} = \lim_{s\to 0} s\,E(s) = \lim_{s\to 0} s\,\frac{1}{s}\left[1 - G(s)\right] = 1 - G(0).
$$

Evaluando la ganancia estática $G(0) = \dfrac{R_2}{R_1 + R_2}$, el error en estado estacionario queda expresado como:

$$
\boxed{e_{ss} = 1 - \frac{R_2}{R_1 + R_2} = \frac{R_1}{R_1 + R_2}.}
$$

| Condición | Ganancia estática $G(0)$ | Error en estado estable $e_{ss}$ | Error porcentual |
|---|---:|---:|---:|
| Control | $0.9901$ | $0.0099\text{ V}$ | $0.99\%$ |
| Caso | $0.5000$ | $0.5000\text{ V}$ | $50.00\%$ |

En el individuo sano (control), la respuesta hormonal efectiva alcanza prácticamente el valor del estímulo ($0.9901\text{ V}$), presentando un error mínimo de $0.99\%$. En cambio, en el caso patológico la salida se estabiliza en apenas $0.50\text{ V}$, lo que genera un error estacionario del $50\%$ que justifica la incorporación de un sistema de control en lazo cerrado.

---

## 8. Evaluación de la estabilidad en lazo abierto

Para determinar la estabilidad en lazo abierto se calculan las raíces del polinomio característico:

$$
R_1 L C s^2 + (R_1 R_2 C + L)s + (R_1 + R_2) = 0.
$$

| Condición | Polo rápido $\lambda_1$ | Polo dominante $\lambda_2$ | Frecuencia natural $\omega_n$ | Factor de amortiguamiento $\zeta$ | Estabilidad |
|---|---:|---:|---:|---:|---|
| Control | $-999989.99\ \mathrm{s}^{-1}$ | $-1010.01\ \mathrm{s}^{-1}$ | $31780.50\ \mathrm{rad/s}$ | $15.75$ | Estable (sobreamortiguado) |
| Caso | $-9999.00\ \mathrm{s}^{-1}$ | $-2.00\ \mathrm{s}^{-1}$ | $141.42\ \mathrm{rad/s}$ | $35.36$ | Estable (sobreamortiguado) |

Ambos sistemas son estables en lazo abierto al poseer dos polos reales negativos. Sin embargo, en el escenario del caso el polo dominante se desplaza de $-1010.01\ \mathrm{s}^{-1}$ a $-2.00\ \mathrm{s}^{-1}$, incrementando la constante de tiempo dominante de $\approx 0.99\text{ ms}$ a $\approx 0.50\text{ s}$ (más de 500 veces más lento) y produciendo un comportamiento fuertemente sobreamortiguado.

---

## 9. Modelo en Simulink y Simscape

Dentro del archivo **`Practica4.slx`** se estructuran los subsistemas **Control** y **Caso**, permitiendo comparar de forma simultánea tres metodologías de modelado: circuito equivalente en Simscape Electrical, función de transferencia y ecuaciones integro-diferenciales.

| Subsistema | Elementos incluidos |
|---|---|
| Control | Circuito RLC en Simscape (`Vs(t): Control CE`), función de transferencia (`Vs(t): Control FT`) y subsistema de ecuaciones integro-diferenciales (`Vs(t): Control EID`) |
| Caso | Circuito RLC en Simscape (`Vs(t): Caso CE`), función de transferencia en lazo abierto (`Vs(t): Caso FT`), subsistema de ecuaciones integro-diferenciales (`Vs(t): Caso EID`) y lazo cerrado con controlador PID (`PID(t): Caso`) que toma como referencia la salida de `Control` |

Los circuitos en Simscape emplean una fuente de voltaje controlada (`Controlled Voltage Source`), resistores ($R_1, R_2$), inductor ($L$), capacitor ($C$), sensor de voltaje (`Voltage Sensor`), referencia eléctrica y convertidores `Simulink-PS` / `PS-Simulink`. Asimismo, los bloques `To Workspace` exportan al espacio de trabajo las señales `Ve`, `Control`, `Caso` y `PID`.

### Señal de entrada empleada en la simulación

La excitación del sistema consiste en un bloque `Step` que genera un **escalón unitario** aplicado en $t = 1\text{ s}$:

$$
V_e(t) = u(t - 1).
$$

| Configuración | Valor |
|---|---:|
| Tipo de señal | Escalón unitario (`Step`) |
| Valor inicial | 0 V |
| Valor final | 1 V |
| Tiempo de aplicación del escalón | 1 s |
| Rango de tiempo de simulación | 0 a 10 s |
| Solucionador y paso máximo | `ode15s`, paso máximo $10^{-2}\text{ s}$ |

---

## 10. Ejecución mediante MATLAB

MATLAB se utiliza como entorno principal para configurar los parámetros, ejecutar el modelo de Simulink y graficar las respuestas temporales del sistema endocrino.

El archivo principal de esta implementación es:

**`Macias23212212.mlx`**

Este cuaderno organiza el desarrollo de la práctica, ejecuta la simulación de `Practica4.slx` y genera las gráficas comparativas entre el individuo sano, el caso patológico en lazo abierto y el caso compensado.

La versión exportada del trabajo se encuentra disponible en:

**`Macias23212212.pdf`**

### Actividades realizadas

1. Definición de los parámetros eléctricos y fisiológicos para Control y Caso.
2. Ejecución de la simulación en Simulink (`Practica4.slx`) durante 10 s.
3. Extracción de las señales `Ve`, `Control`, `Caso` y `PID` desde el espacio de trabajo.
4. Generación de gráficas comparativas y exportación de resultados a PDF.

---

## 11. Diseño y ajuste del controlador PID

Para eliminar el error estacionario del $50\%$ en el escenario patológico y lograr que su respuesta siga el comportamiento del individuo sano, se implementó el bloque `PID Controller1` en configuración **PID** de tiempo continuo, estructura paralela y con filtro derivativo de primer orden ($N$).

La señal de error se define a partir de la respuesta de referencia del control:

$$
e(t) = V_{s,control}(t) - V_{s,PID}(t).
$$

La función de transferencia del controlador PID con filtro derivativo es:

$$
K(s) = k_P + \frac{k_I}{s} + k_D\frac{Ns}{s + N}.
$$

De esta manera, la función de transferencia de seguimiento en lazo cerrado $T(s)$ y la salida controlada $V_{s,PID}(s)$ se expresan como:

$$
T(s) = \frac{K(s)G_{caso}(s)}{1 + K(s)G_{caso}(s)}, \qquad V_{s,PID}(s) = T(s)G_{control}(s)V_e(s).
$$

### Ganancias configuradas en el controlador PID

| Parámetro | Valor almacenado en el modelo de Simulink (`Practica4.slx`) |
|---|---:|
| Proporcional ($k_P$) | `1328.24605947858` |
| Integral ($k_I$) | `326720.915808775` |
| Derivativo ($k_D$) | `0.179714593708974` |
| Coeficiente de filtro derivativo ($N$) | `5077.07776653047` |
| Estructura y dominio | PID paralelo, tiempo continuo |

### Desempeño del sistema en lazo cerrado

| Indicador | Valor calculado para $T(s)$ ante escalón |
|---|---:|
| Tiempo de subida (10 % – 90 %) | 0.00131 s (1.31 ms) |
| Tiempo de establecimiento (banda del 2 %) | 0.00995 s (9.95 ms) |
| Sobreimpulso | 10.14 % |
| Valor pico | 1.10 |
| Polos en lazo cerrado | $-9998.54,\ -6225.52,\ -729.27,\ -365.42\ \mathrm{s}^{-1}$ |
| Estabilidad del sistema en lazo cerrado | Estable |

La acción integral ($k_I$) elimina por completo el error en estado estacionario, mientras que las acciones proporcional ($k_P$) y derivativa filtrada ($k_D, N$) aceleran la respuesta transitoria de la planta del caso para acoplarse rápidamente a la curva de referencia del control.

---

## 12. Desarrollo complementario en Python

Python se emplea como herramienta computacional alternativa para validar de manera independiente las funciones de transferencia, las respuestas al escalón en lazo abierto y el desempeño del controlador PID en lazo cerrado.

El programa correspondiente es:

**`Practica_4.py`**

El documento **`Caso_python.pdf`** contiene el respaldo gráfico y documental de esta implementación.

### Actividades realizadas

1. Definición de los parámetros del circuito RLC para Control y Caso.
2. Construcción de las funciones de transferencia en lazo abierto y en lazo cerrado mediante bibliotecas de control y simulación numérica (`numpy`, `scipy`, `control`, `matplotlib`).
3. Simulación de la respuesta al escalón $u(t-1)$ en el intervalo de $0$ a $10\text{ s}$.
4. Generación de gráficas comparativas para contrastar los resultados con MATLAB y Simulink.

---

## 13. Representación biológica en BioRender

La siguiente ilustración, elaborada en BioRender, esquematiza el eje endocrino estudiado (glándula secretora, torrente sanguíneo, compartimento de almacenamiento y órgano diana) junto con su analogía en el circuito eléctrico RLC de segundo orden.

![Representación del sistema endocrino y su modelo RLC](BioRenderEndocrino.png)

**Figura 1.** Representación fisiológica del sistema endocrino y su circuito eléctrico RLC equivalente. Elaboración propia mediante BioRender.

| Estructura o proceso fisiológico | Elemento del modelo RLC |
|---|---|
| Estímulo inicial y secreción glandular (hipófisis / hipotálamo) | $V_e(t)$ |
| Resistencia y pérdida durante la difusión en el torrente sanguíneo | $R_1$ |
| Almacenamiento temporal de hormonas en tejidos intermedios | $C$ |
| Resistencia al cambio hormonal en el órgano diana (suprarrenal / tiroides) | $R_2$ |
| Inercia biológica de la respuesta del órgano diana | $L$ |
| Flujo de secreción hormonal y flujo de absorción en órgano diana | $F_e(t)$ y $F_s(t)$ |
| Respuesta hormonal efectiva observada en el organismo | $V_s(t)$ |

---

## 14. Discusión final

El modelado del sistema endocrino mediante un circuito RLC de segundo orden permitió verificar la equivalencia exacta entre tres formulaciones distintas: el circuito físico en Simscape Electrical, la función de transferencia de segundo orden y el sistema de ecuaciones integro-diferenciales. En los tres enfoques se obtuvieron curvas idénticas tanto para el individuo sano como para el caso patológico.

En el análisis en lazo abierto, ambos escenarios resultaron estables al contar con polos reales negativos; sin embargo, la disminución de $R_2$ de $100\text{ k}\Omega$ a $1\text{ k}\Omega$ y el aumento de $C$ de $1\ \mu\text{F}$ a $1000\ \mu\text{F}$ degradaron notablemente el desempeño del caso, reduciendo la ganancia estacionaria de $0.9901$ a $0.5000$ (error del $50\%$) y desplazando el polo dominante de $-1010.01\ \mathrm{s}^{-1}$ a $-2.00\ \mathrm{s}^{-1}$.

Al incorporar el controlador PID en lazo cerrado tomando la respuesta sana como referencia, el sistema compensado logró eliminar el error en estado estacionario y estabilizarse en menos de $10\text{ ms}$ tras aplicarse el escalón en $t = 1\text{ s}$, reproduciendo fielmente la dinámica del control. Finalmente, la consistencia entre las simulaciones de MATLAB/Simulink y Python confirma la validez numérica del modelo implementado, recordando que constituye una simplificación matemática útil para el análisis de sistemas de control fisiológico.

---

## 15. Secuencia de trabajo

```mermaid
flowchart TD
    A[Sistema endocrino fisiológico] --> B[Circuito eléctrico RLC de 2.º orden]
    B --> C[Ecuaciones integro-diferenciales y EDO]
    C --> D[Función de transferencia G_s]
    D --> E[Análisis de polos y error en estado estable]
    B --> F[Modelado en Simscape Electrical]
    C --> G[Subsistemas EID en Simulink]
    D --> H[Bloques de Transferencia y diseño PID]
    F --> I[Simulación en MATLAB / Simulink]
    G --> I
    H --> I
    D --> J[Implementación numérica en Python]
    H --> J
    I --> K[Comparación de resultados]
    J --> K
    A --> L[Ilustración biológica en BioRender]
    K --> M[Documentación final]
    L --> M

---
## 16. Requisitos para reproducir la práctica

### Programas y recursos necesarios

- MATLAB y Simulink.
- Simscape y los componentes eléctricos requeridos por el circuito.
- Las herramientas de ajuste de controladores necesarias para abrir y utilizar PID Tuner.
- Python y las bibliotecas que se importen en la versión definitiva del programa.
- BioRender o, en su defecto, la imagen exportada del diagrama biológico.

### Pasos de ejecución

1. Obtener los materiales que integran el repositorio.
2. Colocar el modelo de Simulink (`.slx`) y el cuaderno de MATLAB (`.mlx`) dentro de la misma carpeta de trabajo.
3. Abrir el cuaderno y comprobar los datos definidos para la simulación.
4. Revisar que los parámetros de control y caso coincidan con los valores presentados en este documento.
5. Confirmar qué conjunto de ganancias PI se utilizará en la reproducción.
6. Ejecutar el cuaderno. Durante este proceso se abrirá el modelo de Simulink y se realizará una simulación de 10 s con el solucionador `ode15s` y un paso máximo de $10^{-3}$ s. Cuando el cuaderno solicite el modelo, indicar el nombre base correspondiente al archivo `.slx` disponible.
7. Comprobar que se hayan generado las variables `X.t`, `X.F`, `X.Fsx`, `X.Fsy` y `X.PID`.
8. Crear la gráfica con la función `plotsignals` y exportarla como documento PDF.
9. Ejecutar el programa de Python con el mismo pulso, los mismos parámetros y las ganancias PI seleccionadas. Guardar la figura producida.
10. Comparar las gráficas de ambas plataformas y añadir al repositorio la ilustración de BioRender y las evidencias restantes.


---

## 17. Fuentes consultadas

Las siguientes referencias corresponden al material bibliográfico señalado en el instructivo de la práctica:

1. M. C. Khoo, *Physiological Control Systems: Analysis, Simulation, and Estimation*, 2nd ed., IEEE Press, 2018.
2. F. C. Hoppensteadt y C. S. Peskin, *Modeling and Simulation in Medicine and the Life Sciences*, Springer.
3. J. E. Hall, *Guyton and Hall Textbook of Medical Physiology*, 14th ed., Elsevier, 2021.
4. K. Ogata, *Ingeniería de Control Moderna*, 5.ª ed., Pearson Educación, 2010.
5. N. S. Nise, *Control Systems Engineering*, 8th ed., John Wiley & Sons, 2020.
6. P. A. Valle, *Syllabus para Modelado de Sistemas Fisiológicos*, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B. C., México, 2026. Sección 5.5: «Práctica: Modelado y control del sistema musculoesquelético».
7. Tecnológico Nacional de México, *Programa de estudio de la asignatura Modelado de Sistemas Fisiológicos, IBF-1020*.


---
