#include <iostream>
using namespace std;

int main() {
    string password_sistem = "NASA2026";
    string tebakan = ""; // Inisialisasi awal (kosong)

    cout << "=== SISTEM PELUNCURAN ROKET ===" << endl;

    // 1. Menggunakan WHILE untuk sistem keamanan
    // Selama tebakan TIDAK SAMA DENGAN password asli, terus berputar
    while (tebakan != password_sistem) {
        cout << "Masukkan Password Akses Peluncuran: ";
        cin >> tebakan;

        if (tebakan != password_sistem) {
            cout << "[ERROR] Akses Ditolak. Password salah!\n\n";
        }
    }

    // Jika berhasil keluar dari perulangan WHILE, artinya password benar!
    cout << "\n[SUCCESS] Akses Diterima." << endl;
    cout << "Memulai sekuens hitung mundur peluncuran...\n" << endl;

    // 2. Menggunakan FOR untuk hitung mundur
    // Inisialisasi (i = 10); Kondisi (selama i >= 1); Iterasi (i turun 1 setiap putaran)
    for (int i = 10; i >= 1; i--) {
        cout << "T - Minus : " << i << " detik" << endl;
        // Opsional: Dalam program asli, biasanya disisipkan jeda 1 detik di sini
    }

    cout << "\n🚀 BZZZ SHHHH BOOOM! ROKET MELUNCUR! 🚀" << endl;

    return 0;
}
