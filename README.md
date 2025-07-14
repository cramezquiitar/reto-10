Reto 10 


## Reto 10


1. Desarrolle un programa que permita realizar la [suma/resta de matrices](https://es.wikipedia.org/wiki/Adici%C3%B3n_matricial). El programa debe validar las condiciones necesarias para ejecutar la operación.
suma de matrices
```python
# Esta función me permite ingresar los datos de una matriz
def ingresar_matriz(nombre):
    # Primero pregunto cuántas filas y columnas va a tener
    cantidad_filas = int(input("¿Cuántas filas tiene la matriz " + nombre + "?: "))
    cantidad_columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre + "?: "))
    
    print("Voy a ingresar los valores de la matriz " + nombre + ":")
    nueva_matriz = []  # Aquí voy a guardar la matriz completa

    # Recorro cada fila
    for num_fila in range(cantidad_filas):
        fila_actual = []  # Esta lista va a guardar los números de una fila
        # Recorro cada columna dentro de esa fila
        for num_columna in range(cantidad_columnas):
            mensaje = "Valor en la posición [" + str(num_fila) + "][" + str(num_columna) + "]: "
            numero = float(input(mensaje))  # Ingreso el número y lo convierto a decimal
            fila_actual.append(numero)  # Lo guardo en la fila actual
        nueva_matriz.append(fila_actual)  # Guardo toda la fila en la matriz

    return nueva_matriz, cantidad_filas, cantidad_columnas


# Esta función me permite mostrar la matriz por pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        texto = ""  # En esta variable voy armando la línea que voy a mostrar
        for numero in fila:
            texto += str(numero) + "  "  # Uno los números con espacios
        print(texto)  # Muestro la línea completa


# Esta función hace la suma entre dos matrices del mismo tamaño
def sumar_matrices(matriz_1, matriz_2):
    resultado_suma = []  # Aquí voy a guardar la matriz que resulta de la suma

    # Recorro cada fila de ambas matrices
    for posicion_fila in range(len(matriz_1)):
        fila_sumada = []  # Aquí guardo los resultados de esta fila
        for posicion_columna in range(len(matriz_1[0])):
            suma = matriz_1[posicion_fila][posicion_columna] + matriz_2[posicion_fila][posicion_columna]
            fila_sumada.append(suma)  # Guardo el número sumado
        resultado_suma.append(fila_sumada)  # Agrego la fila completa al resultado

    return resultado_suma


# Parte principal del ccodigo 
print("Este programa suma dos matrices del mismo tamaño")

# Ingreso de datos para ambas matrices
matriz_A, filas_A, columnas_A = ingresar_matriz("A")
matriz_B, filas_B, columnas_B = ingresar_matriz("B")

# Me aseguro de que las matrices tengan el mismo tamaño
if filas_A != filas_B or columnas_A != columnas_B:
    print("No puedo hacer la suma porque las matrices tienen tamaños diferentes.")
else:
    # Hago la suma si todo está bien
    resultado = sumar_matrices(matriz_A, matriz_B)
    print("La matriz resultado de la suma es:")
    mostrar_matriz(resultado)
```
Resta de matricces:
```python
# Esta función me permite ingresar todos los datos de una matriz
def ingresar_matriz(nombre):
    # Primero pregunto cuántas filas y columnas tiene la matriz
    cantidad_filas = int(input("¿Cuántas filas tiene la matriz " + nombre + "?: "))
    cantidad_columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre + "?: "))
    
    print("Voy a ingresar los valores de la matriz " + nombre + ":")
    nueva_matriz = []  # Aquí voy a guardar toda la matriz

    # Recorro cada fila una por una
    for num_fila in range(cantidad_filas):
        fila_actual = []  # Aquí guardo los números de la fila que estoy armando
        # Recorro cada columna en esa fila
        for num_columna in range(cantidad_columnas):
            texto = "Valor en la posición [" + str(num_fila) + "][" + str(num_columna) + "]: "
            numero = float(input(texto))  # Pido el número y lo convierto a decimal
            fila_actual.append(numero)  # Guardo el número en la fila
        nueva_matriz.append(fila_actual)  # Agrego la fila completa a la matriz

    return nueva_matriz, cantidad_filas, cantidad_columnas


# Esta función me permite mostrar una matriz en pantalla, fila por fila
def mostrar_matriz(matriz):
    for cada_fila in matriz:
        linea_mostrada = ""  # Esta línea va guardando los números de una fila
        for numero in cada_fila:
            linea_mostrada += str(numero) + "  "  # Uno cada número con un espacio
        print(linea_mostrada)  # Muestro la fila completa


# Esta función hace la resta entre dos matrices del mismo tamaño
def restar_matrices(matriz_uno, matriz_dos):
    resultado_resta = []  # Aquí voy a guardar la nueva matriz restada

    for fila_posicion in range(len(matriz_uno)):
        fila_resultado = []  # Esta es la fila que voy armando
        for columna_posicion in range(len(matriz_uno[0])):
            # Resto el número de la primera matriz con el de la segunda
            diferencia = matriz_uno[fila_posicion][columna_posicion] - matriz_dos[fila_posicion][columna_posicion]
            fila_resultado.append(diferencia)  # Guardo el resultado de esa posición
        resultado_resta.append(fila_resultado)  # Agrego la fila completa al resultado final

    return resultado_resta


# Parte principal del codigo
print("Este programa resta dos matrices de igual tamaño")

# Primero ingreso las dos matrices
matriz_A, filas_A, columnas_A = ingresar_matriz("A")
matriz_B, filas_B, columnas_B = ingresar_matriz("B")

# Verifico que ambas matrices tengan el mismo tamaño
if filas_A != filas_B or columnas_A != columnas_B:
    print("No se puede hacer la resta porque las matrices no tienen el mismo tamaño.")
else:
    # Si son del mismo tamaño, hago la resta
    resultado_final = restar_matrices(matriz_A, matriz_B)
    print("El resultado de la resta es:")
    mostrar_matriz(resultado_final)

```
2. Desarrolle un programa que permita realizar el [producto de matrices](https://es.wikipedia.org/wiki/Multiplicaci%C3%B3n_de_matrices). El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
# Esta función me permite ingresar los datos de una matriz
def ingresar_matriz(nombre):
    # Primero pregunto cuántas filas y columnas tiene la matriz
    cantidad_filas = int(input("¿Cuántas filas tiene la matriz " + nombre + "?: "))
    cantidad_columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre + "?: "))
    
    print("Ahora voy a ingresar los valores para la matriz " + nombre + ":")
    nueva_matriz = []  # Aquí voy a guardar toda la matriz

    for num_fila in range(cantidad_filas):
        fila_actual = []  # Esta lista guarda los valores de la fila actual
        for num_columna in range(cantidad_columnas):
            texto = "Valor en la posición [" + str(num_fila) + "][" + str(num_columna) + "]: "
            numero = float(input(texto))  # Ingreso el número en esa posición
            fila_actual.append(numero)
        nueva_matriz.append(fila_actual)  # Agrego la fila completa a la matriz

    return nueva_matriz, cantidad_filas, cantidad_columnas


# Esta función me permite mostrar cualquier matriz en pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for numero in fila:
            linea += str(round(numero, 2)) + "  "  # Convierto a texto y redondeo a 2 decimales
        print(linea)


# Esta función hace la multiplicación entre dos matrices si es posible
def multiplicar_matrices(matriz_A, matriz_B):
    matriz_resultado = []  # Aquí voy a guardar la matriz resultante

    # Recorro cada fila de la primera matriz
    for fila_A in range(len(matriz_A)):
        fila_nueva = []  # Esta fila se irá llenando con los resultados

        # Recorro cada columna de la segunda matriz
        for columna_B in range(len(matriz_B[0])):
            acumulador = 0  # Aquí voy a acumular la suma de los productos

            # Recorro cada posición para multiplicar fila por columna
            for posicion in range(len(matriz_B)):
                numero_A = matriz_A[fila_A][posicion]
                numero_B = matriz_B[posicion][columna_B]
                producto = numero_A * numero_B
                acumulador = acumulador + producto  # Acumulo el resultado

            fila_nueva.append(acumulador)  # Guardo el número en la fila
        matriz_resultado.append(fila_nueva)  # Agrego la fila al resultado final

    return matriz_resultado


# Parte principal del codigo
print("Este programa multiplica dos matrices, si se puede")

# Ingreso de ambas matrices
matriz1, filas1, columnas1 = ingresar_matriz("A")
matriz2, filas2, columnas2 = ingresar_matriz("B")

# Verifico que las dimensiones sean compatibles para multiplicar
if columnas1 != filas2:
    print("No puedo hacer la multiplicación.")
    print("Las columnas de la primera matriz deben ser iguales a las filas de la segunda.")
else:
    resultado = multiplicar_matrices(matriz1, matriz2)
    print("La matriz resultado de la multiplicación es:")
    mostrar_matriz(resultado)
```
3. Desarrolle un programa que permita obtener la  [matriz transpuesta](https://es.wikipedia.org/wiki/Matriz_transpuesta) de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.
```python
# Esta función me permite ingresar todos los datos de una matriz
def ingresar_matriz(nombre):
    # Primero pregunto cuántas filas y columnas tiene la matriz
    cantidad_filas = int(input("¿Cuántas filas tiene la matriz " + nombre + "?: "))
    cantidad_columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre + "?: "))

    print("Voy a ingresar los valores de la matriz " + nombre + ":")
    nueva_matriz = []  # Aquí voy a guardar toda la matriz

    for num_fila in range(cantidad_filas):
        fila_actual = []  # Esta lista guarda los valores de una fila
        for num_columna in range(cantidad_columnas):
            mensaje = "Valor en la posición [" + str(num_fila) + "][" + str(num_columna) + "]: "
            numero = float(input(mensaje))  # Ingreso el número y lo guardo
            fila_actual.append(numero)
        nueva_matriz.append(fila_actual)  # Agrego la fila completa a la matriz

    return nueva_matriz, cantidad_filas, cantidad_columnas


# Esta función me permite mostrar una matriz por pantalla
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for numero in fila:
            linea += str(numero) + "  "  # Uno los números con espacio
        print(linea)


# Esta función calcula la matriz transpuesta
def transponer_matriz(matriz_original):
    total_filas = len(matriz_original)
    total_columnas = len(matriz_original[0])
    matriz_transpuesta = []  # Aquí guardo la nueva matriz con filas y columnas intercambiadas

    for numero_columna in range(total_columnas):
        nueva_fila = []
        for numero_fila in range(total_filas):
            valor = matriz_original[numero_fila][numero_columna]
            nueva_fila.append(valor)
        matriz_transpuesta.append(nueva_fila)

    return matriz_transpuesta


# Parte principal del codigo
print("Este programa muestra la matriz transpuesta de una matriz ingresada")

# Ingreso de la matriz original
matriz_usuario, filas_ingresadas, columnas_ingresadas = ingresar_matriz("Original")

# Valido que tenga al menos una fila y una columna
if filas_ingresadas < 1 or columnas_ingresadas < 1:
    print("No se puede continuar. La matriz debe tener por lo menos una fila y una columna.")
else:
    # Calculo la matriz transpuesta
    transpuesta = transponer_matriz(matriz_usuario)

    print("Matriz original:")
    mostrar_matriz(matriz_usuario)

    print("Matriz transpuesta:")
    mostrar_matriz(transpuesta)
```
4. Desarrollar un programa que sume los elementos de una columna dada de una matriz.
```python
# Esta función me permite ingresar todos los datos de una matriz
def ingresar_matriz(nombre):
    # Pregunto primero cuántas filas y columnas tendrá la matriz
    cantidad_filas = int(input("¿Cuántas filas tiene la matriz " + nombre + "?: "))
    cantidad_columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre + "?: "))

    print("Voy a ingresar los valores de la matriz " + nombre + ":")
    nueva_matriz = []  # Aquí voy a guardar toda la matriz

    for numero_fila in range(cantidad_filas):
        fila_actual = []  # Esta lista guarda los valores de una fila
        for numero_columna in range(cantidad_columnas):
            texto = "Valor en la posición [" + str(numero_fila) + "][" + str(numero_columna) + "]: "
            numero = float(input(texto))
            fila_actual.append(numero)
        nueva_matriz.append(fila_actual)  # Agrego la fila completa a la matriz

    return nueva_matriz, cantidad_filas, cantidad_columnas


# Esta función muestra una matriz ya armada
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for numero in fila:
            linea += str(numero) + "  "  # Uno los valores con espacio
        print(linea)


# Esta función me permite sumar todos los valores de una columna específica
def sumar_una_columna(matriz, numero_columna):
    suma_total = 0  # Aquí voy sumando los valores
    for fila in matriz:
        suma_total = suma_total + fila[numero_columna]  # Tomo el número en esa columna
    return suma_total


# Parte principal del codigo 
print("Este programa suma los valores de una columna de una matriz")

# Primero ingreso la matriz
matriz_usuario, total_filas, total_columnas = ingresar_matriz("A")

# Muestro la matriz para que el usuario se ubique
print("La matriz ingresada es:")
mostrar_matriz(matriz_usuario)

# Pido al usuario cuál columna quiere sumar
columna_elegida = int(input("¿Qué número de columna desea sumar? (empieza desde 0): "))

# Verifico si la columna existe
if columna_elegida < 0 or columna_elegida >= total_columnas:
    print("No se puede hacer la suma. Ese número de columna no existe.")
else:
    resultado = sumar_una_columna(matriz_usuario, columna_elegida)
    print("La suma de todos los valores en la columna " + str(columna_elegida) + " es: " + str(resultado))
```
5. Desarrollar un programa que sume los elementos de una fila dada de una matriz.
```python
# Esta función me permite ingresar los datos de una matriz
def ingresar_matriz(nombre):
    # Primero pregunto cuántas filas y columnas tiene la matriz
    cantidad_filas = int(input("¿Cuántas filas tiene la matriz " + nombre + "?: "))
    cantidad_columnas = int(input("¿Cuántas columnas tiene la matriz " + nombre + "?: "))

    print("Ahora voy a ingresar los valores de la matriz " + nombre + ":")
    nueva_matriz = []  # Aquí guardo la matriz completa

    for numero_fila in range(cantidad_filas):
        fila_actual = []  # Lista para guardar los valores de esta fila
        for numero_columna in range(cantidad_columnas):
            texto = "Valor en la posición [" + str(numero_fila) + "][" + str(numero_columna) + "]: "
            numero = float(input(texto))
            fila_actual.append(numero)
        nueva_matriz.append(fila_actual)

    return nueva_matriz, cantidad_filas, cantidad_columnas


# Esta función me permite mostrar la matriz completa
def mostrar_matriz(matriz):
    for fila in matriz:
        linea = ""
        for numero in fila:
            linea += str(numero) + "  "
        print(linea)


# Esta función suma todos los elementos de una fila que el usuario indique
def sumar_una_fila(matriz, numero_fila):
    suma_total = 0  # Aquí voy a acumular la suma de los valores

    fila_seleccionada = matriz[numero_fila]  # Tomo la fila que quiero sumar

    for numero in fila_seleccionada:
        suma_total = suma_total + numero  # Voy sumando uno por uno

    return suma_total


# --- Parte principal del programa ---
print("Este programa suma los valores de una fila de una matriz")

# Ingreso de datos de la matriz
matriz_usuario, total_filas, total_columnas = ingresar_matriz("A")

# Muestro la matriz para que el usuario sepa qué fila escoger
print("La matriz ingresada es:")
mostrar_matriz(matriz_usuario)

# Pregunto al usuario qué fila desea sumar
fila_elegida = int(input("¿Qué número de fila desea sumar? (empieza desde 0): "))

# Verifico que la fila exista
if fila_elegida < 0 or fila_elegida >= total_filas:
    print("No se puede hacer la suma. Ese número de fila no existe.")
else:
    resultado = sumar_una_fila(matriz_usuario, fila_elegida)
    print("La suma de todos los valores en la fila " + str(fila_elegida) + " es: " + str(resultado))
```
