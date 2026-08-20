#include <iostream>
using namespace std;

int main() {
    int pilihan_menu, jumlah_pesanan;
    long total_harga, diskon, harga_akhir;
    char layani_lagi;

    // 1. INTEGRASI: Perulangan (Do-While) sebagai "Jantung" program
    // Agar program terus hidup melayani pelanggan baru tanpa harus ditutup-buka
    do {
        // Inisialisasi ulang total harga setiap pelanggan baru
        total_harga = 0; 
        
        cout << "\n===================================" << endl;
        cout << "      KASIR KEDAI KOPI SENJA       " << endl;
        cout << "===================================" << endl;
        
        // 2. INTEGRASI: Sekuensial (Menampilkan informasi berurutan)
        cout << "1. Kopi Hitam     (Rp 10.000)" << endl;
        cout << "2. Cappuccino     (Rp 15.000)" << endl;
        cout << "3. Roti Bakar     (Rp 12.000)" << endl;
        cout << "4. Mie Goreng     (Rp 18.000)" << endl;
        cout << "-----------------------------------" << endl;
        
        cout << "Pilih nomor menu (1-4): ";
        cin >> pilihan_menu;
        
        cout << "Jumlah pesanan        : ";
        cin >> jumlah_pesanan;

        // 3. INTEGRASI: Percabangan & Operator (Menentukan harga)
        switch(pilihan_menu) {
            case 1:
                total_harga = 10000 * jumlah_pesanan;
                break;
            case 2:
                total_harga = 15000 * jumlah_pesanan;
                break;
            case 3:
                total_harga = 12000 * jumlah_pesanan;
                break;
            case 4:
                total_harga = 18000 * jumlah_pesanan;
                break;
            default:
                cout << "[ERROR] Pilihan menu tidak tersedia!" << endl;
                total_harga = 0; // Hindari perhitungan acak
        }

        // Cek jika menu yang diinput valid (total harga > 0)
        if (total_harga > 0) {
            cout << "\nSubtotal Belanja : Rp " << total_harga << endl;

            // 4. INTEGRASI: Logika Diskon (Percabangan Bersyarat)
            // Jika subtotal di atas Rp 50.000, dapat diskon 10%
            if (total_harga > 50000) {
                diskon = total_harga * 10 / 100; // Operator matematika (10%)
                cout << "Diskon (10%)     : Rp " << diskon << endl;
            } else {
                diskon = 0; // Tidak dapat diskon
            }

            harga_akhir = total_harga - diskon;

            cout << "-----------------------------------" << endl;
            cout << "TOTAL BAYAR      : Rp " << harga_akhir << endl;
            cout << "===================================" << endl;
        }

        // 5. Syarat Perulangan
        cout << "\nApakah ada pelanggan selanjutnya? (y/n): ";
        cin >> layani_lagi;

    } while (layani_lagi == 'y' || layani_lagi == 'Y');

    // Keluar dari perulangan
    cout << "\nSistem Dimatikan. Terima Kasih." << endl;

    return 0;
}
