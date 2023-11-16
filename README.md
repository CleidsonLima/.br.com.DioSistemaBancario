# DioSistemaBancario
Sistema de saque, deposito e extrato bancário 


saldo = 1000.00
contador_saques = 0

def sacar():
    global saldo, contador_saques
    valor = float(input("Digite o valor que deseja sacar: "))
    if valor <= 0:
        print("Valor inválido. Tente novamente.")
    elif valor > saldo:
        print("Saldo insuficiente. Tente novamente.")
    elif valor > 500:
        print("Você só pode sacar até 500 reais por vez.")
    elif contador_saques >= 3:
        print("Você atingiu o limite de 3 saques.")
    else:
        saldo -= valor
        contador_saques += 1
        print(f'Foi sacado o valor: R${valor:.2f}')
        print(f'O valor restante em sua conta é: R${saldo:.2f}')

def depositar():
    global saldo
    valor = float(input("Digite o valor que deseja depositar: "))
    if valor <= 0:
        print("Valor inválido. Tente novamente.")
    else:
        saldo += valor
        print(f'Foi depositado o valor: R${valor:.2f}')

def mostrar_saldo():
    global saldo
    print(f'Seu saldo é: R${saldo:.2f}')

def main():
    while True:
        print("------------------------------------------------")
        operacao = int(input("Digite [1] para sacar, [2] para depositar, [3] para visualizar saldo ou qualquer outro valor para encerrar: "))
        if operacao == 1:
            sacar()
        elif operacao == 2:
            depositar()
        elif operacao == 3:
            mostrar_saldo()
        else:
            print("Muito obrigado por utilizar nosso serviço, até mais")
            break

main()
