# Investigación de operaciones II

## Tomas de decisiones bajo certidumbre 
### Proceso de jerarquia analitica
* **Alternativas:** son las opciones para la toma de decisiones
* **Criterios:** son los atributos que rodean a las alternativas 
* **Pesos:** son los niveles de importancia asignados a los criterios y alternativas 

Escala numerica para determinar los pesos:

| Escala numérica | Significado |
|-----------------|-------------|
|$a_{ij}=1$      | significa que son de igual importancia|
|$a_{ij}=3$      | significa que i es debilmente mas importante que j |
|$a_{ij}=5$| significa que i es fuertemente mas importante j|
|$a_{ij}=7$| significa que i es muy fuertemente mas importate que j|
|$a_{ij}=9$| significa que i es extremadamente más importante que j|

Los valores 2,4,6,8 se interpretan según corresponda.
> NOTA: La consistencia de un juicio en un PJA (proceso de jerarquia analitica) implica que si $a_{ij}=k$ entonces $a_{ij}=1/k$

> NOTA: Además siempre se tiene que $a_{ii}=1$ porque se califica el elemento consigo mismo

### *Normalización de matrices de comparación*
La normalización sirve para estandarizar los pesos en valores que varian entre 0 y 1, de esta manera. Se tendrá una idea cuantitativa más clara del nivel de importancia asignado por el <u>tomador de decisiones</u>

El proceso requiere dividir los **elementos individuales** de cada columna **entre** **la suma de la columna**.

### *Calculo de pesos relativos*
Para realizar el calculo, debemos **promediar los pesos relativos de las filas**  de la <u>matriz NORMALIZADA</u>

### ANALISIS DE CONSISTENCIA 
Una matriz es consistente si las columnas de su matriz NORMALIZADA son iguales. Caso contrario la matriz es NO consistente. 

Las matrices 2x2 siempre son consistentes

Decimos que la decisión es consistente cuando todas sus matrices de comparación son consistentes o **inconsistentes tolerables**. 

Cuando la matriz es NO consistente se debe realizar lo siguiente y calcular la razón de consistencia **(RC)**

FORMULA: 

$$\sum A*W = n_{\text{max}}, \ n_{\text{max}} \geq n $$

donde: 
* A: es la matriz de comparación (original)
* W: es el vector de pesos (la fila de pesos)
* n: dimensión de vector
* nmax: la suma de los elementos del vector resultante A.W

CALCULO DE LA RAZÓN DE CONSISTENCIA
* CI: indice de consistencia 

donde: 
```
CI= (nmax-n)/(n-1)
```
* RI: Razón de consistencia aleatoria 

donde:
```
RI= (1.98*(n-2))/(n) 
```
* RC: razón de consistencia 

Donde:
````
RC = CI/RI
````
Se dice que el nivel de **inconsistencia es tolerable** si es que **_RC_<0,1**

### EXCEL 
Matrices a ser representados:
* MATRIZ DE COMPARACIÓN DE CRITERIOS 
* MATRIZ DE COMPARACIÓN DE ALTERNATIVAS SEGÚN CRITERIO 1,2,..N (la matriz se hace según las alternativas)
* Luego preguntar si es consitente o no

### **Matriz de comparacion de criterio**

|        |      |       |
|--------|------|-------|
| Criterios | CRITERIO 1 | CRITERIO 2
| CRITERIO 1||
| CRITERIO 2||
| TOTAL | |

### **Matriz de comparación de alternativas según CRITERIO 1**
|        |      |       |        |
|--------|------|-------|--------|
|| A | B| C|
| A||
| B||
| C|| 
| TOTAL | |

### **Matriz de comparación de alternativas según CRITERIO 2**
|        |      |       |        |
|--------|------|-------|--------|
|| A | B| C|
| A||
| B||
| C|| 
| TOTAL | |

### **Cuadro para analisis**
|   |   |   |                    |  |   |     |
|---|---|---|--------------------|--|--|--|
|Criterios  | Pesos por criterios  | Alternativas  | Pesos según CRITERIO 1 | Pesos según CRITERIO 2 | ......| Pesos según CRITERIO 3
|CRITERIO 1|||||
|CRITERIO 2|||||
|.....||||||
|CRITERIO N||||| 

### **Pesos Ponderados Finales**

*Formula:* pesoCriterio1*pesoSegunCRITERIO1 + pesoCriterio2 * pesoSegunCRITERIO2 + ... + pesoCriterioN * pesoSegunCRITERION

||||
|-|-|-|
|Alternativa 1|PESO FINAL 1|||
|Alternativa 2|PESO FINAL 2|||
|....||||
|Alternativa N|PESO FINAL N|||

### **ANALISIS DE INCONSISTENCIA**
* A_{se especifica la matriz de comparación} : matriz de comparación 
* $Pesos$ : vector de pesos (matriz de 3x1)
* $MMULT$: MULTIPLICACION DE MATRICES
* recordar (matriz de comparación) = significa la matriz original

|               |               |             |  
|---------------|---------------|-------------|
|Analisis de inconsistencia|    |             |
**A_{se especifica la matriz de comparación} * PesosDeEsaMatriz**| MMULT(matriz1, matriz2)
|sacar nmax = suma_del_analisis)|||
|sacar n = cantidad de filas del vector pesos segun La MATRIZ INCONSISTENTE|||
|sacar (indice consistencia)CI= (nmax-n)/(n-1)|||
|sacar (razon de consistencia aleatoria)RI=(1.98*(n-2))/(n) |||
|Calcular (razon de consistencia aleatoria)RC = CI/RI|||

$recordar: $
Se dice que el nivel de **inconsistencia es tolerable** si es que **_RC_<0,1**



## Toma de decisiones bajo incertidumbre

Toma de decisiones baho incertidumbre implica acciones alternativas cuyas restricciones dependen de los estados de la naturalieza (aleatorios).

|      |       |      |     |       |
|------|-------|------|-----|-------|
|Alternativas/estados| $S_1$| $S_2$|....|$S_n$|
|$a_{1}$|$v_{11}$|$v_{12}$|....|$v_{11}$| 
|$a_{2}$|$v_{21}$|$v_{22}$|....|$v_{2n}$| 
|...|...|...|....|....| 
|$a_{m}$|$v_{m1}$|$v_{m2}$|....|$v_{mn}$| 

- $a_{1}$ : alternarivas de decisión
- $S_{j}$ : estados de la natruraleza
- $V_{ij}$ : retribución de la alternativa i bajo el estado j

La probabilidad de ocurrencia de cada estado de la naturaleza no se conoce o no se puede determinar. La decisión se toma según "criterios" esto vuelve a la situación, una decisión "subjetiva"

### **1. Criterio de LAPLACE**
Probabilidad de ocurrencia de los estados de la naturaleza es igual para todos (los estados son igualmente probables).

Obs: **n** es el nro de columnas

* Si la matriz de retribución está ##**basada en GANANCIAS o ingresos**
$$max_{a_i}\{1/n \sum^{n}_{j=1}v(a_i,s_j)\}$$

En excel:

$\text{Elegir el maximo:}$

$${1/n * suma(DeCadaFila)}$$

* Si la matriz de retribución está ##**basada en COSTOS o perdidas**
$$min_{a_j}\{1/n \sum^{n}_{j=1} v(a_i,s_j)\}$$

En excel:

$\text{Elegir el minimo:}$

$${1/n * suma(DeCadaFila)}$$

### **2. Criterio OPTIMISTA**
El mejor de los resultados posibles
* Matriz de retribucion basada en ##**ganancias o utilidades** 

$\text{Maximax}$
$$max_{ai}\{max_{sj} v_{ij}\}$$

(El maximo de los maximos de alternativas)

En excel:

$\text{Elegir el maximo entre:}$

$$max\{EntreLasFilas\}$$

* Matriz de retribución ##**basada en costos o gastos** 

$\text{Minimin}$

$$min_{ai}\{min_{sj}v_{ij}\}$$

En excel:

$\text{Elegir el minimo entre:}$

$$min\{EntreLasFilas\}$$

### **3. Criterio PESIMISTA o CONSERVADOR**
La major decisión entre las peores condiciones posibles (la menos peor)
* Matriz de retribución **basada en ganancias** 
$$Maximin: max_{ai}\{min_{sj}v_{ij}\}$$

(el maximo entre los minimos alternativas)
* Matriz de retribuciones **basadas en costos**
$$Minimax: min_{ai}\{max_{sj}v_{ij}\}$$

(el minimo entre las maximas alternativas)

### 4. Criterio de SAVAGE
Modera el grado de pesimismo y el impacto negtivo de una posible mala decisión.  “modera” el grado de conservadurismo

$
r(a_i, s_j) = 
\begin{cases} 
v(a_i, s_j) - \min\{v(a_k, s_j)\}, & \text{si } v \text{ es una pérdida} \\
\max\{v(a_k, s_j)\} - v(a_i, s_j), & \text{si } v \text{ es una ganancia}
\end{cases}
$

Es decir (en exel):

$\text{Para pérdida: } [CELDA]-MIN(\text{COLUMNA}_{celda})$
$\text{Para ganancia: } MAX(\text{COLUMNA}_{celda})-[CELDA])$

Es importante tener en cuenta que la matriz de pérdida o 
lamento es una matriz de COSTO de oportunidad, por lo tanto 
los datos que contiene representan los costos de no haber 
contado con el mejor escenario, independientemente de que la 
matriz original contenga ganancias o costos. 

> Luego hacer una columna de Minimax (Savage) si es costo (matriz de arrepentimiento).

Siempre hacer **minimax** (indiferente si es costo o ganancias la matriz)
El minimo entre los maximos de la alternativa.

### 5. Criterio de Hurwicz
Rerpresenta diferentes actitutes entre la mas pesimista y la mas optimista aplicando un índice de optimismo $0\leq\alpha\leq1$
* Matriz de ganancias
$$max_{ai}\{\alpha \ max_{sj} v_{ij}+(1-\alpha)min_{sj}v_{ij}\}$$

* Matriz de costos
$$min_{ai}\{\alpha \ min_{sj}v_{ij}+ (1-\alpha)max_{sj}v_{ij}\}$$


Para excel:

$->\text{Matriz de ganancias:}$

$\text{Al final se elige entre el maximo:}$

$\alpha \ max\{EntreEsaFila\}+(1-\alpha)min\{EntreEsaFila\}$

$->\text{Matriz de costos:}$

$\text{Al final se elige entre el minimo:}$

$\alpha \ min\{EntreEsaFila\}+(1-\alpha)max\{EntreEsaFila\}$



$\text{Decisión según cada criterio:}$

1. La decisión según el criterio de Laplace es ... [La fila donde seleccioné]

2. La decisión según el criterio optimista es ... [La fila donde seleccioné]

3. La decisión según el criterio pesimista es ... [La fila donde seleccioné]

4. La decisión según el criterio savage es ... [La fila donde seleccioné]

5. La decisión según el criterio Hurwicz con indice de optimismo = 0,5 es ... [La fila donde seleccioné]

6. La decisión según el criterio Hurwicz con indice de optimismo = 0,75 es ... [La fila donde seleccioné]

7. La decisión según el criterio Hurwicz con indice de optimismo = 0,25 es ... [La fila donde seleccioné]


## Toma de decisiones bajo riesgo
Cuando tienes que elegir entre diferentes opciones sabiendo que cada una tiene una cierta posibilidad de éxito o fracaso. Cuando se tenga **probabilidades.**

Las decisiones se toman bajo el  $\text{criterio de valor esperado}$

$VE_{i}$: Valor esperado 

$P_{j}$: Probabilidad del estado de la naturaleza

**Formula:** 
$$\sum VE_{i}*P_{j}$$

Los ejercicios suelen presentarse como:

$
\text{Alternativas} = 
\begin{cases} 
\text{Invertir en A} 
\\
\text{Invertir en B}
\end{cases}
$

$
\text{Estados de la naturalez} = 
\begin{cases} 
\text{Mercado Favorable (MF)} 
\\
\text{Mercado Desfavorable (MD)}
\end{cases}
$

$\text{P(MF)=(probabilidad en el mercado alcista o favorable)}$

$\text{P(MD)=(probabilidad en el mercado bajista o desfavorable)}$

$\text{1. Elaborar una matriz de retribuciones}$

$\text{2. Aplicar la formula}$

Ejemplo:

Supongamos que se desea invertir $10,000 en el mercado de valores adquiriendo acciones en una de dos compañías: A y B. Las acciones de la 
compañía A, aún cuando son riesgosas, podrían redituar 50% durante el 
siguiente año, en un mercado favorable. Si las condiciones del mercado de 
valores no son favorables (es decir, un mercado “bajista”) las acciones 
pueden perder 20% de su valor. La compañía B proporciona inversiones 
seguras con 15% de rendimiento en un mercado “alcista” y de sólo 5% en un 
mercado “bajista”. Todas las publicaciones que se ha consultado pronostican una probabilidad de 60% de un mercado “alcista” y 40% de un mercado 
“bajista”. ¿Cómo se debe invertir el dinero?   
a) Construye la matriz de retribuciones del problema incluyendo la 
información de las probabilidades.  
b) Resuelve el problema por el Criterio del Valor Esperado (VE). 


$\text{capital=10000}$

$
\text{Alternativas} = 
\begin{cases} 
\text{Invertir en A} 
\\
\text{Invertir en B}
\end{cases}
$

$
\text{Estados de la naturaleza} = 
\begin{cases} 
\text{Mercado Favorable (MF)} 
\\
\text{Mercado desfavorable (MD)}
\end{cases}
$

$\text{P(MF)=0.6}$

$\text{P(MD)=0.4}$

a) 
Matriz de retribuciones
|   |   |    |
|---|---|----|
|Alternativas/Estados| MF | MD|
|Invertir en A| 5000| -2000|
|Invertir en B| 1500| 500|
|||

b) Resolución por Criterio del valor esperado (VE)

$\sum VE_{i}*P_{j}$

$VE(A)= 5000*0.6 + (-2000)*0.4 = 2200$

$VE(B)= 1500*0.6 + (500)*0.4 = 1100$

El que genere más inversión: 

$VE*= max\{2200,1100\}=2200$ entonces se debe invertir en A


## Árbol de decisión

- **Nodo Circular:** representa un punto de donde se desprenden estados de la naturaleza 
- **Nodo Cuadrangular:** representa un punto de donde se desprenden alternativas (nodo de decisión)

Ejemplo de las inversiones:

````mermaid
graph LR
    A[2200] -->|Inversion A| B((VE 2200))
    A -->|Inversion B| C((VE 1100))
    B -->|MF = 0.6| D[5000] 
    B -->|MD = 0.4| F[-2000]
    C -->|MF = 0.6| E[1500]
    C -->|MD = 0.4| H[500]

````

$\text{Valor esperado con información perfecta (VECIP)}$

Formula:

$\text{VECIP}= \sum (\text{Mejor pago bajo el estudio j})*ProbApriori$

$ \ \ \  \   \  \   \  \ \ \ \ \    \    \ = 5000*0.6+500*0.4$

> Mejor pago tanto del mercado favorable como desfavorable

$\text{VE=2200}$


$\text{Valor Esperado de la Información Perfecta (VEIP)}$

$VEIP = VECIP - 2200$

Estamos dispuestos a pagar hasta 1000 por la información perfecta

$\text{Valor esperado de la información muestral}\\$
$\text{VEIM = VECIM + CostoDelEstudio - VESIM}\\$

$\text{VECIM: Valore esperado con información muestral: valor que se consigue sin estudio - a priori resultado}\\$
$\text{VESIM: Valore esperado sin información muestral: valor que se consigue con estudio - a posteriori resultado}\\$

$\text{Posibles resultados de estudio}\\$
A favor - en contra

Por ejemplo:

90% de probabilidad de invertir (a favor) en un mercado favorable

se reduce 50% en un mercado bajista

-
$\text{P(A FAVOR/ MF) = 0.9 Exito MF}$

$\text{P(En contra/ MF) = 0.1 Fracaso MF}$

$\text{P(A FAVOR/ MD) = 0.5 Exito MF}$

$\text{P(En contra/ MD) = 0.5 Exito MF}$

-
$\text{Probabilidad a Priori}$

Se puede realizar una investigación especifica (información muestral) (estudio de mercado)

````mermaid
graph TD
    A[Provee probabilidad condicionales]
    A --> B[Probabilidad Conjuntos]
    A --> C[Probabilidad Absoluta]
    B --> D[Probabilidad a Posteriori]
    C --> D[Probabilidad a Posteriori]
````

$V_{1}=\text{a favor}$

$m_{1}=\text{MF}$

$
\text{Probabilidad condicionales para MF} = 
\begin{cases} 
\text{P(V1 | M1)} 
\\
\text{P(V2 | M1)} 
\end{cases}
$

$
\text{Probabilidad condicionales para MD} = 
\begin{cases} 
\text{P(V1 | M2)} 
\\
\text{P(V2 | M2)} 
\end{cases}
$

**Probabilidades Conjuntas**

$\text{P(Vj | mi)*P(mi)} $

**Probabilidades absolutas**

$\text{P(Vj)=}\sum P\text{(Vj | mi)*P(mi)} $

****
| |
|-|
|Definición de variables|
|$v_1$=voto a favor|
|$v_2$=voto en contra|
|$m_1$=mercado favorable|
|$m_2$=mercado desfavorable|

|||
|-|-|
|P(m1)|0,6|
|P(m2)|0,4|

- Sacar:

$\text{Probabilidad a priori: }$ Probabildidades iniciales


$\text{Probabilidades condicionales: }$ son la probabilidad de que algo suceda bajo la condición de que ya sabemos que otra cosa ha sucedido. Por ejemplo "a favor o en contra de invertir"

$\text{P(v1|m1)} \ \text{voto a favor en mercado favorable}\\$ 
$\text{P(v2|m1)} \ \text{voto en contra en mercado favorable}\\$
$\text{P(v1|m2)} \ \text{voto a favor en mercado desfavorable}\\$
$\text{P(v2|m2)} \ \text{voto en contra en mercado desfavorable}\\$



$\text{Probabilidades conjuntas: }$ Combinación de eventos y se usa para detectar el valor esperado

$\text{P(v1|m1)P(m1)}\\$
$\text{P(v2|m1)P(m1)}\\$
$\text{P(v1|m2)P(m2)}\\$
$\text{P(v2|m2)P(m2)}\\$


$\text{Probabilidades absolutas: }$ sumatoria de las probabilidades abasolutas teniendo en cuenta los votos a favor (v1) y en contra (v2)

$P(v1)=\text{P(v1|m1)P(m1)}+\text{P(v1|m2)P(m2)}\\$ 
$P(v2)=\text{P(v2|m1)P(m1)}+\text{P(v2|m2)P(m2)}\\$

$\text{Probabilidades a posteriori:}\\$ 
$\text{P(m1|v1)= probabilidadesConjuntas(P(m1))/probabilidadesAbs(P(v1))}\\$
$\text{P(m2|v1)= probabilidadesConjuntas(P(m2))/probabilidadesAbs(P(v1))} \\$
$\text{P(m1|v2)= probabilidadesConjuntas(P(m1))/probabilidadesAbs(P(v2))} \\$
$\text{P(m2|v2)= probabilidadesConjuntas(P(m2))/probabilidadesAbs(P(v2))} \\$

**** 
Posibles preguntas:

$\text{Según los resultados globales es conveniente realizar el esudio de mercado porque?}\\$
$\text{ * Si conviene porque el rvalor esperado con estudio es mayor que sin estudio}\\$
$\text{ * No conviene porque la diferencia entre los valores esperados no es significativo como para hacer todo un trabajo de implementacipon de un estudio de mercado}$

## Métodos Cuantitativos
$\text{Tendencia Estacional}$

### Primer método cuantitativo

**Promedio móvil simple (PMS):** Para abarcar todos los cuatro trismestres del año promediar a apartir del tercer trimestre del primer año, hasta el penultimo año.

Ejemplo: 

Si me da pide $\text{PMS(3)}$ entonces (agarrar los tres primeros y promediar - ubiracarse entonces una celda abajo):
|||||
|-|-|-|-|
|Mes|Ventas|PMS(3)|E.Abs.(3)
1|20||
2|24||
3|27||
4|31|=PROMEDIO(20;24;37)| =ABS(El primer PMS(3)-el valor de ventas real)
5|37||
6|47||
7|53||
8|62||
9|54||
10|36||
11|32||
12|29|Arrastrar hasta acá|arrastrar hasta el mes de dic. el de enero no tendrá error absoluto por no tener valor real|
13||si quiero tener el PMS del mes de enero del año sgte|
|||DMA||

**DMA(Desviación media abosuluta)=** Promedio de la columna de errores abs

**E.ABS.** (Error Absoluto)=Ubicarse en la celda donde empezó el PMS y calcular la diferencia entre (PMS-Ventas)

**VIDEO DE LA PROFE**

(conclusión que sacó)

a) Como la DMA del PMS de 3 periodos es menor que la DMA del PMS de 4 periodos, entonces el método más exacto para esta esta serie de datos es hasta ahora el PMS de tres
periodos


**Promedio móvil centrado:** Dividir de a dos hasta el penultimo

$\text{Valor Indice: Ventas reales/promedio movil centrado}$

### Segundo método cuantitativo

**Promedio movil ponderado:**
Las mas recientes tienen mas valor que las anteriores, mientras mas se alejan los valores sus coef. de pond. se vuelven mas pequeños 

$y_7=0.5*y_6+0.3*y_5+0.1*y_4$


Por ejemplo si queremos hacer un PMP(3) necesitamos 3 coeficientes de ponderación alpha2, alpha1, alpha0. Calculo:

||||
|-|-|-|
|Coef.de pond.|||
|alpha2|0.167||
|alpha1|0.333||
|alpha0|0.5||

Como es el ejemplo PMP(3) voy a la cuarta celda, entonces se calcula (FIJAR LOS ALPHAS ANTES DE ARRASTRAR):

||||
|-|-|-|
|PMP(3)|E.Abs(PMP)|
|||
|||
|||
|=alpha0 * ventas(marzo)+alpha1 * ventas(febrero) + alpha2 * ventas(enero)| =abs(venta - PMP(3))|
|....|...|
|DMA| =PROMEDIO(excepto con el valor que no se agregó en ventas)


Recordar: no arrastrar hasta diciembre donde no tiene valor real.

**Conclusión parcial del vídeo de la profe:**

b) como la DMA del PMP del 3 periodo es menor que el DMA del PMS de 3 periodos, entonces el método más exacto para esta serie de datos es hasta ahora el periodo PMP de 3 periodos 

### Tercer método cuantitativo

**Suavizado exponencial:** Resuelve el problema filosofico porque le da mayor importancia a los valores mas recientes y menos importancia cuando se va acercando para el cual quiero sacar el pronostico, tambien resuelve el problema operacional porque no necesitamos almacenamiento muy grande cuando tenemos grandes cantidades de datos porque en cada iteración va pisando los datos anteriores y es como va absorviendo la información de estos datos. Funciona bien cuando tenemos series muy grandes de datos

Requiere una estimación inicial (si el problema no da, tomar el primer valor de ventas como estimación inicial). Se puede poner en el cuadro como el primer valor de ventas. Entonces a partir del periodo dos implementamos la formula;

$y_{(t+1)}=alpha*y_t+(1-alpha)*y_{t}$

|||
|-|-|
|Coef. de pond.||
|alpha|0.5|

recordar: alpha fijar,calcular desde el periodo donde calculamos la formula del suavizado 

|||
|-|-|
|Suav. Exp.|E. Abs (suav. exp.)|
|20|
|=$alpha$*ventas(enero)+(1-$alpha$)*(20(el 20 de la celda anterior))|  =ABS(venta-Suav. Exp)
|....|
|arrastrar hasta el ultimo||
|DMA | =PROMEDIO(ARRASTAR HASTA EL PENULTIMO SI NO SE TIENE VALOR REAL)|

C) como el suavizado exponencial es menor que el DMA del PMP de 3 periodos, entonces el método más exacto para esta serie de datos es el Suavizado Exponencial

D) el metodo que menos se ajusta a la serie dada es el PMS de 4 periodos (porque tiene el valor mas alto)

Todos fueron observaciones simples

### PRONOSTICOS CAUSALES
Valores que dependen de causas - Regresión lineal


||||
|-|-|-|
|Estudiante|Hs de estudio| Calificacion | 
|1|40|4|
|2|42|4|
|3|30|3|
|4|35|3|
|5|25|1|
|6|28|2|
|7|32|3|
|8|35|3|
|9|40|4|
|10|42|4|

Posibles preguntas:

a) Identifica e indica la variable dependiente y la independiente.

Como se puede establecer que la calificación depende de las horas de estudio entonces la variable dependiente sería y=calificación y la variable independiente ser x= hs de estudio

b) Realiza un gráfico de dispersión de los datos e indica la recta de ajuste.

Seleccionar las variables independiente y dependiente. Insertar grafico de disperción ir luego a la opción con simbolo de más (+) seleccionar linea de tendencia

c) Estima la recta de regresión lineal simple por mínimos cuadrados

Estimar la recta de regresión lineal en el gráfico yendo a linea de tendencia luego en el [>] seleccionar más opciones, luego ir a presentar la ecuac. del gráfico

d) Realiza la predicción de calificación final de un estudiante que dedica 24 horas de estudio de la materia

Predicción para 24 hs de estudio, o sea x=24
reemplazar en la formular que te dió el gráfico.

e) Calcula el coeficiente de correlación lineal e interpreta su resultado.

EXCEL TIENE UNA FUNCIÓN

$\text{COEF.DE.CORREL(matrizhsdeEstudio;matrizCalif)}$

sin titulos obviamente en la formula de excel

Coeficiente de correlación si
* Toma valores cercanos a -1 es fuerte e inversa
* Toma valores carcanos a 1 es fuerte y directa
* Toma valores cercanos a 0 es debil


Rpta de la profe: como el coeficiente de relación salió 0.94 se aprecia una correlación fuerte entre las variables


f) Calcula el coeficiente de determinación e interpreta su resultado.

El coeficiente de deteminación es $r^2$ indica el porcentaje de la variación de la variable dependiente y que se explica por el modelo de ajuste

para hallar poner entre las opciones presentar R cuadrado del gráfico y listo.

Para responder si $r^2 = 0.8867$, El valor del coeficiente de determinación indica que el 88.67% de la variabilidad de las calificaciones puede ser explicada por la recta de ecucación (poner la ecuación) tomando como variable causal a las (completar con el nombre de las variables independientes)
 


 si da una función $y=c_{1}.e^{c_{2}x}$

Hacer cambio de variable: 
* Usando logaritmos bajar los exponentes:
$ln(y)=ln(c_1)+ln(e^{c_{2}x})$
* Cambio de variables:

$z=ln(y)$  
$k=ln(c_1)$

* la función queda linealizada: $z=k+c_{2}x$ 

Agregar una nueva columna a la tabla: $z=ln(y)$ y crear una grafica de dispersión para luego sacar los valores de la ecuación

------------------------------------------------------------------------------------------------

## TEORÍA DE COLAS
### Por ejemplo:
Para todo menciona una tasa de llegada de 50000 productos al año, y los días tienen 8 horas y los años 240 días.

Si por ejemplo dice que existe una Sección A que verifica un producto A con **una máquina** que es capaz de procesar 220 productos al día.
```
    (M/M/1):(DG/infinito/infinito): 
```  
*Calculos:*
```
- PRODUCTO A
Para lambda o tasa media de llegada:
    tiempo: 8 hs y 240 días: 240.333
    Convierto en cuanto es en cada día: 240.333
    Tasa media de llegadas: 50000 productos/año: 50000/240.33: 208.04
Para mu:
    mu: productos_al_día*nro_de_servidores
    mu: 220*1: 220
```

*Dentro del POM QM:*
```
    Arrival rate (lambda) (tasa media de llegada): 208
    Service rate (mu): 220
    Number of servers: 1
```
|Parameter	|Value|Parameter|Value|	Hours (based on 8 hr day)|	Hours (based on 24 hr day)|
|-----------|-----|---------|-----|--------------------------|----------------------------|
M/M/1  (exponential service times)||Average server utilization|	,95		
Arrival rate(lambda)|	208		|Average number in the queue(Lq)|	16,39		
Service rate(mu)|	220|		Average number in the system(L)|	17,33|		
Number of servers|	1		|Average time in the queue(Wq)|	,08|	,63|	1,89
|||Average time in the system(W)|	,08|	,67|	2|
|||Probability (% of time) system is empty (P0)|	,05		

````
Metricas del POM
* Average Server Utilization (𝜌): La utilización del servidor es la fracción de tiempo que el servidor está ocupado atendiendo solicitudes. Es un indicador de la eficiencia del sistema, ya que cuanto mayor es la utilización, más tiempo está ocupado el servidor. ¿Qué tan ocupado está el servidor en promedio?

* Average Number in the Queue (L_q): Esta métrica te dice cuántos clientes, en promedio, están esperando ser atendidos en la cola mientras el servidor está ocupado.

* Average Number in the System (L): Esta métrica te dice cuántos clientes/productos están en el sistema completo, es decir, la suma de los clientes/producots que están siendo atendidos y los que están esperando en la cola.

* Average Time in the Queue (W_q): Esta métrica te dice el tiempo promedio que un cliente/producto pasa esperando en la cola antes de ser atendido.

* Average Time in the System (W): Esta métrica te dice el tiempo total que un cliente/producto pasa en el sistema, incluyendo tanto el tiempo que espera en la cola como el tiempo que pasa siendo atendido.

* Probability the System is Empty (P_o): Esta métrica nos dice la probabilidad de que no haya clientes/productos en el sistema en un momento dado. Ocioso

````