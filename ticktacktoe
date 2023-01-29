#include <iostream>
#include <array>

constexpr int board_size = 3;

enum class Player { X, O };

std::array<std::array<char, board_size>, board_size> board = {{{' ', ' ', ' '},
                                                               {' ', ' ', ' '},
                                                               {' ', ' ', ' '}}};

void print_board() {
    std::cout << "  A B C\n";
    for (int row = 0; row < board_size; ++row) {
        std::cout << row + 1 << " ";
        for (int col = 0; col < board_size; ++col) {
            std::cout << board[row][col] << " ";
        }
        std::cout << "\n";
    }
}

bool check_winner(Player player) {
    char symbol = (player == Player::X) ? 'X' : 'O';

    // Check rows
    for (int row = 0; row < board_size; ++row) {
        int count = 0;
        for (int col = 0; col < board_size; ++col) {
            if (board[row][col] == symbol) {
                ++count;
            }
        }
        if (count == board_size) {
            return true;
        }
    }

    // Check columns
    for (int col = 0; col < board_size; ++col) {
        int count = 0;
        for (int row = 0; row < board_size; ++row) {
            if (board[row][col] == symbol) {
                ++count;
            }
        }
        if (count == board_size) {
            return true;
        }
    }

    // Check diagonals
    int count = 0;
    for (int i = 0; i < board_size; ++i) {
        if (board[i][i] == symbol) {
            ++count;
        }
    }
    if (count == board_size) {
        return true;
    }

    count = 0;
    for (int i = 0; i < board_size; ++i) {
        if (board[i][board_size - i - 1] == symbol) {
            ++count;
        }
    }
    if (count == board_size) {
        return true;
    }

    return false;
}

bool make_move(Player player, int row, int col) {
    char symbol = (player == Player::X) ? 'X' : 'O';

    if (row >= 0 && row < board_size && col >= 0 && col < board_size && board[row][col] == ' ') {
        board[row][col] = symbol;
        return true;
    } else {
        return false;
    }
}

int main() {
    print_board();

    Player current_player = Player::X;
    while (true) {
        char column_char;
        int row;
        std::cout << "Player " << (current_player == Player
