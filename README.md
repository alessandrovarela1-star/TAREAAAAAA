# Maquina-Expendedora
saldo = 5.0

productos = {
    "1": ("Coca Cola", 2.5),
    "2": ("Galletas", 1.5),
    "3": ("Alfajor", 2.0)
}

while True:
    print("\n--- MAQUINA EXPENDEDORA ---")
    print(f"Saldo disponible: {saldo:.2f} Bs.")
    print("1. Coca Cola - 2.5 Bs.")
    print("2. Galletas - 1.5 Bs.")
    print("3. Alfajor - 2.0 Bs.")
    print("4. Salir")

    opcion = input("Seleccione una opción: ")

    if opcion == "4":
        print(f"Gracias por comprar. Saldo restante: {saldo:.2f} Bs.")
        break

    if opcion in productos:
        nombre, precio = productos[opcion]

        if saldo >= precio:
            saldo -= precio
            print(f"Has comprado: {nombre}")
            print(f"Saldo restante: {saldo:.2f} Bs.")
        else:
            print("Saldo insuficiente para comprar este producto.")
    else:
        print("Opción no válida.")

    if saldo < min(precio for _, precio in productos.values()):
        print("\nYa no tienes saldo suficiente para comprar más productos.")
        print(f"Saldo final: {saldo:.2f} Bs.")
        break
