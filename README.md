# black-jack
Mi dirección de github para este repositorio:
https://github.com/carmenm02/black-jack.git
Mi diagrama de flujo es el siguiente:
<img width="898" alt="Captura de pantalla 2021-11-23 a las 17 32 08" src="https://user-images.githubusercontent.com/91721886/143065437-99970588-f815-4f6c-b3ef-9b7b678c5e8b.png">
El codigo que he usado es:

from random import choice, sample

cartas = {
    chr(0x1f0a1): 11,
    chr(0x1f0a2): 2,
    chr(0x1f0a3): 3,
    chr(0x1f0a4): 4,
    chr(0x1f0a5): 5,
    chr(0x1f0a6): 6,
    chr(0x1f0a7): 7,
    chr(0x1f0a8): 8,
    chr(0x1f0a9): 9,
    chr(0x1f0aa): 10,
    chr(0x1f0ab): 10,
    chr(0x1f0ad): 10,
    chr(0x1f0ae): 10,
}

print("Cartas: {}".format(" ".join(cartas.keys())))
print("Puntos: {}".format(list(cartas.values())))

print("1\ Iteración estándar sobre un diccionario")
for carta, valor in cartas.items():
    print("la carta {} vale {}".format(carta, valor))

partidas = int(input("¿Cuantas quieres jugar?: "))
primera=0
while partidas != primera:
    lista = list(cartas)
    print("Seleccionó: ", end=" ")
    carta = choice(lista)
    score = cartas[carta]
    print(carta, end=" ")

print("2\ Iteración ordenada sobre un diccionario")
for carta in sorted(cartas.keys()):
    print("la carta {} vale {}".format(carta, cartas[carta]))

print("3\ Black Jack")
lista_cartas = list(cartas)

print("Ha seleccionado:", end=" ")
carta = choice(lista_cartas)
score = cartas[carta]
print(carta, end=" ")
carta = choice(lista_cartas)
score += cartas[carta]
print(carta, end=" ")
print(" >>> su puntuación es de", score)

main_banca = sample(lista_cartas, 2)
score_banca = sum(cartas[carta] for carta in main_banca)
print("La banca tiene: {} {}  >> su score es {}".format(main_banca[0],main_banca[1], score_banca))
