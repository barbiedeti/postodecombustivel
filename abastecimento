import textwrap

def menu():
    selecao_menu = """ \n
    ===================== ESCOLHA O COMBUSTÍVEL =====================
    [1] - \tEtanol
    [2] - \tGasolina Comum
    [3] - \tGasolina Aditivada
    [4] - \tCancelar Abastecimento
    =================================================================
    """
    return input(textwrap.dedent(selecao_menu))
  

def valor_abastecimento (valor_litro, tipo_combustivel, quantidade_litros):
  
  #Descontos utilizando dicionário
  descontos = {
    "etanol": (0.02, 0.04),
    "gasolina comum": (0.03, 0.06),
    "gasolina aditivada": (0.04, 0.08)
  }

  #Valor do abastecimento
  if quantidade_litros <= 25:
    porc_desconto = descontos[tipo_combustivel][0]
  else:
    porc_desconto = descontos[tipo_combustivel][1]

  #Valor do desconto
  valor_desconto = valor_litro * porc_desconto

  #Valor total do abastecimento
  valor_total = (valor_litro - valor_desconto) * quantidade_litros

  return valor_total

#escolha do tipo de combustível
def tipo_combustivel():
   opcao = menu()
   if opcao == "1":
       return "etanol"
   elif opcao == "2":
       return "gasolina comum"
   elif opcao == "3":
       return "gasolina aditivada"
   elif opcao == "4":
       print("Abastecimento cancelado!")
       exit()
   else:
       print("Opção inválida!")
       return tipo_combustivel()
   
#caso o usuário utilize virgula (,) ao invés de ponto (.) na hora de inserir valor do litro
def entrada_litros(valor):
   return valor.replace(",", ".")

def main(): #interação com o usuário
    valor_litro = entrada_litros(input("Qual o valor do litro do combustível? "))
    valor_litro = float(valor_litro)
    combustivel = tipo_combustivel()
    quantidade_litros = float(input("Informe quantos litros deseja abastecer: "))

    #calcular valor
    abastecimento = valor_abastecimento(valor_litro, combustivel, quantidade_litros)

    #resultado
    print(f"O valor total do seu abastecimento é de R$ {abastecimento:.2f}")

if __name__ == "__main__":
    main()
