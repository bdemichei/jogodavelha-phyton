# Jogo da Velha

def exibir_tabuleiro(tabuleiro):
    for linha in tabuleiro:
        print(" | ".join(linha))
        print("-" * 5)

def verificar_vitoria(tabuleiro, simbolo):
    #linhas, colunas e diagonais
    for i in range(3):
        if all([celula == simbolo for celula in tabuleiro[i]]) or \
           all([tabuleiro[j][i] == simbolo for j in range(3)]):
            return True
    if tabuleiro[0][0] == tabuleiro[1][1] == tabuleiro[2][2] == simbolo or \
       tabuleiro[0][2] == tabuleiro[1][1] == tabuleiro[2][0] == simbolo:
        return True
    return False

def jogo_da_velha():
    print("Bem-vindo ao Jogo da Velha!\n")
    
    jogador1 = input("Nome do Jogador 1 (X): ")
    jogador2 = input("Nome do Jogador 2 (O): ")
    
    jogadores = {"X": jogador1, "O": jogador2}
    
    tabuleiro = [[" " for _ in range(3)] for _ in range(3)]
    jogador_atual = "X"
    rodadas = 0

    while True:
        exibir_tabuleiro(tabuleiro)
        print(f"{jogadores[jogador_atual]} ({jogador_atual}), é a sua vez. Escolha a linha e a coluna (0 a 2):")
        
        try:
            linha = int(input("Linha: "))
            coluna = int(input("Coluna: "))
        except ValueError:
            print("Entrada inválida! Use apenas números de 0 a 2.")
            continue

        if linha not in range(3) or coluna not in range(3):
            print("Posição fora do tabuleiro. Tente novamente.")
            continue
        if tabuleiro[linha][coluna] != " ":
            print("Essa posição já está ocupada. Tente novamente.")
            continue

        tabuleiro[linha][coluna] = jogador_atual
        rodadas += 1

        if verificar_vitoria(tabuleiro, jogador_atual):
            exibir_tabuleiro(tabuleiro)
            print(f"Parabéns, {jogadores[jogador_atual]}! Você venceu!")
            break

        if rodadas == 9:
            exibir_tabuleiro(tabuleiro)
            print("Empate!")
            break

        jogador_atual = "O" if jogador_atual == "X" else "X"

if __name__ == "__main__":
    jogo_da_velha()
