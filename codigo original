conta_corrente = 0
extrato = ''
quant_saque = 3

def saque(valor, saldo):
    saldo -= valor
    print(f'Saque de R${valor:.2f} realizado com sucesso. Saldo atual: R${saldo:.2f}')
    
    return saldo

def deposito(valor, saldo):
    saldo += valor
    print(f'Depósito de R${valor:.2f} realizado com sucesso. Saldo atual: R${saldo:.2f}')
    
    return saldo

def exibir_extrato(saldo):
    print(extrato)
    print(f'\nSaldo atual: R${saldo:.2f}')

def menu(saldo):
    print(f'''
    ------------------------------------------    
          
    Selecione a opção de transação
    Seu saldo atual: R${saldo:.2f}
    SAQUE
    DEPÓSITO
    EXTRATO
    DIGITE 'STOP' PARA ENCERRAR O PROGRAMA!
    
    ------------------------------------------ 
''')

def obter_valor(mensagem):
    while True:
        try:
            valor = float(input(mensagem))
            return valor
        except ValueError:
            print("Transação inválida! Por favor, digite um número válido.")

print((f"{'_'*14}𝑩𝑨𝑵𝑪𝑶{'_'*14}").center(40))

while True:
    menu(conta_corrente)
    transacao = input('Digite aqui: ').upper()
    
    if transacao == 'STOP':
        break

    if transacao == 'SAQUE':
        while True: 
            print(f'Saques disponíveis: {quant_saque}')
            valor_saque = obter_valor('Valor do saque: ')

            if valor_saque > 500:
                print('-'*15 + 'SAQUE ULTRAPASSA DE LIMITE MÁXIMO' + '-'*15)
            elif valor_saque > conta_corrente:
                print('-'*15 + 'SALDO INSUFICIENTE PARA SAQUE' + '-'*15)
            elif quant_saque == 0:
                print('-'*15 + 'SAQUE INDISPONÍVEL, VOLTE AMANHÃ' + '-'*15)
                break
            elif valor_saque < 0:
                print('Transação inválida! Tente novamente')
            else:
                conta_corrente = saque(valor_saque, conta_corrente)
                extrato += f'Saque R${valor_saque}\n'
                quant_saque -= 1
                if input('DESEJA REALIZAR OUTRO SAQUE? S/N ').upper() == 'N':
                    break
    
    elif transacao == 'DEPOSITO':
        valor_deposito = obter_valor('Digite o valor do depósito: ')
        if valor_deposito < 0:
            print('Transação inválida! Tente novamente')
        else:
            conta_corrente = deposito(valor_deposito, conta_corrente)
            extrato += f'Depósito R${valor_deposito}\n'
        
    elif transacao == 'EXTRATO':
        exibir_extrato(conta_corrente)

    else:
        print('Transação inválida! Tente novamente')
