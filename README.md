
# 📋 Kanban Lite: Aplikasi Manajemen Proyek Visual

**Kanban Lite** adalah aplikasi manajemen proyek sederhana berbasis Java yang menerapkan prinsip **Kanban Board**. Aplikasi ini memungkinkan pengguna untuk membuat proyek, menetapkan tugas, dan mengelola tim secara visual. Dibangun dengan paradigma **Object-Oriented Programming (OOP)** dan arsitektur **MVC (Model-View-Controller)**.

---

## 🎯 Tujuan Aplikasi

- 🗂️ Membantu tim dalam mengelola proyek dan tugas secara visual.
- 👥 Memisahkan peran antara manager dan member untuk pengalaman pengguna yang berbeda.
- 🧩 Menyediakan antarmuka login, registrasi, dan dashboard proyek yang lengkap.
- 🔄 Mendukung penambahan, pengeditan, dan manajemen proyek serta tim.

---

## 🏗️ Struktur Direktori & Kelas

```
├── src
│   └── main
│       ├── java
│       │   └── kanbanlitegradle
│       │       ├── controller
│       │       │   ├── DashboardManagerController.java
│       │       │   ├── DashboardMemberController.java
│       │       │   ├── DetailProyekController.java
│       │       │   ├── EditProyekController.java
│       │       │   ├── KanbanBoardController.java
│       │       │   ├── LoginController.java
│       │       │   ├── ManageTeamDialogController.java
│       │       │   ├── RegisterController.java
│       │       │   ├── StartMenuController.java
│       │       │   └── TambahProyekController.java
│       │       │
│       │       ├── model
│       │       │   ├── AppContext.java
│       │       │   ├── LocalDateAdapter.java
│       │       │   ├── Manager.java
│       │       │   ├── Member.java
│       │       │   ├── Project.java
│       │       │   ├── ProjectDataStore.java
│       │       │   ├── Task.java
│       │       │   ├── TaskStatus.java
│       │       │   ├── User.java
│       │       │   ├── UserAdapter.java
│       │       │   ├── UserDataStore.java
│       │       │   └── UserRegistry.java
│       │       │
│       │       └── Main.java
│
│       ├── resources
│       │   ├── css
│       │   │   └── style.css
│       │   ├── data
│       │   │   ├── projects.json
│       │   │   └── users.json
│       │   ├── DashboardManager.fxml
│       │   ├── DashboardMember.fxml
│       │   ├── DetailProyek.fxml
│       │   ├── EditProyek.fxml
│       │   ├── KanbanBoard.fxml
│       │   ├── Login.fxml
│       │   ├── ManageTeamDialog.fxml
│       │   ├── Register.fxml
│       │   ├── StartMenu.fxml
│       │   └── TambahProyek.fxml
│
├── build.gradle
└── gradle/
```

---

## 🧱 Deskripsi Kelas

### 🔹 User
Mewakili akun pengguna dalam sistem:
- `username`, `password`, `role` (Manager/Member)
- Digunakan untuk autentikasi dan otorisasi

### 🔹 Project
Mewakili proyek dalam sistem Kanban:
- `id`, `name`, `deskripsi`, `deadline`, `status`
- Menyimpan daftar `teamMembers` (List<String>) dan `tasks`

### 🔹 Task
Mewakili pekerjaan spesifik dalam proyek:
- `id`, `judul`, `deskripsi`, `status`, `assignedTo` (String username)
- Status: `"To Do"`, `"In Progress"`, `"Done"`

### 🗂 AppContext
Kelas singleton untuk menyimpan data global aplikasi selama runtime:
- `currentUser`, `currentProject`, `editable`, `projectList`

### 💾 UserDataStore & ProjectDataStore
Kelas utilitas untuk menyimpan dan memuat data:
- Menyimpan data `User` dan `Project` ke file JSON
- Menggunakan `Gson` untuk serialisasi dan deserialisasi

### 📅 LocalDateAdapter
Adaptor custom untuk menyimpan dan membaca tanggal `LocalDate` saat disimpan dalam file JSON

---

## 🧩 Controller & View (FXML)

### 📜 LoginController & RegisterController
- Mengatur proses login dan registrasi pengguna
- Registrasi menyimpan data ke file JSON

### 👤 DashboardMemberController
- Menampilkan daftar proyek untuk Member
- Hanya bisa melihat proyek yang melibatkan dirinya

### 👥 DashboardManagerController
- Menampilkan dan mengelola semua proyek
- Bisa menambah, mengedit, menghapus proyek dan task

### 📋 KanbanBoardController
- Menampilkan task dalam format Kanban Board
- Menyesuaikan akses berdasarkan peran dan keanggotaan

---

## 🕹 Fitur Utama

- ✅ Login & Registrasi dengan pemilihan peran (Manager / Member)
- 🛠️ Manajemen Proyek oleh Manager:
  - Tambah, edit, hapus proyek
  - Tambah, ubah status, hapus task
  - Tetapkan anggota tim (Member) ke proyek
- 👥 Dashboard Member:
  - Melihat daftar proyek yang diikuti
  - Membuka Kanban Board untuk proyeknya
  - Ubah status task jika ditugaskan ke dirinya
- 📋 Tampilan Kanban Board:
  - Menampilkan task berdasarkan status
  - Interaktif dan disesuaikan hak akses pengguna
- 💾 Penyimpanan permanen:
  - Semua data disimpan dalam file JSON
  - Data tidak hilang saat aplikasi ditutup

---

## ✍️ Author

| 👤 Nama                  | 🌐 Tugas                                                  |
|-------------------------|-----------------------------------------------------------|
| 😊 Abdul Jabbar Fanshurna | Mengembangkan controller dan `Main`                     |
| 🌸 Diani Annisah         | Menyusun dan mengembangkan struktur model                |
| 🧠 A. Alya Musaenab Asmin| Membuat tampilan (FXML), pengelolaan view, integrasi UI  |
