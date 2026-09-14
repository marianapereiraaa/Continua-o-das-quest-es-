# Continua-o-das-quest-es-

 questão 57:
def contar_caractere(string, caractere):
    print(string.count(caractere))
string = input("Digite uma string:")
caractere = input("Digite um caractere:")
contar_caractere(string, caractere)

Questão 58:
def calcular_gorjeta(conta): 
    gorjeta = conta * 0.10 
    print(f"Gorjeta: R$ {gorjeta:.2f}")

Questão 59: 
def escolher_numero(a, b):
    if a % 2 == 0 and b % 2 == 0:
        return min(a, b)
    else:
        return max(a, b)

a = int(input("Digite o primeiro número: "))
b = int(input("Digite o segundo número: "))

resultado = escolher_numero(a, b)

print("Resultado:", resultado)

Questão 60: 
def converter_temperatura(f):
    c = (5 / 9) * (f - 32)
    return c


f = float(input("Digite a temperatura em F: "))

resultado = converter_temperatura(f)

print("Temperatura em Celsius:", resultado)

Questão 61: 
def inverter(string):
    return string[::-1]


print(inverter("python2023"))
print(inverter("0203programacao2023"))
print(inverter("luz azul"))
print(inverter("arara rara"))
print(inverter("anotaram a data da maratona"))

Questão 62: 
def numero_perfeito(numero):
    soma = 0

    for i in range(1, numero):
        if numero % i == 0:
            soma += i
  
     return soma == numero 
numero = int(input("Digite um número: "))

if numero_perfeito(numero):
    print("É um número perfeito.")
else:
    print("Não é um número perfeito.")

Questão 63: 
def receber_numeros():
    numeros = []

    for i in range(5):
        numero = float(input("Digite um número: "))
        numeros.append(numero)

    return numeros

def maior_numero(numeros):
    maior = numeros[0]

    for numero in numeros:
        if numero > maior:
            maior = numero

    return maior

def menor_numero(numeros):
    menor = numeros[0]

    for numero in numeros:
        if numero < menor:
            menor = numero

    return menor

numeros = receber_numeros()

print("Maior número:", maior_numero(numeros))
print("Menor número:", menor_numero(numeros))


