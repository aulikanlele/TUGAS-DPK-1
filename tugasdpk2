
#include <stdio.h>

char papan[3][3] = {
    {'1', '2', '3'},
    {'4', '5', '6'},
    {'7', '8', '9'}
};

void tampilkanPapan() {
    printf("\n");
    printf(" %c | %c | %c\n", papan[0][0], papan[0][1], papan[0][2]);
    printf("---+---+---\n");
    printf(" %c | %c | %c\n", papan[1][0], papan[1][1], papan[1][2]);
    printf("---+---+---\n");
    printf(" %c | %c | %c\n", papan[2][0], papan[2][1], papan[2][2]);
}

int cekPemenang() {
    for (int i = 0; i < 3; i++) {
        if (papan[i][0] == papan[i][1] &&
            papan[i][1] == papan[i][2])
            return 1;

        if (papan[0][i] == papan[1][i] &&
            papan[1][i] == papan[2][i])
            return 1;
    }

    if (papan[0][0] == papan[1][1] &&
        papan[1][1] == papan[2][2])
        return 1;

    if (papan[0][2] == papan[1][1] &&
        papan[1][1] == papan[2][0])
        return 1;

    return 0;
}

int main() {
    int posisi, baris, kolom;
    char pemain = 'X';
    int langkah = 0;

    printf("=== PERMAINAN TIC-TAC-TOE ===\n");
    printf("Pemain 1: X\n");
    printf("Pemain 2: O\n");

    while (langkah < 9) {
        tampilkanPapan();

        printf("\nGiliran pemain %c\n", pemain);
        printf("Pilih kotak (1-9): ");

        if (scanf("%d", &posisi) != 1) {
            printf("Input harus berupa angka!\n");
            while (getchar() != '\n');
            continue;
        }

        if (posisi < 1 || posisi > 9) {
            printf("Pilihan tidak valid!\n");
            continue;
        }

        baris = (posisi - 1) / 3;
        kolom = (posisi - 1) % 3;

        if (papan[baris][kolom] == 'X' ||
            papan[baris][kolom] == 'O') {
            printf("Kotak sudah terisi!\n");
            continue;
        }

        papan[baris][kolom] = pemain;
        langkah++;

        if (cekPemenang()) {
            tampilkanPapan();
            printf("\nPemain %c MENANG!\n", pemain);
            return 0;
        }

        if (pemain == 'X')
            pemain = 'O';
        else
            pemain = 'X';
    }

    tampilkanPapan();
    printf("\nPermainan SERI!\n");

    return 0;
}
