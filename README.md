# PyLearningHub

Bienvenid@ a `PyLearningHub` nuestro programa inteligente para aprender Python en sólo 6 lecciones, desde fundamentos hasta tecnicas avanzadas, ideal si tienes con poco tiempo ¡Empecemos!

Cada Lección se compone de conceptos clave y un codigo de ejemplo que tienes que ir escribiendo y ejecutando. Al finalizar tendrás 6 archivos que te servirán para repasar las 6 lecciones.

Requerimientos técnicos: tener instalado Python 3.12+ y algún IDE como VS Code. Alternativamente si no puede hacer instalación puede usar Google Colab `colab.research.google.com`.

## Lecciones:
- Lección N° 1 : Sentencias Básicas
- Lección N° 2 : Estructuras y Sentencias iterativas
- Lección N° 3 : Excepciones
- Lección N° 4 : Funciones y Módulos
- Lección N° 5 : Programación Orientada a Objetos (POO)
- Lección N° 6 : Uso Avanzado


## Lección N° 1 : Sentencias Básicas
### • 1.1) Asignación y salida
```
nombre = "Ana"  # asignación dato String
tipo = 'vip'  # asignación dato String
print(f"bienvenid@ {nombre} ({tipo}) pase")  # salida
```
### • 1.2) Entrada y condicional
```
nombre = input("Su nombre: ")  # entrada
tipo = input("Tipo cliente: ")  # entrada
if(tipo == 'vip') # condicional si es vip o no
  print(f"bienvenid@ {nombre} ({tipo}) pase")
else
  print(f"bienvenid@ {nombre} ({tipo}) espere")
```
### • 1.3) Operadores aritmeticos, de comparación y lógicos
```
nombre = "Jose"
tipo = "vip"
puntos = 1_000
precio_base = 100_000
desc = 0.30
precio_final = precio_base * (1 - desc)

es_vip = tipo == 'vip'  # operador de comparación
if es_vip: # operador lógico
    puntos = precio_final * 0.2  # operador aritmerico
    print(f"Bienvenid@ {nombre} ({tipo}) pase")
else:
    puntos = precio_final * 0.1  # operador aritmerico
    print(f"bienvenid@ {nombre} ({tipo}) espere")

print(f"Es VIP: {es_vip}")  # salida operador lógico
```


## Lección N° 2 : Estructuras de Datos y Sentencias Iterativas
### • 2.1) Estructuras de datos
#### a) Listas: colecciones ordenadas y modificables
```
clases = ["turista", "vip"]  #esta es una lista
print(clases[1])  # accede a 2° valor
clases.append("platino")  # agrega elemento al final
print(clases)
```
#### b) Tuplas: como lista pero inmutable
```
coordenadas = (33.4489, -70.6693)
print(coordenadas[1])  # acceso al 2ro
x, y = coordenadas  # desempaquetado
print(f"x: {x}, y: {y}")
```
##### c) Conjuntos: únicos sin orden
```
clases = {"turista", "vip", "platino"}
clases.add("vip")  # no duplica
print(clases)
```
#### d) Diccionarios: clave-valor
```
cliente = {"nombre": "Ana", "tipo": "vip"}
print(cliente["nombre"])  # salida: Ana
cliente["puntos"] = 1500  # agregar nueva entrada
print(cliente)
```
### • 2.2) Ciclos
#### a) While: itera mientras se cumpla la condicion
```
clases = {"turista", "vip", "platino"}
intento = ""
while intento not in clases:
    intento = input("Ingrese tipo de cliente: ")
print(f"Tipo cliente valido: {intento}")

```
#### b) Ciclo For
```
clases = {"turista", "vip", "platino"}
for tipo in clases:
    print(f"Tipo disponible: {tipo}")
```
#### c) Ciclo For comprimido
```
porcentajes = [0.1, 0.2, 0.3]
precio = 100_000
puntos = [precio * p for p in porcentajes]
print(puntos)
```


## Lección N° 3 : Manejo de Excepciones
### • 3.1) Manejo genérico
```
try:
    puntos = int(input("Ingrese puntos acumulados: "))
    print(f"Puntos ingresados: {puntos}")
except:
    print("Ocurrió un error al ingresar puntos.")
```
### • 3.2) Finally
```
try:
    puntos = int(input("Ingrese puntos acumulados: "))
    print(f"Puntos ingresados: {puntos}")
except:
    print("Ocurrió un error al ingresar puntos.")
finally:
    print("Liberando recursos")
```
### • 3.3) específicas
```
try:
    puntos = int(input("Ingrese puntos acumulados: "))
    print(f"Puntos ingresados: {puntos}")
except ValueError:
    print("Ocurrió un ValueError al ingresar puntos.")
finally:
    print("Liberando recursos")
```
### • 3.4) excepttion personalizadas
```
class DatoPuntosError(Exception):
    pass  # definición más simple

puntos = input("Ingrese puntos: ")
try:
    if not puntos.isdigit():  # si no es número
        raise DatoPuntosError("Puntos no es número.")
    puntos = int(puntos)
    print(f"Puntos registrados: {puntos}")
except DatoPuntosError as e:
    print(f"Error personalizado: {e}")
finally:
    print("Liberando recursos")
```


## Lección N° 4 : Funciones y Módulos
### • 4.1) funciones
```
# declaración de función
def calc_puntos(precio, tipo): # recibe Parametros
    if tipo == "vip":
        return precio * 0.2
    else:
        return precio * 0.1

puntos = calc_puntos(100_000, "vip") # envía Argumentos
print(f"Generó {puntos} puntos")
```
### • 4.2) librerías y modulos
```
import pandas as pd  # importa paquete de datos
df = pd.DataFrame([100, 200, 300])  # crea dataframe
print(df)  # dataframe potencia y abstrae el manejo
```


## Lección N° 5 : Programación Orientada a Objetos (POO)
### • 5.1) Principios POO
• **_Encapsulamiento_**: Otorga seguridad, controla cuales detalles internos se muestran o se ocultan.

• **_Abstracción_**: Simplifica, permite ejecutar funcionalidad compleja mediante una invocación.

• **_Herencia_**: Mejora código y mantenibilidad, modelando clases del mundo real, para no repetir codigo. 

• **_Polimorfismo_**: flexibilidad, comportamientos adaptable según escenario y contexto.

### • 5.2) clases y objetos
```
# definición de clase base
class Persona:
    def __init__(self, nombre, edad):  # constructor
        self.nombre = nombre
        self.edad = edad

class Pasajero(Persona):  # hereda de Persona
    def __init__(self, nombre, edad, clase, destino):
        super().__init__(nombre, edad)  # llama a constructor padre
        self.clase = clase
        self.destino = destino

# creación de objeto
p1 = Pasajero("Ana", 35, "vip", "Londres")
print(f"{p1.nombre} ({p1.edad}) viaja a {p1.destino} como {p1.clase}")
```


## Lección N°6 : Uso Avanzado del Lenguaje
### • 6.1) multiparadigma
Existen dos categorías de paradigma de programación la `programación imperativa` (estructurada, por procedimientos y orientada a objetos) y la `programación declarativa` (funcional y lógica). Al ser Python es multiparadigma le permite adoptar cualquier paradigma, además es multiproposito

```
# Programación estructurada, paso a paso
total = 0
for n in [10, 20, 30]:
    total += n
print(f"Total (imperativo): {total}")

# Programación funcional, con funciones integradas
numeros = [10, 20, 30]
suma = sum(numeros)
print(f"Total (funcional): {suma}")
```
### • 6.2) tipado dinamico
```
dato = 10       # entero
print(type(dato))

dato = "texto"  # ahora es string
print(type(dato))

dato = [1, 2, 3]  # ahora es lista
print(type(dato))
```
### • 6.3) bibliotecas (Pandas)
```
import pandas as pd  # importa librería de datos

datos = {"Cliente": ["Ana", "Luis"], "Puntos": [1500, 800]}
df = pd.DataFrame(datos)  # crea tabla de datos

print(df)  # muestra la tabla
```
```
from datetime import datetime  # importa desde biblioteca estándar

# obtiene la fecha y hora actual
ahora = datetime.now()
print(f"Fecha y hora actual: {ahora}")

# formateo personalizado de fecha
formato = ahora.strftime("%d-%m-%Y %H:%M")
print(f"Formato amigable: {formato}")
```









