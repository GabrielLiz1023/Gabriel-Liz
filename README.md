# Gabriel-Liz

import os

# Criar uma lista vazia para armazenar as tarefas
lista_de_tarefas = []

def limpar_tela():
    os.system('cls' if os.name == 'nt' else 'clear')

# Função para adicionar uma tarefa à lista
def adicionar_tarefa():
    tarefa = input("Digite a tarefa que deseja adicionar: ")
    lista_de_tarefas.append(tarefa)
    print(" ")
    print(f"Tarefa '{tarefa}' adicionada à lista.")

# Função para listar todas as tarefas
def listar_tarefas():
   
    print("Lista de tarefas:")
    print(" ")
    for i, tarefa in enumerate(lista_de_tarefas, start=1):
        print(f"{i}. {tarefa}")

# Função para remover uma tarefa da lista
def remover_tarefa():
    listar_tarefas()
    if lista_de_tarefas:
        try:
            indice = int(input("Digite o número da tarefa que deseja remover: ")) - 1
            if 0 <= indice < len(lista_de_tarefas):
                tarefa_removida = lista_de_tarefas.pop(indice)
                print(f"Tarefa '{tarefa_removida}' removida da lista.")
            else:
                print("Número de tarefa inválido.")
        except ValueError:
            print("Por favor, digite um número válido.")
    else:
        print("A lista de tarefas está vazia.")

# Loop principal do programa
while True:
    

    print("\nEscolha uma opção:")
    print(" ")
    print("1. Adicionar Tarefa")
    print("2. Listar Tarefas")
    print("3. Remover Tarefa")
    print("4. Sair")
    print(" ")
    opcao = input("Digite o número da opção: ")
    limpar_tela()

    if opcao == "1":
        adicionar_tarefa()
    elif opcao == "2":
        listar_tarefas()
    elif opcao == "3":
        remover_tarefa()
    elif opcao == "4":
        print("Saindo do programa.")
        break
    else:
        print("Opção inválida. Por favor, escolha uma opção válida.")
