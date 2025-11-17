Nama : Reza Afzaal Faizullah Taqy <br>
NRP : 5025241051 <br>
Kelas : A <br>
Tahun : 2025 <br>


<img width="479" height="400" alt="image" src="https://github.com/user-attachments/assets/c58bc163-db2e-4baa-8efa-e3ef9495079a" />
<img width="852" height="569" alt="image" src="https://github.com/user-attachments/assets/254eaf23-f653-460f-93fc-8954baeb1fcc" />



1. Class UserInput
```
class UserInput
{
    private Scanner scanner;

    public UserInput()
    {
        scanner = new Scanner(System.in);
    }

    public String read()
    {
        System.out.print("> ");
        return scanner.nextLine();
    }
}
```

Class UserInput digunakan untuk membaca input dari user melalui konsol.
Method read() menampilkan prompt ">" lalu mengembalikan teks yang diketik user.

2. Class BotResponder
```
class BotResponder
{
    private Random random;
    private HashMap<String, Integer> keywordMap;
    private String[] responses;
    private int lastIndex = -1;

```

Class BotResponder berfungsi menghasilkan respon otomatis.
Cara kerjanya:

Mendeteksi Keyword

Input user dipecah menjadi kata-kata.
Jika ada kata yang cocok dengan keyword, maka chatbot memberikan respon khusus.

Contoh keyword:

windows → "Windows moment."

mac → "Mac users never have this problem (they do)."

gpu / graphics → "Graphic card? Might be crying."

Jika Tidak Ada Keyword

Chatbot memilih jawaban acak, tetapi memastikan tidak mengulang jawaban sebelumnya.

initResponses()

Berisi daftar 15 respon unik.

initKeywords()

Memetakan kata kunci ke indeks response tertentu.

3. Class HelpDeskSystem
```
class HelpDeskSystem
{
    private UserInput input;
    private BotResponder responder;
```

Class HelpDeskSystem adalah inti program chatbot:

Fungsi utama:

Menampilkan pesan selamat datang

Membaca input user secara loop

Menghasilkan respon lewat BotResponder

Berhenti jika user mengetik "bye"

printWelcome()

Menampilkan judul & instruksi program.

printGoodbye()

Menampilkan pesan penutup.

4. Class HelpDeskApp (Main Class)
```
public class HelpDeskApp
{
    public static void main(String[] args)
    {
        HelpDeskSystem system = new HelpDeskSystem();
        system.start();
    }
}
```

Class HelpDeskApp adalah entry point.
Tugasnya hanya membuat objek HelpDeskSystem dan menjalankan chatbot.

5. Alur Program

Program menampilkan pesan sambutan "TechBuddy Assistant".

User memasukkan keluhan atau masalah komputer.

Sistem memeriksa apakah ada keyword pada input.

Jika keyword cocok → berikan respon spesifik.
Jika tidak → berikan respon acak.

User mengetik "bye".

Sistem menampilkan pesan perpisahan dan berhenti.
