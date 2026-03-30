# MinPro1PBW

# Tampilan Setiap Section/Fitur

### Tampilan Home
<img width="1895" height="905" alt="Screenshot 2026-03-30 215331" src="https://github.com/user-attachments/assets/86500893-ac28-49a8-871c-e94ea71eca8f" />

### Tampilan About & Experience
<img width="1898" height="864" alt="image" src="https://github.com/user-attachments/assets/59e9e311-bb93-4dce-9f5b-57dc71550830" />

### Tampilan Certificates
<img width="1901" height="903" alt="image" src="https://github.com/user-attachments/assets/769dc1aa-b707-4979-8bb4-39f3ef19953f" />


# Kode & Penjelasan Kode Setiap Section/Fitur

Kode:

```html
<!DOCTYPE html>
<html lang="id">

<head>
    <meta charset="UTF-8">
    <title>Portofolio Saya</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="style.css">
</head>

<body>

    <div id="app">

        <!-- Navbar -->
        <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
            <div class="container">
                <a class="navbar-brand" href="#">Portofolio</a>

                <button class="navbar-toggler" data-bs-toggle="collapse" data-bs-target="#menu">
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse" id="menu">
                    <ul class="navbar-nav ms-auto">
                        <li class="nav-item"><a class="nav-link" href="#home">Home</a></li>
                        <li class="nav-item"><a class="nav-link" href="#about">About</a></li>
                        <li class="nav-item"><a class="nav-link" href="#experience">Experience</a></li>
                        <li class="nav-item"><a class="nav-link" href="#certificates">Certificates</a></li>
                    </ul>
                </div>
            </div>
        </nav>

        <!-- Home -->
        <section id="home">
            <div class="container">
                <img src="img/profil.jpeg">
                <h1>{{ nama }}</h1>
                <p>{{ deskripsi }}</p>
            </div>
        </section>

        <!-- About -->
        <section id="about" class="py-5">
            <div class="container">
                <h2 class="text-center mb-4">About Me</h2>

                <p class="text-center">
                    Saya adalah Mahasiswi Prodi Sistem Informasi Universitas Mulawarman yang memiliki minat dalam
                    pengembangan website dan terus belajar teknologi baru.
                </p>

                <h4 class="mt-4">Skills</h4>

                <div class="mb-3" v-for="skill in skills">
                    <label>{{ skill.nama }}</label>
                    <div class="progress">
                        <div class="progress-bar" :style="{width: skill.level + '%'}">
                        </div>
                    </div>
                </div>

            </div>
        </section>

        <!-- Experience -->
        <section id="experience" class="py-5 bg-light">
            <div class="container">
                <h2 class="text-center mb-4">Experience</h2>

                <div class="list-group">
                    <div class="list-group-item" v-for="exp in experiences">
                        {{ exp }}
                    </div>
                </div>
            </div>
        </section>

        <!-- Certificates -->
        <section id="certificates" class="py-5">
            <div class="container">
                <h2 class="text-center mb-4">Certificates</h2>

                <div class="row">
                    <div class="col-md-4 mb-3" v-for="cert in certificates">
                        <div class="card h-100">
                            <img :src="cert.gambar">
                            <div class="card-body">
                                <h5 class="card-title">{{ cert.judul }}</h5>
                                <p class="card-text">{{ cert.deskripsi }}</p>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </section>

    </div>

    <!-- Vue -->
    <script src="https://unpkg.com/vue@3"></script>
    <script>
        const app = Vue.createApp({
            data() {
                return {
                    nama: "Marza Hanaya Melodya Goga",
                    deskripsi: "Mahasiswi Sistem Informasi Universitas Mulawarman",

                    skills: [
                        { nama: "Soft Skill", level: 90 },
                        { nama: "Basic Editing", level: 85 },
                        { nama: "Basic Programming", level: 75 }
                    ],

                    experiences: [
                        "Basic Programming",
                        "Basic Editing & Design (Canva, Coreldraw, Figma & Capcut)",
                        "Communication Skills",
                        "Team Collaboration"
                    ],

                    certificates: [
                        {
                            judul: "Study Club Soft Skill",
                            deskripsi: "Meningkatkan kemampuan komunikasi dan kerja sama tim.",
                            gambar: "img/sertif1.png"
                        },
                        {
                            judul: "INFORSA 2025",
                            deskripsi: "Sekretaris Bureau Entrepreneurship of Development INFORSA 2025 (administrasi & keuangan).",
                            gambar: "img/sertif2.png"
                        },
                        {
                            judul: "TAROT 2024",
                            deskripsi: "Anggota Humas & Dana MaKrab TAROT 2024 (administrasi & keuangan).",
                            gambar: "img/sertif3.png"
                        },
                        {
                            judul: "APLIKASI 2024",
                            deskripsi: "Peserta kegiatan pengenalan lingkungan kampus Sistem Informasi.",
                            gambar: "img/sertif4.jpg"
                        },
                        {
                            judul: "GEAR 2024",
                            deskripsi: "Peserta kegiatan pengenalan lingkungan kampus Fakultas Teknik.",
                            gambar: "img/sertif5.jpg"
                        },
                        {
                            judul: "APLIKASI 2025",
                            deskripsi: "Anggota Divisi Kesehatan & Konsumsi APLIKASI 2025.",
                            gambar: "img/sertif6.jpg"
                        }
                    ]
                }
            }
        })

        app.mount('#app')
    </script>

</body>

</html>

```

Penjelasan Kode:


Website portofolio ini memiliki beberapa bagian utama yaitu Navbar, Home, About Me, Experience, dan Certificates yang saling terhubung melalui menu navigasi. Navbar dibuat dengan bantuan Bootstrap sehingga tampil rapi dan tetap bisa digunakan dengan baik di berbagai ukuran layar. Pada bagian Home ditampilkan foto, nama, dan deskripsi singkat yang diambil dari data Vue JS sehingga mudah diubah tanpa mengedit langsung HTML. Bagian About Me berisi penjelasan diri serta daftar kemampuan yang ditampilkan dalam bentuk progress bar dengan persentase tertentu. Selanjutnya, Experience menampilkan daftar pengalaman atau kemampuan dalam bentuk list yang tersusun rapi. Pada bagian Certificates, ditampilkan beberapa sertifikat dalam bentuk card yang berisi gambar, judul, dan deskripsi. Secara keseluruhan, website ini menggunakan HTML sebagai kerangka utama, CSS untuk mempercantik tampilan, Bootstrap 5 untuk membantu desain yang responsif, serta Vue JS 3 untuk mengatur dan menampilkan data secara dinamis.

Teknologi yang digunakan:

Teknologi yang digunakan dalam pembuatan website portofolio ini adalah HTML sebagai struktur utama halaman, CSS untuk mengatur tampilan dan desain, Bootstrap 5 untuk membantu membuat layout yang rapi dan responsif, serta Vue JS 3 yang digunakan untuk mengelola dan menampilkan data secara dinamis seperti nama, skills, pengalaman, dan sertifikat.
