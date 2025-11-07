# Jogo de Pedra, Papel ou Tesoura
import random
opcoes = ["pedra", "papel", "tesoura"]

#Apresenta as regras do jogo

print("Saudações Amiga Querida! Vou-lhe apresentar o jogo de Pedra, Papel ou Tesoura. Esse jogo ocorre entre você e o computador!")
print("Cada jogadora escolhe entre Pedra, Papel ou Tesoura sendo que Pedra ganha de Tesoura, Papel ganha de Pedra, Tesoura ganha de Papel e se ambas escolhem a mesmo opção acontece um empate.")

#solicita da usuária quantas partidas serão
partidas = input("Insira o número de partidas: ")
while True:
  if partidas.isdigit():
    if int(partidas) > 0:
      break
    else:
      partidas = input("Número inválido! Digite Novamente: ")
  else:
    partidas = input("Número inválido! Digite novamente: ")

print(f"você escolheu {partidas} partidas ")

#placar
c = 0
u = 0

for i in range(0, int(partidas)):
  #escolhas realizadas pelas jogadoras
  jogada = str(input("Escolha entre Pedra, Papel ou Tesoura: ")).lower()

  while True:
    if jogada.lower() in opcoes:
      print(f"Você escolheu: {jogada}")
      break
    else:
      jogada = input("Jogada Inválida: Digite Novamente: ")

  # vez do computador
  jogada_computador = random.choice(opcoes)
  print(f"O computador escolheu: {jogada_computador}")

  #comparando as jogadas
  if jogada == jogada_computador:
    c = c + 0
    u = u + 0
    print(f"Houve um empate! {c} Vs. {u}")


  elif jogada == "pedra" and jogada_computador == "tesoura" or jogada == "papel" and jogada_computador == "pedra" or jogada == "tesoura" and jogada_computador == "papel" :
    u = u + 1
    print(f"A jogadora ganhou! {c} Vs. {u}")

  elif jogada_computador == "pedra" and jogada == "tesoura" or jogada_computador == "papel" and jogada == "pedra" or jogada_computador == "tesoura" and jogada == "papel":
    c = c + 1
    print(f"O computador ganhou! {c} Vs. {u}")

#averiguação dos resultados
if c > u:
  print("Resultado Final: O computador ganhou!")
elif u > c:
  print("Resultado Final: A usuária ganhou! Parabéns!")
else:
  print("Resultado Final: Houve um empate!!")

print(f"Muito obrigada por Jogar!")
