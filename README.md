import time
import os

# Cores em ANSI escape code
VERMELHO = "\033[91m"
LARANJA = "\033[38;5;208m"
RESET = "\033[0m"

# Letreiro com o nome "Fahrenheit"
letreiro = [
    "*************",
    "* Fahrenheit *",
    "*************"
]

# Função para imprimir o letreiro com efeito piscante
def imprimir_letreiro():
    for linha in letreiro:
        for char in linha:
            if char == "*":
                print(VERMELHO + "*" + RESET, end="")
            else:
                print(LARANJA + char + RESET, end="")
        print()
    time.sleep(0.5)  # Aguarda 0,5 segundos
    os.system("cls" if os.name == "nt" else "clear")  # Limpa a tela

# Loop infinito para manter o letreiro piscante
while True:
    imprimir_letreiro()
