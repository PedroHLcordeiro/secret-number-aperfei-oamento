# secret-number-aperfei-oamento
import random

print("*********************************")
print("Bem vindo ao jogo de Adivinhação!")
print("*********************************")
numero_secreto = random.randrange(1,101)
total_de_tentativas = 0
rodada = 1
pontos = 1000

print("escolha um nível : ")
print("(1) (2) ou (3)")

nível = int(input("escolha o nível:"))


if (nível == 1):
    total_de_tentativas = 20
elif (nível == 2):
    total_de_tentativas = 10
else:
    total_de_tentativas = 5

for rodada in range(1,total_de_tentativas + 1):
    print("Tentativa {} de {}".format(rodada, total_de_tentativas))

    chute_str = input("Digite um número que esteja entre 1 e 100: ")
    print("Você digitou " , chute_str)
    chute = int(chute_str)

    if (chute < 1 or chute > 100):
        print("burrão, tem que ser menor que 100 e maior que 1!")
        continue

    acertou = chute == numero_secreto
    maior = chute > numero_secreto
    menor = chute < numero_secreto

    if(acertou):
        print("Parabéns! Você acertou e fez {} pontos!".format(pontos))

        break
    else:
        if(maior):
            print("O seu chute foi maior do que o número secreto!")
        elif(menor):
            print("O seu chute foi menor do que o número secreto!")
        pontos_perdidos = abs(numero_secreto - chute)
        pontos = pontos - pontos_perdidos
        print("pontos")
    rodada = rodada + 1

print("Fim do jogo")
