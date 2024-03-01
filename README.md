import json
from pathlib import Path
BASE_DIR = Path(__file__).resolve().parent

notas  = []

while True: # nos permite ingresar varios alumnos hasta que decidamos salir
    nombre = input("Ingrese el nombre del alumno (s para salir): ")
    if nombre == "s":
        print("Saliendo...")
        break
    nota = float(input("Ingrese su nota: "))
    alumno = {"nombre": nombre, "nota": nota} # aca se crea un diccionario que se mete dentro de la lista de notas 
    notas.append(alumno)

with open(BASE_DIR/"notas.json", "w") as archivo: # base dir para que me guarde bien el archivo donde va 
    json.dump(notas, archivo) # una vez que sale del bucle, recien ahi va a guardar los datos en archivo json

print("Las notas se han guardado en el archivo notas.json")


# pandas pip install pandas

from pathlib import Path

import pandas # sirve para la manipulacion y analisis de datos
              # pip install pandas en la terminal

BASE_DIR = Path(__file__).resolve().parent
ruta_archivo = BASE_DIR / "dataset_turnos_detalle.csv"

datos = pandas.read_csv(ruta_archivo)
print(datos) # si no quiero usar la extension Jupyter

# INSTALAR BIEN PANDAS #


