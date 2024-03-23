# Reto_6
1.Dado la figura de la imagen, desarrolle:


[![68747470733a2f2f692e706f7374696d672e63632f465276436d7078782f696d6167652e706e67.png](https://i.postimg.cc/BQNmyWzT/68747470733a2f2f692e706f7374696d672e63632f465276436d7078782f696d6167652e706e67.png)](https://postimg.cc/GH8P8fdt)


.Una función matemática para calcular el volumen y el área superficial.
.Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r1, r2 y h.
.Revise como utilizar el valor de pi usando import math y math.pi
```python
import math
def calculo_volumen (r1:float, r2:float, h:float) ->float:
  Volumen = (4/3 * math.pi * r1**3)+((math.pi* r2**2* h)/3)
  return Volumen

def calculo_area_superficial (r1, r2, h) ->float:
  Area = (4*math.pi * r1**2)+((math.pi * r2**2)+(math.pi*r2* ((r2**2 + h**2) **0.5)))
  return Area

if __name__ == "__main__":
  r1 =float(input("Radio de la esfera: "))
  r2 =float(input("Radio del cono: "))
  h =float(input("Altura del cono: "))
  Volumen_figura = calculo_volumen(r1,r2,h)
  Area_superficial = calculo_area_superficial(r1,r2,h)
  print("El volumen es: " + str(Volumen_figura) + ", el area superficial es: " + str(Area_superficial))
```
Valor de pi en math
```python
import math
x =math.pi
print(x)
# 3.1415...
```
2.Dado la figura de la imagen, desarrolle:

[![68747470733a2f2f692e706f7374696d672e63632f4b7a4a626a707a742f3638373437343730373333613266326636393265.png](https://i.postimg.cc/FzT0PvK1/68747470733a2f2f692e706f7374696d672e63632f4b7a4a626a707a742f3638373437343730373333613266326636393265.png)](https://postimg.cc/BP186dHG)

.Una función matemática para calcular el área y el perimetro.
.Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r, a y b.
.Revise como utilizar el valor de pi usando import math y math.pi
```python
import math
def are (a:float, b:float, r:float):
    return (b*a) + 2*(math.pi*r)
def per (a:float, b:float, r:float):
    return (2*(b+a)) + (2*math.pi*r)
if __name__ == "__main__":
    a = float(input("Altura del rectangulo: "))
    b = float(input("Base del rectangulo: "))
    r = float(input("Radio de los dos circulos: "))
area_t = are(a, b, r)
print("El area total del la figura es " + str(area_t) + "")
per_t = per(a, b, r)
print("El perimetro total del la figura es " + str(per_t) + "")
```
3.Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

```python
def masa(n:float,m:float,k:float) -> float:
  return n*6+m*7+k*1
if __name__ == "__main__":
    n=float(input("Cantidad de gallinas: "))
    m=float(input("Cantidad de gallos: "))
    k=float(input("Cantidad de pollitos: "))
    masa_total = masa(n,m,k)
    print("La cantidad o masa total es "+str(masa_total)+" kilogramos")
```
4.Mi mamá me manda a comprar P panes a 300 cada uno, M bolsas de leche a 3300 cada una y H huevos a 350 cada uno. Hacer un programa que me diga las vueltas (o lo que quedo debiendo) cuando me da un billete de B pesos.
```python
billete: int

def panes_totales(p: int) -> int:
    return p * 300

def huevos_totales(d: int) -> int:
    return d * 350

def bolsas(c: int) -> int:
    return c * 3300

def total(p: int, d: int, c: int) -> int:
    return panes_totales(p) + huevos_totales(d) + bolsas(c)

def vuelto(billete: int, p: int, d: int, c: int) -> int:
    return billete - total(p, d, c)

def debe(billete: int, p: int, d: int, c: int) -> int:
    return total(p, d, c) - billete

if __name__ == "__main__":
    billete = int(input("Valor del billete a pagar: \n"))
    d = int(input("Número de huevos: \n"))
    p = int(input("Número de panes: \n"))
    c = int(input("Número de bolsas de leche: \n"))
    
    if billete in [2000, 5000, 10000, 20000, 50000, 100000]:
        billetes_comerciales = billete
        vuelto_final = vuelto(billete, p, d, c)
        if vuelto_final >= 0:
            print("El vuelto es:", vuelto_final)
        else:
            deber_final = debe(billete, p, d, c)
            print("La persona debe:", deber_final, "pesos adicionales.")
    elif billete != [2000, 5000, 10000, 20000, 50000, 100000]:
         print("No ingreso un billete valido")
    else:
        print("No es un billete real.")
```

5.Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.
```python
c: int
ti: float  # tasa de interes (en porcentaje)
t: int  # tiempo
def interes(c: int, ti: float) -> float:
    return c * (ti / 100)  # Convertimos la tasa de interés a porcentaje

def valor_final(c: int, ti: float, t: int) -> float:
    return c * (1 + interes(c, ti)) ** t

if __name__ == "__main__":
    c = int(input("Ingrese el capital del préstamo: "))
    ti = float(input("Ingrese la tasa de interés  sin el signo %): "))
    t = int(input("Ingrese el tiempo en meses: "))
    print("Este es el interés compuesto:", valor_final(c, ti, t))
```
6.El número de contagiados de Covid-19 en el país de NuncaLandia se duplica cada día. Hacer un programa que diga el número total de personas que se han contagiado cuando pasen D días a partir de hoy, si el número de contagiados actuales es C.
```python
def personas_finales(c: int, d: int) -> int:
    return c * (2 ** d)

if __name__ == "__main__":
    d = int(input("dias que pasaron: "))
    c = int(input("personas iniciales contaminadas: "))
    
    if d > 0 and c > 0:
        print("Se contaminaron:", personas_finales(c, d), "personas en", d, "días.")
    else:
        print("No se pueden tener días o personas negativas.")
```
7.Escriba un programa que pida 5 números reales y calcule las siguientes operaciones usando una función para cada una:

.El promedio
.La mediana
.El promedio multiplicativo (multilplica todos y luego calcula la raíz de la cantidad de operandos)
.Ordenar los números de forma ascendente
.Ordenar los números de forma descendente
.La potencia del mayor número elevado al menor número
.La raíz cúbica del menor número

```python
from funciones import ordenar_numeros

def introducir():
    a : float = float(input("Piense en un numero y digitelo: \n "))
    b : float = float(input("Digite un numero completo y seguido del dia, mes y año de su nacimiento\nejemplo, dia 19 mes 10 año 2005, numero resultante 19102005: \n "))
    c : float = float(input("Digite su edad sumando el año en el que estamos: \n "))
    d : float = float(input("dteigi un numero re random: \n "))
    e : float = float(input("Preguntele a su amigo un numero mayor a 500 y escribalo: \n "))
    numeros = ordenar_numeros(a,b,c,d,e)
    desarrollo(a,b,c,d,e,numeros)

def promedio(a,b,c,d,e):
    promedio = (a+b+c+d+e)/5
    print(f"Promedio: {promedio}")
    return

def mediana(numeros):
    mediana = numeros[2]
    print(f"Mediana: {mediana}")
    return

def promedio_multiplicativo(a,b,c,d,e):
    promedio_multiplicativo : float = (a*b*c*d*e)/5
    print(f"Promedio multiplicativo: {promedio_multiplicativo}")
    return

def ascendente(numeros):
    print(f"Números de forma ascendente: {numeros}")
    return

def descendente(numeros):
    numeros.sort(reverse=True)
    print(f"Números de forma descendente: {numeros}")
    return

def potencia(numeros):
    potencia : float = (numeros[0])**numeros[-1]
    print(f"Potencia del mayor número elevado al menor número: {potencia}")
    return

def raiz(numeros):
    numero_menor = numeros[4]
    raiz : float = numero_menor ** (1/3)
    print(f"La raiz cúbica del número menor: {raiz}")
    return

def desarrollo(a,b,c,d,e,numeros):
    promedio(a,b,c,d,e)
    promedio_multiplicativo(a,b,c,d,e)
    ascendente(numeros)
    mediana(numeros)
    descendente(numeros)
    potencia(numeros)
    raiz(numeros)
    return
    
def continuar():
    opcion : int = int(input("¿Desea continuar? Marque 1 (sí) o 2 (no): "))
    return opcion

if __name__ == "_main_":
    print("Ingrese cinco número para realizar determinadas operaciones.")

    while True:
        introducir()
        opcion = continuar()
        if opcion == 2:
            break
        elif opcion != 1 and 2:
            print("Estas bien bro?")
            break

def ordenar_numeros(a,b,c,d,e):

    if a < b and a < c and a < d and a < e:
        numeros = [a, 0, 0, 0, 0]
    elif b < a and b < c and b < d and b < e:
        numeros = [b, 0, 0, 0, 0]
    elif c < a and c < b and c < d and c < e:
        numeros = [c, 0, 0, 0, 0]
    elif d < a and d < b and d < c and d < e:
        numeros = [d, 0, 0, 0, 0]
    else:
        numeros = [e, 0, 0, 0, 0]


    if (a <= b and a <= c and a <= d and a <= e) or numeros[0] == a:
        if b <= c and b <= d and b <= e:
            numeros[1] = b
        elif c <= b and c <= d and c <= e:
            numeros[1] = c
        elif d <= b and d <= c and d <= e:
            numeros[1] = d
        else:
            numeros[1] = e
    elif b <= a and b <= c and b <= d and b <= e:
        if a <= c and a <= d and a <= e:
            numeros[1] = a
        elif c <= a and c <= d and c <= e:
            numeros[1] = c
        elif d <= a and d <= c and d <= e:
            numeros[1] = d
        else:
            numeros[1] = e
    elif c <= a and c <= b and c <= d and c <= e:
        if a <= b and a <= d and a <= e:
            numeros[1] = a
        elif b <= a and b <= d and b <= e:
            numeros[1] = b
        elif d <= a and d <= b and d <= e:
            numeros[1] = d
        else:
            numeros[1] = e
    elif d <= a and d <= b and d <= c and d <= e:
        if a <= b and a <= c and a <= e:
            numeros[1] = a
        elif b <= a and b <= c and b <= e:
            numeros[1] = b
        elif c <= a and c <= b and c <= e:
            numeros[1] = c
        else:
            numeros[1] = e
    else:
        if a <= b and a <= c and a <= d:
            numeros[1] = a
        elif b <= a and b <= c and b <= d:
            numeros[1] = b
        elif c <= a and c <= b and c <= d:
            numeros[1] = c
        else:
            numeros[1] = d

    for i in range(2, 5):
        if numeros[i] == 0:
            smallest_remaining = min([num for num in [a, b, c, d, e] if num not in numeros])
            numeros[i] = smallest_remaining

    return numeros

def promedio(a,b,c,d,e):
    promedio = (a+b+c+d+e)/5
    print(f"Promedio: {promedio}")
    return

def mediana(numeros):
    if len(numeros) % 2 == 0:
        mediana : float  = (numeros[len(numeros)//2-1] + numeros[len(numeros)//2])/2
    else:
        mediana = numeros[len(numeros)//2]
    print(f"Mediana: {mediana}")
    return

def promedio_multiplicativo(a,b,c,d,e):
    promedio_multiplicativo : float = (a*b*c*d*e)/5
    print(f"Promedio multiplicativo: {promedio_multiplicativo}")
    return

def ascendente(numeros):
    print(f"Números de forma ascendente: {numeros}")
    return

def descendente(numeros):
    numeros.sort(reverse=True)
    print(f"Números de forma descendente: {numeros}")
    return

def potencia(numeros):
    potencia : float = (numeros[0])**numeros[-1]
    print(f"Potencia del mayor número elevado al menor número: {potencia}")
    return

def raiz(numeros):
    numero_menor = numeros[4]
    raiz : float = numero_menor ** (1/3)
    print(f"La raiz cúbica del número menor: {raiz}")
    return
```
8.Para el punto anterior incluir las funciones en un archivo independiente e importarlas para su uso.

```python
from funciones import ordenar_numeros
from funciones import promedio
from funciones import mediana
from funciones import promedio_multiplicativo
from funciones import ascendente
from funciones import descendente
from funciones import potencia
from funciones import raiz
```
9.Consultar qué es y cómo funciona pip en python.
pip es un sistema de gestión de paquetes utilizado para instalar y administrar paquetes de software escritos en Python. Muchos paquetes pueden ser encontrados en el Python Package Index (PyPI). pip es un acrónimo recursivo que se puede interpretar como Pip Instalador de Paquetes o Pip Instalador de Python. Una característica particular de pip es que permite gestionar listas de paquetes y sus números de versión correspondientes a través de un archivo de requisitos. Esto nos permite una recreación eficaz de un conjunto de paquetes en un entorno separado (p. ej. otro ordenador) o entorno virtual.

10.Hacer un listado de módulos populares para python que se puedan instalar com pip y consultar cómo instalarlos.
.requests: Una biblioteca para realizar solicitudes HTTP de manera sencilla. pip install requests

.numpy: Proporciona soporte para arrays y matrices, junto con una colección de funciones matemáticas. pip install numpy

.pandas: Ofrece estructuras de datos y herramientas de análisis de datos. pip install pandas

.matplotlib: Una biblioteca de gráficos 2D que produce figuras de calidad en una variedad de formatos impresos y entornos interactivos. pip install matplotlib

.scipy: Utilizado para cálculos científicos y técnicos. pip install scipy

.flask: Un microframework para aplicaciones web. pip install flask

.django: Un framework de alto nivel para el desarrollo rápido de sitios web seguros y mantenibles. pip install django

.beautifulsoup4: Utilizado para raspar datos de archivos HTML y XML. pip install beautifulsoup4

.tensorflow: Una biblioteca de código abierto para aprendizaje automático. pip install tensorflow

.pytorch: Otra biblioteca para aprendizaje automático, enfocada en la computación de tensores y redes neuronales. pip install torch torchvision

<h2>Bibliografía</h2>
    <div class="bibliografia">
        <table>
          <tr>
                <td>Hafeezul Kareem Shaik. 14 bibliotecas y módulos de Python que todo desarrollador debería conocer. Recuperado de https://geekflare.com/es/popular-python-libraries-modules/<a href="https://geekflare.com/es/popular-python-libraries-modules/"></a></td>
            </tr> 
          <tr>
                <td>Wikipedia. (2024). Pip (administrador de paquetes). Recuperado de (https://es.wikipedia.org/wiki/Pip_(administrador_de_paquetes))<a href="(https://es.wikipedia.org/wiki/Pip_(administrador_de_paquetes))"></a></td>
          </tr>            
        </table>
    </div>
