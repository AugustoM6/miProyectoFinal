import os

rutas = ["Coronado - San José", "Ipís - San José", "Purral - San José", "El Carmen - San José", "Mozotal - San José"]
precios = ["Tiquete sencillo: 500 colones", "Tiquetes por un día: 1000 colones", "Tiquetes Semanales: 7000 colones"]
asientos_ocupados_por_ruta = [
    [['', ''], ['', ''], ['', ''], ['', ''], ['', '']],
    [['', ''], ['', ''], ['', ''], ['', ''], ['', '']],
    [['', ''], ['', ''], ['', ''], ['', ''], ['', '']],
    [['', ''], ['', ''], ['', ''], ['', ''], ['', '']],
    [['', ''], ['', ''], ['', ''], ['', ''], ['', '']]
]

espacios_disponibles_por_ruta = [
    [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]],
    [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]],
    [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]],
    [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]],
    [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10]]
]

def mostrar_rutas():
    print("Rutas disponibles:")
    for x in range(len(rutas)):
        print(f"{x + 1}. {rutas[x]}")

def mostrar_precios():
    print("Opciones de compra:")
    for x in range(len(precios)):
        print(f"{x + 1}. {precios[x]}")

def mostrar_espacios_disponibles(ruta_seleccionada):
    print(f"Espacios disponibles para la ruta {rutas[ruta_seleccionada]}:")
    for x in espacios_disponibles_por_ruta[ruta_seleccionada]:
        valores = ''
        for y in x:
            valores += str(y) + " "
        print(valores[:-1])

def marcar_asiento_ocupado(ruta_seleccionada, asiento_seleccionado):
    x = asiento_seleccionado // 2
    y = asiento_seleccionado % 2

    if asientos_ocupados_por_ruta[ruta_seleccionada][x][y] == '':
        espacios_disponibles_por_ruta[ruta_seleccionada][x][y] = 'O'
        return True
    else:
        print(" El asiento ya está ocupado. Seleccione otro, por favor .")
        return False
def adquirir_tiquetes():
    mostrar_rutas()
    ruta_seleccionada = int(input("Seleccione la ruta (1-5): ")) - 1
    mostrar_precios()
    tipo_tiquete = int(input("Seleccione el tipo de tiquete (1-3): \n")) - 1
    cantidad_tiquetes = int(input("Ingrese la cantidad de tiquetes que desea comprar: \n"))

    print(f"\nEspacios disponibles para la ruta {rutas[ruta_seleccionada]}:")
    mostrar_espacios_disponibles(ruta_seleccionada)
    print("Seleccione el número del asiento (1-10): \n")
    for x in range(cantidad_tiquetes):
        while True:
            asiento_seleccionado = int(input()) - 1
            if marcar_asiento_ocupado(ruta_seleccionada, asiento_seleccionado):
                break

    subtotal = cantidad_tiquetes * (tipo_tiquete + 1) * 500
    iva = int(subtotal * 0.13)
    total = int(subtotal + iva)

    print("\nFactura:")
    print(f"Cantidad de tiquetes: {cantidad_tiquetes}")
    print(f"Tipo de tiquete: {precios[tipo_tiquete]}")
    print(f"Subtotal: {subtotal} colones")
    print(f"Total del IVA: {iva} colones")
    print(f"Total a pagar: {total} colones")

    generar_factura(cantidad_tiquetes, tipo_tiquete, subtotal, iva, total)

def generar_factura(cantidad_tiquetes, tipo_tiquete, subtotal, iva, total):
    archivo_factura = open("factura.txt", "w")
    archivo_factura.write(f"Cantidad de tiquetes: {cantidad_tiquetes}\n")
    archivo_factura.write(f"Tipo de tiquete: {precios[tipo_tiquete]}\n")
    archivo_factura.write(f"Subtotal: {subtotal} colones\n")
    archivo_factura.write(f"Total del IVA: {iva} colones\n")
    archivo_factura.write(f"Total a pagar: {total} colones\n")
    archivo_factura.close()

while True:
    print("\nMenú Principal:")
    print("1. Ver rutas")
    print("2. Ver precios")
    print("3. Adquirir tiquete(s)")
    print("4. Mostrar espacios disponibles")
    print("5. Salir")

    opcion = input("Seleccione una opción (1-5): ")
    if opcion == '1':
        mostrar_rutas()
    elif opcion == '2':
        mostrar_precios()
    elif opcion == '3':
        adquirir_tiquetes()
    elif opcion == '4':
        ruta_seleccionada = int(input("Seleccione la ruta (1-5): ")) - 1
        mostrar_espacios_disponibles(ruta_seleccionada)
    elif opcion == '5':
        print("Gracias por su compra. ¡Buen Viaje!")
        break
    else:
        print("Opción no válida. Por favor, seleccione una opción válida.")
