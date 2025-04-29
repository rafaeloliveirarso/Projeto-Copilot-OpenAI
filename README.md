# Projeto Copilot e OpenIA

Foi utilizado o Copilot para interagir e gerar exemplos práticos do que ele pode ser capaz.
Abaixo, a transcrição de cada solicitação.

---

### Crie um Jogo da Velha em Python

**Resposta:** Um jogo da velha simples que pode ser jogado no terminal entre dois jogadores humanos.

    def print_board(board):
    for row in board:
        print(" | ".join(row))
        print("-" * 5)


    def check_winner(board):
    for row in board:
        if row[0] == row[1] == row[2] and row[0] != " ":
            return row[0]

    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] and board[0][col] != " ":
            return board[0][col]

    if board[0][0] == board[1][1] == board[2][2] and board[0][0] != " ":
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] and board[0][2] != " ":
        return board[0][2]

    return None


    def is_full(board):
    return all(cell != " " for row in board for cell in row)


    def main():
    board = [[" " for _ in range(3)] for _ in range(3)]
    current_player = "X"

    while True:
        print_board(board)
        print(f"Vez do jogador {current_player}.")

        try:
            row = int(input("Escolha a linha (0-2): "))
            col = int(input("Escolha a coluna (0-2): "))
            if board[row][col] != " ":
                print("Espaço já ocupado. Tente novamente.")
                continue
        except (ValueError, IndexError):
            print("Entrada inválida. Tente novamente.")
            continue

        board[row][col] = current_player

        winner = check_winner(board)
        if winner:
            print_board(board)
            print(f"Jogador {winner} venceu!")
            break

        if is_full(board):
            print_board(board)
            print("Empate!")
            break

        current_player = "O" if current_player == "X" else "X"


    if __name__ == "__main__":
    main()


#### Como executar:
1. Certifique-se de ter o Python instalado (versão 3.x).
2. Salve o script fornecido no arquivo `jogo_da_velha.py`.
3. No terminal, execute o script:
   ```bash
   python jogo_da_velha.py

---

### Crie um script SQL para uma base de dados que armazene informações financeiras, como data, valor, local e descrição. Ideal para controlar os gastos de uma microempresa.
**Resposta:** Aqui está um exemplo de script SQL para criar uma base de dados que armazena informações de controle de gastos de uma Microempresa (ME). O banco de dados inclui os campos: Data, Valor, Local e Descrição.

Arquivo: controle_gastos.sql

Estrutura da Tabela:
data (Data do gasto)
valor (Valor do gasto)
local (Local onde ocorreu o gasto)
descricao (Descrição detalhada do gasto)

Como usar:
Crie o banco de dados executando o script SQL em seu sistema de gerenciamento de banco de dados (por exemplo, MySQL ou MariaDB).
Utilize comandos SQL para inserir, consultar ou atualizar os dados.

Exemplo de inserção:

    CREATE DATABASE ControleGastosME;

    USE ControleGastosME;
    
    CREATE TABLE Gastos (
        id INT AUTO_INCREMENT PRIMARY KEY,
        data DATE NOT NULL,
        valor DECIMAL(10, 2) NOT NULL,
        local VARCHAR(255),
        descricao TEXT
    );
    
    -- Exemplo de inserção de dados
    INSERT INTO Gastos (data, valor, local, descricao) 
    VALUES 
    ('2025-04-29', 150.75, 'Supermercado X', 'Compra de materiais de limpeza'),
    ('2025-04-28', 500.00, 'Fornecedor Y', 'Compra de matéria-prima'),
    ('2025-04-27', 30.50, 'Posto de combustível Z', 'Abastecimento do veículo');

---

### COMO ME ENCONTRAR?
[![LinkedIn](https://img.shields.io/badge/LinkedIn-000000?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rafaeloliveirarso/) 
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rafaeloliveirarso)
[![Gmail](https://img.shields.io/badge/Gmail-000000?style=for-the-badge&logo=gmail&logoColor=red)](mailto:rafael.silvaoliveira1992@gmail.com)
