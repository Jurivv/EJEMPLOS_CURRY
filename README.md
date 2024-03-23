# Reto_6
1.Dado la figura de la imagen, desarrolle:


[![68747470733a2f2f692e706f7374696d672e63632f465276436d7078782f696d6167652e706e67.png](https://i.postimg.cc/BQNmyWzT/68747470733a2f2f692e706f7374696d672e63632f465276436d7078782f696d6167652e706e67.png)](https://postimg.cc/GH8P8fdt)


.Una función matemática para calcular el volumen y el área superficial.
.Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r1, r2 y h.
.Revise como utilizar el valor de pi usando import math y math.pi


2.Dado la figura de la imagen, desarrolle:
[![68747470733a2f2f692e706f7374696d672e63632f3174344d727a734c2f696d6167652e706e67.png](https://i.postimg.cc/KzJbjpzt/68747470733a2f2f692e706f7374696d672e63632f3174344d727a734c2f696d6167652e706e67.png)](https://postimg.cc/BLLkwg2v)
.Una función matemática para calcular el área y el perimetro.
.Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r, a y b.
.Revise como utilizar el valor de pi usando import math y math.pi


3.Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.


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
