## 📄 `README.md` (untuk repo MongoDB)

````markdown
# 🛢️ MongoDB Setup for ToDo List API

Repository ini berisi dokumentasi dan skrip dasar untuk setup database MongoDB yang digunakan oleh proyek **ToDo List API** (dibuat menggunakan Go native).

---

## 📂 Struktur Database

- **Database**: `todolist`
- **Collection**: `notes`

---

## 📥 Cara Setup MongoDB (Linux)

### 1. Install MongoDB

```bash
sudo apt update
sudo apt install mongodb
````

### 2. Jalankan MongoDB

```bash
sudo systemctl start mongodb
sudo systemctl enable mongodb
```

### 3. Masuk ke Mongo Shell

```bash
mongosh
```

Jika menggunakan versi lama:

```bash
mongo
```

---

## 🗂️ Buat Database dan Collection

Setelah masuk ke MongoDB shell, jalankan perintah berikut:

```js
// Gunakan database todolist
use todolist

// Tambahkan 1 catatan awal
db.notes.insertOne({
  title: "Belajar MongoDB",
  done: false,
  created_at: new Date()
})

// Tampilkan semua data notes
db.notes.find().pretty()
```

---

## 🔍 Contoh Data

```json
{
  "_id": ObjectId("666f2f5fbe8f88d02a58207c"),
  "title": "Belajar MongoDB",
  "done": false,
  "created_at": ISODate("2025-06-15T07:25:00Z")
}
```

---

## 🎯 Struktur Koleksi (`notes`)

| Field        | Tipe       | Keterangan                    |
| ------------ | ---------- | ----------------------------- |
| `_id`        | `ObjectId` | ID unik (otomatis dari Mongo) |
| `title`      | `String`   | Judul catatan                 |
| `done`       | `Boolean`  | Status selesai atau belum     |
| `created_at` | `Date`     | Tanggal dibuat                |

---

## 🧩 Koneksi dengan Proyek Golang

Proyek Go akan terhubung ke MongoDB di URI:

```
mongodb://localhost:27017
```

Mengakses collection:

* Database: `todolist`
* Collection: `notes`

---

## 📁 Terkait

* [🔗 ToDo List API in Go (Native)](https://github.com/Aimannawal/Go-Todolist.git)

---

## 🧑‍💻 Dibuat oleh

Aiman Wafi’i An Nawal
SMK Telkom Sidoarjo – Backend Developer
