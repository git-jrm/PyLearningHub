# PyLearningHub

Bienvenid@ a `PyLearningHub` nuestro programa inteligente para aprender Python en sólo 6 lecciones, desde fundamentos hasta técnicas avanzadas.

Cada Lección se compone de conceptos clave y un código de ejemplo que puede ir escribiendo y ejecutando. Requerimientos técnicos: tener instalado Python 3.12+ y algún IDE como VS Code. Alternativamente, si no puede instalar use Google Colab `colab.research.google.com`.

Los contenidos se han organizado cuidadosamente para ofrecer una experiencia secuencial y un aprendizaje progresivo. ¡Empecemos!

> `Relacionado:` Portafolio de Ingeniería de Datos con código Python: [Módulo 2](https://github.com/git-jrm/ing-datos-M2), [Módulo 3](https://github.com/git-jrm/ing-datos-M3)

## Lecciones:
- [Lección N° 1 : Sentencias Básicas](#lecci%C3%B3n-n-1--sentencias-b%C3%A1sicas)
- [Lección N° 2 : Estructuras y Sentencias iterativas](#lección-n-2--estructuras-de-datos-y-sentencias-iterativas)
- [Lección N° 3 : Excepciones](#lección-n-3--manejo-de-excepciones)
- [Lección N° 4 : Funciones y Módulos](#lección-n-4--funciones-y-módulos)
- [Lección N° 5 : Programación Orientada a Objetos](#lección-n-5--programación-orientada-a-objetos)
- [Lección N° 6 : Uso Avanzado](#lecci%C3%B3n-n6--python-avanzado)

## Lección N° 1 : Sentencias Básicas
### • 1.1) Asignación y salida
```
nombre = "Ana"  # asignación a variable `nombre` dato String "Ana"
clase = 'vip'  # asignación dato String usando comillas simples
puerta = 33  # asignación dato Integer
print(f"bienvenid@ {nombre}, vaya a la puerta {puerta}")  # salida por pantalla
```
### • 1.2) Entrada y condicional
```
nombre = input("Su nombre: ")  # entrada desde teclado
tipo = input("Su clase: ")  # entrada desde teclado
if(tipo == 'vip') # condicional si es vip o no
  print(f"bienvenid@ {nombre}, pase")
else
  print(f"bienvenid@ {nombre}, favor espere")
```
### • 1.3) Operadores aritmeticos, de comparación y lógicos
```
nombre = "Jose"
tipo = "vip"
puntos = 1_000
precio = 100_000
desc = 0.30
subtotal = precio * (1 - desc) # operador aritmético

es_vip = tipo == 'vip'  # operador de comparación
if es_vip: # operador lógico
    puntos = puntos + (subtotal * 0.5)  # operador aritmético
else:
    puntos = puntos + (subtotal * 0.1)  # operador aritmético

print(f"Es VIP: {es_vip}")  # salida operador lógico
print(f"Ha acumulado: {puntos} puntos")  # salida
```

[Volver](#pylearninghub)

## Lección N° 2 : Estructuras de Datos y Sentencias Iterativas
### • 2.1) Estructuras de datos
#### a) Listas: colecciones ordenadas y modificables
```
clases = ["economy", "vip"]  # esta es una lista, se usa []
clases_list = list(["economy", "vip", "especial"])  # otra forma
print(clases[1])  # accede al 2° valor

clases.remove("especial")  # elimina por valor
ultimo = clases.pop()  # elimina y retorna último
print(f"Se eliminó: {ultimo}")  # Se eliminó: vip

clases.append("business")  # agrega 1 elemento al final
clases.extend(["platinum","vip"])  # agrega múltiples elementos al final
clases.insert(1, "premium")  # inserta en 2° posición
print(clases)  # ['economy', 'premium', 'business', 'platinum', 'vip']
```
#### b) Tuplas: como lista pero inmutable
```
coordenadas = (33.4489, -70.6693)  # esta es una tupla, se usa ()
coordenadas_tuple = tuple([33.4489, -70.6693])  # otra forma
print(coordenadas[1])  # accede al 2°
x, y = coordenadas  # desempaquetado
print(f"x: {x}, y: {y}")

print(len(coordenadas))  # longitud, sirve en list
print(coordenadas.index(-70.6693))  # indica posición 1 (2° valor)
```
##### c) Conjuntos: únicos sin orden
```
clases = {'economy', 'premium', 'business', 'platinum', 'vip'}  # conjunto (set)
clases.add("vip")  # no duplica
print(clases)
```
#### d) Diccionarios: clave-valor
```
cliente = {"nombre": "Ana", "clase": "vip"}  # este es un diccionario (dict), se usa {}
print(cliente["nombre"])  # salida: Ana
cliente["puntos"] = 1500  # agrega nueva clave-valor
print(cliente)
```
### • 2.2) Ciclos
#### a) While: itera mientras se cumpla la condicion
```
clases = {'economy', 'premium', 'business', 'platinum', 'vip'}
intento = ""
while intento not in clases:
    intento = input("Ingrese clase cliente: ")
print(f"Clase cliente valido: {intento}")

```
#### b) Ciclo For
```
clases = {'economy', 'premium', 'business', 'platinum', 'vip'}
for tipo in clases:
    print(f"Tipo disponible: {tipo}")
```
#### c) Compresión y optimización
```
porcentajes = [0.1, 0.2, 0.3, 0.4, 0.5]
precio = 100_000
puntos = [precio * p for p in porcentajes]
print(puntos)
```

[Volver](#pylearninghub)

## Lección N° 3 : Manejo de Excepciones
### • 3.1) Manejo genérico try-except
```
try:  # bloque a protejer de Excepciones
    puntos = int(input("Ingrese Puntos: "))
    print(f"Puntos ingresados: {puntos}")
except:  # controla cualquier tipo de excepción
    print("Ocurrió algún tipo de error al ingresar puntos.")
```
### • 3.2) Finally
```
try:
    puntos = int(input("Ingrese Puntos: "))
    print(f"Puntos ingresados: {puntos}")
except:
    print("Ocurrió algún tipo de error al ingresar puntos.")
finally:
    print("Liberando recursos")  # se ejecuta siempre
```
### • 3.3) específicas
```
try:
    puntos = int(input("Ingrese Puntos: "))
    print(f"Puntos ingresados: {puntos}")
except ValueError:
    print("Ocurrió un <<ValueError>> al ingresar puntos.")
finally:
    print("Liberando recursos")
```
### • 3.4) Excepciones personalizadas
```
# definición simple de Excepción
class NumericPuntosError(Exception):
    pass

try:
    puntos = input("Ingrese Puntos: ")
    if not puntos.isdigit():  # si no es número
        raise NumericPuntosError("Puntos debe ser numérico.")
    puntos = int(puntos)
    print(f"Puntos registrados: {puntos}")
except NumericPuntosError as e:
    print(f"Error personalizado: {e}")
finally:
    print("Liberando recursos")
```

[Volver](#pylearninghub)

## Lección N° 4 : Funciones y Módulos
### • 4.1) Funciones: se definen con la palabra reservada `def`
```
# declaración de función (reutilización de código)
def calcula_puntos(precio, clase): # recibe Parametros precio y tipo
    if clase == "vip":
        return precio * 0.5
    else:
        return precio * 0.1

puntos = calcula_puntos(300_000, "vip") # envía Argumentos
print(f"Ana generó {puntos_ana} puntos")
print(f"Jose generó {calcula_puntos(900_000, "business")} puntos")
```
### • 4.2) Módulos propios
```
# moduloPuntos.py
def calculaPuntos(precio, clase): # recibe Parametros precio y clase
    if clase == "vip":
        return precio * 0.5
    else:
        return precio * 0.1
```

```
# main.py
from moduloPuntos import calculaPuntos

datos = []
puntos = calculaPuntos(300_000, "vip")
datos.append(puntos)
datos.append(calculaPuntos(900_000, "business"))
print(datos)
```
### • 4.3) Paquetes externos (import)
Si necesitamos funcionalidad adicional a la librería estandar debemos instalar la que necesitemos, en este caso instalaremos `pyopensky` ejecutando: `pip install pyopensky`
```
# pip install pyopensky

from pyopensky.rest import REST

api = REST()
df = api.states()  # obtiene estado de vuelos actuales
print(df.columns)  # muestra las columnas disponibles
print(df.head(10)[["callsign", "origin_country", "altitude", "sensors", "groundspeed"]])
```

[Volver](#pylearninghub)

## Lección N° 5 : Programación Orientada a Objetos
### • 5.1) Principios POO
• **_Encapsulamiento_**: Otorga seguridad, controla cuales detalles internos se muestran o se ocultan.

• **_Abstracción_**: Simplifica, permite ejecutar funcionalidad compleja mediante una invocación.

• **_Herencia_**: Mejora código y mantenibilidad, modelando clases del mundo real, para no repetir codigo. 

• **_Polimorfismo_**: flexibilidad, comportamientos adaptable según escenario y contexto.

### • 5.2) clases y objetos
```
# definición de Clase
class Persona:
    def __init__(self, nombre, edad):  # constructor
        self.nombre = nombre
        self.edad = edad

class Pasajero(Persona):  # hereda de Clase <<Persona>>
    def __init__(self, nombre, edad, clase, destino):
        super().__init__(nombre, edad)  # llama a constructor padre
        self.clase = clase
        self.destino = destino

# creación de objeto
p1 = Pasajero("Ana", 35, "vip", "Londres")
print(f"{p1.nombre} ({p1.edad}) viaja a {p1.destino} como {p1.clase}")
```

[Volver](#pylearninghub)

## Lección N°6 : Python Avanzado
### • 6.1) Programas multiparadigma
Python además de tener tipado dinámico y ser multiproposito, es multiparadigma, lo que permite crear casi cualquier tipo de solución. Esto permite crear programas usando paradigmas como programación `imperativa` (estructurada, por procedimientos y orientada a objetos) ó `declarativa` (funcional y lógica). Esto permite crear soluciones en áreas tan diversas como: ciencia de datos, Mobile ó Desk Apps, Web, E-comerce, Cyberseguridad, entre muchos otros.

### • 6.2) biblioteca estandar
La biblioteca estándar de Python es muy amplia y poderosa, algunas de las librerías más usadas podrían ser `math`, `random` y `statistics` para ciencia de datos y `os`, `io` y `csv` para desarrollo avanzado, entre muchas otras.
#### a) biblioteca estándar en Ciencia de datos
```
import math
import statistics
import random

print(f"Raíz de 144: {math.sqrt(144)}")  # 12.0
print(f"Coseno de 0: {math.cos(0)}")  # 1.0

datos = [100, 200, 300, 400, 500]
print(f"Promedio: {statistics.mean(datos)}")  # 300
print(f"Mediana: {statistics.median(datos)}")  # 300

print(f"Elemento aleatorio: {random.choice(datos)}")
print(f"Número entre 1 y 10: {random.randint(1, 10)}")
```
#### b) biblioteca estándar en Desarrollo avanzado: 
```
import os
import csv
import datetime

print(f"Ruta actual: {os.getcwd()}")
print(f"Archivos en directorio actual: {os.listdir()}")

with open("clientes.csv", mode="w", newline="") as archivo:
    writer = csv.writer(archivo)
    writer.writerow(["Nombre", "Clase", "Puntos"])
    writer.writerow(["Ana", "vip", 1500])

ahora = datetime.datetime.now()
print(f"Fecha y hora actual: {ahora}")
print(f"Solo fecha: {ahora.date()}")

```
### • 6.3) Ejercicios desarrollo aplicaciones próposito general
#### Ejercicios desarrollo 1 : Generador de contraseña simple
Objetivo: Utiliza las bibliotecas estándar random y string para crear una contraseña aleatoria de 8 caracteres.
```
import random
import string

caracteres = string.ascii_letters + string.digits
contrasena = ''.join(random.choice(caracteres) for _ in range(8))
print(f"Contraseña generada: {contrasena}")
```
#### Ejercicios desarrollo 2 : Registro básico de usuarios en archivo CSV
Objetivo: Solicita al usuario su nombre y clase de cliente, y guarda los datos en un archivo CSV llamado usuarios.csv.
```
import csv

nombre = input("Ingrese su nombre: ")
clases = {'economy', 'premium', 'business', 'platinum', 'vip'}

intento = ""
while intento not in clases:
    intento = clase = input("Ingrese su clase: ")

with open("usuarios.csv", mode="a", newline="") as archivo:
    writer = csv.writer(archivo)
    writer.writerow([nombre, clase])
    print(f"Usuario {nombre} ({clase}) registrado correctamente.")
```

[Volver](#pylearninghub)










