# Examen003D
import numpy as np

arreglo1 = np.empty((10,10),int)
arreglo2 = np.full((10,10),'asi')

opcion = 0
name = []
ape = []
fech = []
for x in range(0,10):
    for j in range(0,10):
        arreglo1[x][j]=cont      
        cont += 1
for x in range(0,10):
     for j in range(0,10):
        arreglo2[x][j]= str(arreglo1[x][j])   
        cont += 1
ruts = []

flag = True
while flag:
    print("Bienvenido a la venta de entradas del concierto de Michael Jam")
    print("1.- COMPRAR ENTRADAS")
    print("2.- MOSTRAR UBICACIONES DISPONIBLES")
    print("3.- VER LISTADO DE ASISTENTES")
    print("4.- MOSTRAR GANANCIAS TOTALES")
    print("5.- SALIR")
    opcion = int(input("\nIngrese una Opcion entre el 1 y 5:\n"))
    if opcion == 1:
        print("----------------\nComprar Entradas\n----------------")
        print("TIPO DE ASIENTO")
        print("Platinum(1-20)$120.000")
        print("Gold(21-50) $80.000")
        print("Silver(51-100)$50.000")
        try:
            cant_entradas= int(input("Cuantas entradas desea comprar? Maximo de 3 entradas:  "))
            if cant_entradas > 3:
                print("\nEl Maximo es solo de 3 entradas!!!\n")
            if cant_entradas <= 3:
                entradas = 0
                while entradas != cant_entradas:
                    print("___________\n|ESCENARIO|\n-----------")
                    print(arreglo2)
                    asiento = int(input("Seleccione un asiento: "))
                    total = 0
                    cantE = 0
                    totalSilver = 0
                    totalGold = 0
                    totalPlatinum = 0
                    gold = 0
                    platinum = 0
                    silver = 0
                    cont = 1
                    if asiento >=1 and asiento <=20:
                        total += 120000                    
                        platinum+=1
                        totalPlatinum +=120000
                        asiento = str(asiento)
                        if asiento in arreglo2:
                            f.Comprar_entradas(asiento,arreglo2)
                            run = int(input("Ingrese su run sin puntos ni DV: "))
                            ruts.append(run)
                            entradas+=1
                            input("Continuar")
                        else:
                            print("No está disponible")
                            input("Continuar")
                    elif asiento >= 21 and asiento <= 50:
                        total += 80000                    
                        gold+=1
                        totalGold +=80000
                        asiento = str(asiento)
                        if asiento in arreglo2:
                            f.Comprar_entradas(asiento,arreglo2)
                            run = int(input("Ingrese su run sin puntos ni DV: "))
                            ruts.append(run)
                            entradas+=1
                            input("Continuar")
                        else:
                            print("No está disponible")
                            input("Continuar")
                    elif asiento >=51 and asiento <= 100:
                        total += 50000                    
                        silver+=1
                        totalSilver +=50000
                        asiento = str(asiento)
                        if asiento in arreglo2:
                            f.Comprar_entradas(asiento)
                            run = int(input("Ingrese su run sin puntos ni DV: "))
                            ruts.append(run)
                            entradas+=1
                            input("Continuar")
                        else:
                            print("No está disponible")
                            input("Continuar")
        except:
            print("Ingrese un numero")
    elif opcion == 2:
        print(arreglo2)
    elif opcion == 3:
        try:
            print(f.mostrar_listado_asistentes(ruts))
        except:
            print("No existen datos")
    elif opcion == 4:
        try:
            print(f.mostrar_ganancias_totales(platinum,gold,silver,total,totalP,totalG,totalS))
        except:
            print("No existen datos")
    else:
        opcion == 5
        break
