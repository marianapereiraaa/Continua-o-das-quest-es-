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
 
Questão 64: 

def calcular_soma(a, b, c):
    soma = a + b + c

    if soma > 21 and (a == 11 or b == 11 or c == 11):
        soma -= 10

    if soma > 21:
        return -1

    return soma


a = int(input("Digite o primeiro número: "))
b = int(input("Digite o segundo número: "))
c = int(input("Digite o terceiro número: "))

Questão 65: 
def calcularCubo(numero):
    return numero ** 3


def calcularDivisaoCubo(numero):
    if numero % 3 == 0:
        return calcularCubo(numero)
    else:
        return False

numero = int(input("Digite um número: "))

print(calcularDivisaoCubo(numero))

Questão 66: 
def calcular_animais(cabecas, pernas):
    coelhos = (pernas - (cabecas * 2)) // 2
    galinhas = cabecas - coelhos

    return coelhos, galinhas


coelhos, galinhas = calcular_animais(35, 94)

print("Coelhos:", coelhos)
print("Galinhas:", galinhas)

Questão 67: 
while True:
    try:
        idade = int(input("Digite sua idade: "))

        if idade < 0:
            raise ValueError

        break

    except ValueError:
        print("Digite uma idade válida.")

print("Idade:", idade)
 
Questão 68:
try:
    lucros = float(input("Digite os lucros: "))
    acionistas = int(input("Digite a quantidade de acionistas: "))

    resultado = lucros / acionistas

    print("Valor para cada acionista:", resultado)

except ZeroDivisionError:
    print("A quantidade de acionistas não pode ser zero.")

except ValueError:
    print("Digite apenas valores numéricos.")

Questão 69:
try:
    arquivo = open("relatorio_vendas.txt", "r")

    conteudo = arquivo.read()

    print(conteudo)

    arquivo.close()

except FileNotFoundError:
    print("O arquivo não foi encontrado.")

finally:
    print("Encerramento do recurso.")

Questão 70: 
def buscar_permissao(perfis, perfil, indice):
    try:
        return perfis[perfil][indice]
    except (KeyError, IndexError, TypeError):
        return "acesso_restrito"


perfis = {
    "admin": ["ler", "editar", "excluir"],
    "usuario": ["ler", "editar"]
}

print(buscar_permissao(perfis, "admin", 1))

Questão 71: 
class SaldoInsuficienteError(Exception):
    pass


def sacar(saldo, valor):
    if valor > saldo:
        raise SaldoInsuficienteError("Saldo insuficiente.")

    return saldo - valor


saldo = 500

try:
    valor = float(input("Digite o valor do saque: "))

    novo_saldo = sacar(saldo, valor)

    print("Saque realizado.")
    print("Novo saldo:", novo_saldo)

except SaldoInsuficienteError as erro:
    print(erro)

Questão 72: 
class SaldoInsuficienteError(Exception):
    pass


def sacar(saldo, valor):
    if valor > saldo:
        raise SaldoInsuficienteError("Saldo insuficiente.")

    return saldo - valor

Questão 73: 
precos = ["30", "50", "70"]

for preco in precos:
    try:
        valor = float(preco)

    except ValueError:
        print("Preço inválido.")

    else:
        desconto = valor * 0.10
        valor_final = valor - desconto

Questão 74: 
produtos = {
    1: "Notebook",
    2: "Celular",
    3: "Tablet"
}


def buscar_produto(id):
    try:
        produto = produtos[id]

        return {
            "status": 200,
            "produto": produto
        }

    except KeyError:
        return {
            "status": 404,
            "mensagem": "Produto não encontrado."
        }

    except Exception:
        return {
            "status": 500,
            "mensagem": "Erro interno do servidor."
        }


print(buscar_produto(1))
print(buscar_produto(10))

Questão 75: 
import time


def conectar_api():
  tentativas = 3
  for tentativa in range(1, tentativas + 1):
    try:
      
      print(f"Tentativa {tentativa} de conexão com a API...")
      raise ConnectionError("Falha na conexão com o servidor.")

    except ConnectionError as e:
      print(f"Erro capturado: {e}")
      if tentativa == tentativas:
        print(
            "Limite de 3 tentativas atingido. Falha na conexão. Encerrando de"
            " forma segura."
        )
        return False
      time.sleep(1)  
  return True

Questão 76: 
import traceback


def processar_dados(lista_elementos):
  resultados = []
  for item in lista_elementos:
    try:
      
      resultado = float(item) * 2
      resultados.append(resultado)
    except (TypeError, ValueError):
      print(
          f"[AUDITORIA] Erro ao processar o valor '{item}'. Detalhes técnicos:"
      )
      traceback.print_exc()  
      print("-" * 40)
  return resultados


 (válidos e inválidos)
dados = [10, "20", "abc", 40, None, "50.5"]
processar_dados(dados)

Questão 77: 
def realizar_saque(saldo, valor_saque):
  if valor_saque <= 0:
    raise ValueError("O valor do saque deve ser positivo.")
  if valor_saque > saldo:
    raise ValueError("Saldo insuficiente para realizar o saque.")
  
  novo_saldo = saldo - valor_saque
  return novo_saldo


saldo_atual = 1000.00
saques_para_testar = [200.00, -50.00, 1500.00]

for valor in saques_para_testar:
  try:
    print(f"\nTentando sacar R$ {valor:.2f}...")

Questão 78: 
def calcular_media(n1, n2, n3):
  
  if not all(isinstance(n, (int, float)) for n in [n1, n2, n3]):
    raise TypeError("As notas devem ser valores numéricos.")

 
  for nota in [n1, n2, n3]:
    if not (0 <= nota <= 10):
      raise ValueError("As notas devem estar estritamente entre 0 e 10.")

  media = (n1 + n2 + n3) / 3
  return media



entradas_teste = [(8.0, 9.0, 7.5), (11.0, 5.0, 6.0), ("8", 7.0, 9.0)]

for notas in entradas_teste:
  try:
    print(f"\nCalculando média para as notas: {notas}")
    media = calcular_media(*notas)
    print(f"Média calculada: {media:.2f}")

   
    if media >= 7.0:
      print("Situação: Aprovado!")
    elif media >= 5.0:
      print("Situação: Recuperação.")
    else:
      print("Situação: Reprovado.")

  except (ValueError, TypeError) as e:
    print(f"Erro nos dados informados: {e}")

Questão 79:
def cadastrar_produto(nome, preco, quantidade):
  if not isinstance(nome, str) or not nome.strip():
    raise ValueError("O nome do produto não pode ser vazio.")
  if preco <= 0:
    raise ValueError("O preço deve ser maior que zero.")
  if quantidade < 0:
    raise ValueError("A quantidade não pode ser negativa.")

  return f"Produto '{nome}' cadastrado com sucesso!"


testes_produtos = [
    ("Notebook", 3500.00, 10),
    ("", 150.00, 5),          
    ("Mouse", -50.00, 20),      
    ("Teclado", 100.00, -2)     
]

for p, pr, q in testes_produtos:
  try:
    mensagem = cadastrar_produto(p, pr, q)
    print(mensagem)
  except ValueError as e:
    print(f"Erro no cadastro: {e}")

Questão 80: 
class ProdutoInvalidoError(Exception):
  pass


class ValorInvalidoError(Exception):
  pass


class QuantidadeInvalidaError(Exception):
  pass



def registrar_venda(produto, preco, quantidade):
  if not isinstance(produto, str) or not produto.strip():
    raise ProdutoInvalidoError("O nome do produto não pode estar vazio.")

  try:
    preco_float = float(preco)
  except (ValueError, TypeError):
    raise ValorInvalidoError("O preço deve ser um número válido.")

  if preco_float <= 0:
    raise ValorInvalidoError("O preço deve ser maior que zero.")

  try:
    qtd_int = int(quantidade)
  except (ValueError, TypeError):
    raise QuantidadeInvalidaError(
        "A quantidade deve ser um número inteiro válido."
    )

  if qtd_int <= 0:
    raise QuantidadeInvalidaError("A quantidade deve ser um número inteiro positivo.")

  total_compra = preco_float * qtd_int
  return {
      "produto": produto,
      "preco": preco_float,
      "quantidade": qtd_int,
      "total": total_compra,
  }



def gerar_relatorio(vendas):
  if not vendas:
    print("\nNenhuma venda válida registrada hoje.")
    return

  total_vendas_realizadas = len(vendas)
  faturamento_total = sum(v["total"] for v in vendas)
  ticket_medio = faturamento_total / total_vendas_realizadas

 
  contagem_produtos = {}
  for v in vendas:
    prod = v["produto"]
    contagem_produtos[prod] = contagem_produtos.get(prod, 0) + v["quantidade"]

  produto_mais_vendido = max(contagem_produtos, key=contagem_produtos.get)

  print("\n====== RELATÓRIO DE VENDAS DIÁRIO ======")
  print(f"Quantidade total de vendas realizadas: {total_vendas_realizadas}")
  print(f"Produto mais vendido: {produto_mais_vendido}")
  print(f"Faturamento total da loja: R$ {faturamento_total:.2f}")
  print(f"Ticket médio por venda: R$ {ticket_medio:.2f}")
  print("========================================")



  vendas_validas = []

  print("--- Sistema de Registro de Vendas ---")
  print("Digite 'fim' no nome do produto para encerrar e gerar o relatório.\n")

  while True:
    try:
      produto = input("Nome do produto: ").strip()
      if produto.lower() == "fim":
        break

      preco_input = input("Preço unitário: ")
      qtd_input = input("Quantidade vendida: ")

     
      venda = registrar_venda(produto, preco_input, qtd_input)

    except (
        ProdutoInvalidoError,
        ValorInvalidoError,
        QuantidadeInvalidaError,
    ) as e:
      print(f"[ERRO DE VALIDAÇÃO]: {e}")
     
      try:
        with open("log_erros.txt", "a", encoding="utf-8") as log_file:
          log_file.write(f"Erro: {e}\n")
      except IOError:
        print("Não foi possível gravar no arquivo de log.")

    else:
      vendas_validas.append(venda)
      print(f"-> Venda de '{produto}' registrada com sucesso!\n")

    finally:
      print(
          "[STATUS]: Tentativa de registro processada.\n"
          + "-" * 35
      )
  gerar_relatorio(vendas_validas)

  if vendas_validas:
    try:
      with open("vendas.txt", "w", encoding="utf-8") as arquivo_vendas:
        for v in vendas_validas:
          arquivo_vendas.write(
              f"Produto: {v['produto']}, Preço: {v['preco']}, Qtd: {v['quantidade']}, Total: {v['total']}\n"
          )
      print("Dados salvos com sucesso em 'vendas.txt'.")
    except IOError:
      print("Erro ao tentar salvar o arquivo de vendas.")

