# pdc_reto_12
### Soy Rafael Santiago Chirivi Peña y pertenezco al grupo de "Fenomenoides", adelante se muestra nuestro logo 

<details><summary>Preparense para ver el grandioso logo: </summary><p>
<div align='center'>
<figure> <img src="https://i.postimg.cc/NFbwf57S/logo-def.png" alt="Defensa Civil" width="400" height="auto"/></br>
<figcaption><b> "somos programadores, no diseñadores" </b></figcaption></figure>
</div>
</p></details><br>

### A continuacion, se muestran las soluciones propuestas a los distintos puntos de este reto

Procesar el archivo y extraer:

Cantidad de vocales
Cantidad de consonantes
Listado de las 50 palabras que más se repiten

```python
archivo_texto = open("reto12text.txt", "r") # se importa el archivo de texto
text = archivo_texto.read()                 # se asigna el texto a una variable
text = text.lower()                         # se hacen minusculas todos los caracteres alfabeticos
palabras_unicas = []                        # se define una lista vacia de palabras unicas
tabla_frecuencia : list = []                # se defina una lista vacia para guardar las frecuencias de las palabras

vocales : int = int(text.count("a")) + int(text.count("e")) + int(text.count("i")) + int(text.count("o")) + int(text.count("u"))    # se define la cantidad de vocales a partir del numero de apariciones de los caracteres a e i o u 
print(f"el numero de vocales dentro del texto es de {vocales}")         # se imprimen el numero de vocales

consonantes : int = int(text.count("b")) + int(text.count("c")) + int(text.count("d")) + int(text.count("f")) + int(text.count("g")) + int(text.count("h")) + int(text.count("j")) + int(text.count("k")) + int(text.count("l")) + int(text.count("m")) + int(text.count("n")) + int(text.count("p")) + int(text.count("q")) + int(text.count("r")) + int(text.count("s")) + int(text.count("t")) + int(text.count("v")) + int(text.count("w")) + int(text.count("x")) + int(text.count("y")) + int(text.count("z"))    # se define la cantidad de consonantes a partir del numero de apariciones de estos caracteres
print(f"el numero de consonantes dentro del texto es de {consonantes}") # se imprimen el numero de consonantes

palabras : list = text.split()  # se convierte el texto a una lista, removiendo caracteres que pueden generar problemas como puntos (.), comas (,) etc...
print(f"el numero de palabras en el texto es de {len(palabras)}")   # se imprime el numero de palabras a partir de la cantidad de elementos de la lista creada

for i in range (len(palabras)):                             # se recorre la lista creada
        existencia = palabras[i] in palabras_unicas         # se define una propiedad de existencia, para asi evitar hallar frecuencia de palabras repetidas en base a una lista que resguarda las palabras unicas del texto
        if existencia == False:                             # si se comprueba que la palabra analizada no hace parte de la lista de palabras unicas, se realiza el proceso
            palabra_frecuencia = []                         # se define una lista vacia para guardar la frecuencia de la palabra y la palabra misma
            frecuencia : int = palabras.count(palabras[i])  # se halla la frecuencia de la palabra
            palabras_unicas.append(palabras[i])             # se añade esta palabra a la lista de palabras unicas para tener un punto de comparación
            palabra_frecuencia.append(frecuencia)           # se añade la frecuencia de la palabra a la lista definida
            palabra_frecuencia.append(palabras[i])          # se añade la palabra a la lista definida
        tabla_frecuencia.append(palabra_frecuencia)         # se añade la lista frecuencia-palabra a una lista mas grande para poder guardar todas las palabras unicas junto a sus frecuencias

tabla_frecuencia.sort(reverse=True)     # se ordena de manera descendente las frecuencias, y al tratarse de listas en el formato explicado, se ordenan tambien las palabras asignadas a las frecuencias
for i in range(0,50):   # se recorre un rango de 50 iteraciones
    print(f"la palabra {tabla_frecuencia[i][1]} aparece un total de {tabla_frecuencia[i][0]} veces en el texto")    # se imprime la palabra y el numero de apariciones que presenta en el texto, todo esto un total de 50 veces
```
