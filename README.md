# 📝 Aplikasi To-Do Sederhana dengan React

Panduan langkah demi langkah untuk membuat aplikasi **To-Do List** sederhana menggunakan **React** dan **Vite**. Cocok untuk pemula yang baru belajar React.

## ✨ Fitur

- Menambah tugas baru
- Menandai tugas selesai / belum selesai
- Menghapus tugas

## 🧰 Prasyarat

Pastikan sudah terpasang:

- [Node.js](https://nodejs.org/) versi 18 atau lebih baru
- npm (sudah termasuk dalam Node.js)
- Code editor, misalnya [VS Code](https://code.visualstudio.com/)

Cek versi dengan perintah:

```bash
node -v
npm -v
```

## 🚀 Membuat Proyek

1. Buat proyek baru menggunakan Vite:

   ```bash
   npm create vite@latest todo-app -- --template react
   ```

2. Masuk ke folder proyek dan pasang dependensi:

   ```bash
   cd todo-app
   npm install
   ```

3. Jalankan server pengembangan:

   ```bash
   npm run dev
   ```

4. Buka alamat yang muncul di terminal (biasanya `http://localhost:5173`).

## 📁 Struktur Folder

```
todo-app/
├── public/
├── src/
│   ├── App.jsx        # Komponen utama
│   ├── App.css        # Gaya untuk App
│   ├── main.jsx       # Titik masuk aplikasi
│   └── index.css
├── index.html
├── package.json
└── vite.config.js
```

## 💻 Menulis Kode

### 1. Ganti isi `src/App.jsx`

```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [tasks, setTasks] = useState([]);
  const [input, setInput] = useState("");

  const addTask = () => {
    if (input.trim() === "") return;
    setTasks([...tasks, { id: Date.now(), text: input, done: false }]);
    setInput("");
  };

  const toggleTask = (id) => {
    setTasks(
      tasks.map((task) =>
        task.id === id ? { ...task, done: !task.done } : task
      )
    );
  };

  const deleteTask = (id) => {
    setTasks(tasks.filter((task) => task.id !== id));
  };

  return (
    <div className="app">
      <h1>To-Do List</h1>

      <div className="input-group">
        <input
          type="text"
          value={input}
          placeholder="Tulis tugas baru..."
          onChange={(e) => setInput(e.target.value)}
          onKeyDown={(e) => e.key === "Enter" && addTask()}
        />
        <button onClick={addTask}>Tambah</button>
      </div>

      <ul>
        {tasks.map((task) => (
          <li key={task.id} className={task.done ? "done" : ""}>
            <span onClick={() => toggleTask(task.id)}>{task.text}</span>
            <button onClick={() => deleteTask(task.id)}>✕</button>
          </li>
        ))}
      </ul>

      {tasks.length === 0 && <p className="empty">Belum ada tugas.</p>}
    </div>
  );
}

export default App;
```

### 2. Ganti isi `src/App.css`

```css
.app {
  max-width: 420px;
  margin: 40px auto;
  padding: 24px;
  border-radius: 12px;
  background: #f5f5f5;
  color: #222;
  font-family: system-ui, sans-serif;
}

.input-group {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
}

.input-group input {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid #ccc;
  border-radius: 6px;
}

button {
  padding: 8px 12px;
  border: none;
  border-radius: 6px;
  background: #4f46e5;
  color: white;
  cursor: pointer;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 0;
  border-bottom: 1px solid #ddd;
}

li span {
  cursor: pointer;
}

li.done span {
  text-decoration: line-through;
  color: #888;
}

.empty {
  text-align: center;
  color: #888;
}
```

### 3. Bersihkan `src/index.css`

Hapus isinya atau sisakan reset sederhana agar tampilan tidak bentrok:

```css
body {
  margin: 0;
  background: #e5e7eb;
}
```

## 🧠 Konsep React yang Dipelajari

| Konsep | Penjelasan |
| --- | --- |
| **Komponen** | `App` adalah fungsi yang mengembalikan tampilan (JSX) |
| **State (`useState`)** | Menyimpan data yang bisa berubah, seperti daftar tugas |
| **Event handler** | `onClick`, `onChange`, dan `onKeyDown` untuk merespons aksi pengguna |
| **Rendering list** | `tasks.map()` dengan `key` unik untuk menampilkan daftar |
| **Conditional rendering** | `&&` untuk menampilkan pesan saat daftar kosong |

## 📦 Build untuk Produksi

```bash
npm run build
```

Hasil build ada di folder `dist/`. Untuk mencobanya secara lokal:

```bash
npm run preview
```

## 🌐 Deploy (Opsional)

Anda bisa mengunggah folder `dist/` ke layanan gratis seperti:

- [Netlify](https://www.netlify.com/)
- [Vercel](https://vercel.com/)
- [GitHub Pages](https://pages.github.com/)

## 🔧 Ide Pengembangan Lanjutan

- Simpan data ke `localStorage` agar tidak hilang saat halaman di-refresh
- Tambahkan fitur edit tugas
- Tambahkan filter (semua / selesai / belum selesai)
- Pisahkan kode menjadi komponen kecil (`TaskItem`, `TaskForm`)
- Coba tambahkan TypeScript atau Tailwind CSS

## 📚 Referensi

- [Dokumentasi React](https://react.dev/)
- [Dokumentasi Vite](https://vite.dev/)

## 📄 Lisensi

Bebas digunakan untuk belajar. Silakan modifikasi sesuai kebutuhan.
