# React Todo App

Aplikasi To-Do List sederhana yang dibuat dengan React dan Vite. Proyek ini dibuat sebagai latihan untuk memahami dasar-dasar React, seperti komponen, state, dan penanganan event.

## Fitur

- Menambah tugas baru
- Menandai tugas sebagai selesai atau belum selesai
- Menghapus tugas

## Teknologi

- [React](https://react.dev/)
- [Vite](https://vite.dev/)

## Prasyarat

Pastikan Node.js versi 18 atau lebih baru sudah terpasang di komputer Anda.

```bash
node -v
```

## Instalasi

1. Clone repository ini:

```bash
   git clone https://github.com/username/react-todo-app.git
```

2. Masuk ke folder proyek:

```bash
   cd react-todo-app
```

3. Pasang dependensi:

```bash
   npm install
```

4. Jalankan aplikasi:

```bash
   npm run dev
```

5. Buka `http://localhost:5173` di browser.

## Perintah yang Tersedia

| Perintah          | Fungsi                                  |
| ----------------- | --------------------------------------- |
| `npm run dev`     | Menjalankan server pengembangan         |
| `npm run build`   | Membuat versi produksi di folder `dist` |
| `npm run preview` | Melihat hasil build secara lokal        |

## Struktur Proyek

```
react-todo-app/
├── public/
├── src/
│   ├── App.jsx       # Komponen utama dan logika aplikasi
│   ├── App.css       # Gaya untuk komponen App
│   ├── main.jsx      # Titik masuk aplikasi
│   └── index.css     # Gaya global
├── index.html
├── package.json
└── vite.config.js
```

## Cara Kerja

Aplikasi menyimpan daftar tugas dalam state menggunakan `useState`. Setiap tugas berbentuk objek dengan tiga properti:

```js
{ id: 1700000000000, text: "Belajar React", done: false }
```

Tiga fungsi utama mengelola daftar tersebut:

- `addTask` menambahkan tugas baru ke daftar.
- `toggleTask` mengubah status selesai sebuah tugas.
- `deleteTask` menghapus tugas dari daftar.

## Rencana Pengembangan

- [ ] Menyimpan data ke `localStorage`
- [ ] Fitur edit tugas
- [ ] Filter tugas (semua, selesai, belum selesai)
- [ ] Memecah kode menjadi komponen yang lebih kecil

## Kontribusi

Saran dan perbaikan sangat diterima. Silakan buka *issue* atau kirim *pull request*.

## Lisensi

Proyek ini menggunakan lisensi [MIT](LICENSE).
