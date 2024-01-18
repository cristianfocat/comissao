vendedores2=[]

def total_porc(preco, qtd):
    total = preco * qtd

    if total <= 1000:
      return 0

    elif total >= 1000 and total <= 5000:
      comissao = total * 0.05
      return comissao

    elif total >=5001 and total <=50000:
      comissao=total * 0.10
      return comissao

    elif total > 50000:
      comissao=total * 0.15
      return comissao

   

def porc(preco, qtd):
    total = preco * qtd

    if total <= 1000:
      return f'Sem'

    elif total >= 1000 and total <= 5000:
      comissao = total * 0.05
      return f'5%'

    elif total >=5001 and total <=50000:
      comissao=total * 0.10
      return f'10%'

    elif total > 50000:
      comissao=total * 0.15
      return f'15%'

def vendedore():

    vendedores = []
    nome=input("Nome: ")
    sobrenome=input("sobrenome: ")
    codigo=int(input('Codigo Produto: '))
    preco=float(input('Preço Peça: '))
    qtd=int(input('quantidade vendida: '))
    print(30*"=")
    print()
    valor1=total_porc(preco,qtd)
    valor2=porc(preco, qtd)
    r = f'Vendedor: {nome} {sobrenome}\n' \
        f'Código Produto: {codigo}\n' \
        f'Preço: {preco}\n' \
        f'Quantidade Vendida: {qtd}\n' \
        f'Total Vendido R$: {preco*qtd:.0f}\n' \
        f'Comissão de:{valor1} \n' \
        f'Porcentagem de Comissão: {valor2}'
    
    vendedores.append(r)
    vendedores2.append(vendedores)
    
    for x in vendedores2:
        for vv in x:
            print(vv)
            print()
            print(30*"=")
    print()
    continuar()


def continuar():
  print()
  cont=input('Quer continuar?: ').strip().lower()
  print()
  match cont:
    case 's':
      vendedore()
    case 'n':
      exit()
    case _:
      print('invalido!')
      vendedore()



vendedore()
