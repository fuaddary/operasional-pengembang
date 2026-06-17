# Week 16 FP — Future of DevSecOps: Research-Driven Enhancement

**Mata Kuliah**: Operasional Pengembang (DevOps)
**Mode Belajar**: Mandiri + Kolaboratif (asinkronus)
**Durasi**: Bebas (demo minggu berikutnya via Zoom)

---

## Sebelum Mulai

Modul ini berbeda dari modul-modul sebelumnya.

Di modul sebelumnya, kamu mengikuti langkah-langkah yang sudah ada. Di sini, **kamu yang memimpin**. Tidak ada lab step-by-step. Tidak ada kode yang tinggal disalin. Yang ada adalah sebuah tantangan nyata:

> *"Kamu diberi kebebasan memilih teknologi DevSecOps masa depan yang ingin kamu eksplorasi. Tugasmu adalah menemukan literatur ilmiah yang mendukungnya, mengimplementasikan enhancement berdasarkan temuan tersebut, dan membuktikan bahwa peningkatan itu bekerja."*

Ini mensimulasikan apa yang dilakukan engineer senior ketika harus membuat keputusan teknis yang dapat dipertanggungjawabkan: **temukan literatur yang relevan, pahami state of the art, implementasikan, dan ukur hasilnya**.

---

## Bagian 1 — Apa yang Dimaksud "Future of DevSecOps"?

Pipeline yang kita bangun di modul-modul sebelumnya sudah berjalan. Tapi di dunia nyata, "berjalan" saja tidak cukup.

Riset terkini mengidentifikasi berbagai gap yang masih ada di sebagian besar pipeline DevSecOps. Beberapa arah yang sedang aktif diteliti dan dikembangkan komunitas:

| Area                              | Contoh Topik yang Relevan                                      |
| --------------------------------- | -------------------------------------------------------------- |
| **Observability**           | eBPF-based monitoring, distributed tracing, runtime security   |
| **Supply Chain Security**   | SBOM, artifact signing, provenance verification, SLSA          |
| **Developer Experience**    | Platform Engineering, Internal Developer Platform, Golden Path |
| **Deployment Intelligence** | GitOps, drift detection, declarative infrastructure            |
| **AI & Automation**         | AIOps, anomaly detection, AI-generated pipelines, MLOps        |
| **Policy as Code**          | OPA/Rego, admission controllers, compliance automation         |
| **Zero Trust**              | Service mesh security, mTLS, workload identity                 |
| **Chaos & Resilience**      | Chaos engineering, fault injection, SLO-based alerting         |

Daftar di atas bukan batasan — ini hanya contoh untuk membantu kamu melihat landscape yang ada. Jika kelompokmu menemukan topik lain yang relevan dengan DevSecOps dan didukung literatur ilmiah yang kuat, itu sepenuhnya valid.

---

## Bagian 2 — Proses Pemilihan Topik dan Paper

### Alur Hari Ini

```
Kelompok berdiskusi           Presentasi singkat        Dosen memberikan
dan memilih topik +    →      di kelas (5 menit    →   persetujuan atau
kandidat paper                per kelompok)             masukan
```

### Yang Harus Disiapkan untuk Diskusi Hari Ini

Setiap kelompok mempresentasikan **secara singkat** (5 menit, tidak perlu slide):

1. **Topik yang dipilih** — satu kalimat: *"Kami ingin meningkatkan pipeline dengan [X] karena gap [Y] yang kami identifikasi."*
2. **Dua kandidat paper** — judul, penulis, tahun, venue publikasi, dan satu kalimat mengapa paper ini relevan
3. **Enhancement yang direncanakan** — gambaran kasar: apa yang akan diimplementasikan berdasarkan paper tersebut

Dosen akan memberikan **lampu hijau** atau **masukan perbaikan** sebelum kelompok mulai implementasi.

---

## Bagian 3 — Kriteria Paper yang Valid

Karena paper dipilih sendiri, ada **kriteria wajib** yang harus dipenuhi. Paper yang tidak memenuhi kriteria ini akan diminta diganti sebelum implementasi dimulai.

### ✅ Kriteria Wajib (semua harus terpenuhi)

**1. Tahun publikasi: 2021–2025**
DevSecOps bergerak cepat. Paper yang lebih tua dari 5 tahun sering sudah tidak mencerminkan state of the art. Pengecualian hanya untuk paper foundational yang sangat berpengaruh (misalnya paper yang mendefinisikan konsep dasar) — tapi harus disertai satu paper terbaru sebagai pendampingnya.

**2. Diterbitkan di jurnal / conference bereputasi**
Minimal salah satu dari kategori berikut:

- Jurnal atau conference IEEE (ieeexplore.ieee.org)
- Jurnal atau conference ACM (dl.acm.org)
- Jurnal atau conference Springer/Elsevier yang terindeks Scopus atau Web of Science
- USENIX Security, NDSS, atau venue keamanan setara
- arXiv *hanya* jika paper sudah disubmit atau diterima di venue di atas (lihat bagian "Submitted to..." di halaman arXiv-nya)

**3. Ada metodologi yang jelas**
Paper harus bisa menjawab pertanyaan: *"Bagaimana penulis membuktikan klaimnya?"* — melalui eksperimen, studi kasus, systematic review, atau evaluasi empiris. Paper yang hanya berisi opini atau deskripsi tanpa metodologi tidak memenuhi kriteria ini.

**4. Ada sesuatu yang bisa diimplementasikan**
Paper harus menghasilkan sesuatu yang konkret untuk diimplementasikan — arsitektur, algoritma, tool, framework, atau metodologi yang bisa kamu terapkan dan ukur. Paper yang murni teoritis tanpa implikasi implementasi tidak cocok untuk tugas ini.

**5. Relevan dengan DevSecOps**
Topik paper harus terhubung dengan satu atau lebih tahap dalam pipeline DevSecOps: development, testing, security scanning, build, deployment, monitoring, atau operasional.

### ❌ Yang Bukan Paper Ilmiah Bereputasi

Sumber-sumber berikut **tidak bisa** dijadikan referensi ilmiah (tapi boleh digunakan sebagai panduan implementasi):

- Blog post, Medium article, atau artikel vendor
- Dokumentasi resmi tool (Kubernetes docs, GitHub Actions docs, dsb.)
- White paper dari perusahaan (AWS, Google Cloud, HashiCorp, dsb.)
- Laporan industri (CNCF Survey, State of DevOps Report, dsb.)
- Wikipedia atau sumber ensiklopedia

### 🔍 Cara Menemukan Paper yang Baik

Gunakan sumber-sumber ini untuk mencari:

- **Google Scholar** — scholar.google.com, filter "Since 2021"
- **IEEE Xplore** — ieeexplore.ieee.org
- **ACM Digital Library** — dl.acm.org
- **Semantic Scholar** — semanticscholar.org (bagus untuk melihat paper yang mengutip paper tertentu)
- **arXiv** — arxiv.org/list/cs.SE (Software Engineering) atau cs.CR (Cryptography and Security)

**Tips pencarian yang efektif:**

- Mulai dari nama teknologi + "survey" atau "systematic review" untuk mendapat gambaran besar
- Dari paper survey, ikuti referensi ke paper implementasi yang spesifik
- Cek bagian "Related Work" di paper yang sudah kamu temukan — biasanya mengarah ke paper penting lainnya
- Cari nama tool yang ingin kamu implementasikan + "evaluation" atau "performance"

---

## Bagian 4 — Yang Harus Diimplementasikan

### Prinsip Dasar

Enhancement yang kamu buat harus:

1. **Menjawab gap nyata** yang diidentifikasi paper — bukan sekadar menambahkan tool karena terlihat menarik
2. **Bisa diukur** — ada metrik sebelum dan sesudah yang menunjukkan improvement
3. **Terintegrasi dengan pipeline yang sudah ada** dari modul sebelumnya — bukan sistem yang berdiri sendiri
4. **Bisa dijalankan ulang oleh orang lain** dari README yang kamu tulis

### Skala Implementasi yang Realistis untuk 1 Minggu

Tidak perlu mengimplementasikan seluruh arsitektur yang diusulkan paper. Yang penting adalah:

- Satu komponen inti yang benar-benar berjalan
- Pengukuran yang bermakna
- Pemahaman tentang bagaimana sisa arsitektur akan terhubung

**Contoh skala yang tepat:**

- "Implementasi SBOM generation + signing — bukan seluruh supply chain security framework"
- "Implementasi drift detection dengan ArgoCD — bukan seluruh GitOps platform"
- "Implementasi anomaly detection pada satu metrik — bukan seluruh AIOps pipeline"

---

## Bagian 5 — Struktur Repositori dan Deliverable

### Struktur Repositori

```
[nama-kelompok]-devsecops-future/
├── README.md                      ← Setup dari nol + ringkasan implementasi
├── papers/
│   ├── paper-1-[judul-singkat].md ← Reading notes paper pertama
│   └── paper-2-[judul-singkat].md ← Reading notes paper kedua
├── research/
│   ├── 01-gap-analysis.md         ← Gap yang diselesaikan, berbasis paper
│   ├── 02-state-of-the-art.md     ← Apa yang sudah ada, apa yang masih kurang
│   └── 03-design-decisions.md     ← Keputusan desain + justifikasi dari paper
├── implementation/
│   └── [file konfigurasi, manifest, script, dsb.]
├── evaluation/
│   ├── metrics-before.md          ← Baseline sebelum implementasi
│   ├── metrics-after.md           ← Pengukuran setelah implementasi
│   └── analysis.md                ← Analisis: apakah berhasil? seberapa?
├── presentation/
│   └── slides.pdf
└── docs/
    └── refleksi-kelompok.md
```

### Penjelasan Komponen Kunci

**`papers/paper-*.md` — Reading Notes**

Untuk setiap paper, tulis catatan yang mencakup:

- Klaim utama paper dan bagaimana cara membuktikannya
- Temuan kunci yang langsung relevan untuk implementasimu
- Asumsi atau keterbatasan yang disebutkan paper
- Satu hal yang kamu ragukan atau pertanyakan dari paper

Ini bukan rangkuman — ini bukti bahwa kamu benar-benar membaca dan berpikir kritis.

**`research/03-design-decisions.md` — Keputusan Berbasis Paper**

Setiap keputusan desain yang signifikan harus ada rujukan ke paper. Formatnya bisa seperti ini:

> *"Kami memilih [pendekatan X] karena [Penulis, Tahun] menunjukkan bahwa [temuan Y]. Dalam konteks pipeline kami, ini berarti [implikasi Z]."*

Keputusan yang hanya berdasarkan "karena terlihat lebih mudah" atau "karena tutorial online merekomendasikan ini" tidak memenuhi ekspektasi modul ini.

**`evaluation/` — Data Nyata**

Ini bagian yang paling membedakan proyek ini dari sekadar mengikuti tutorial. Ukur sesuatu yang bermakna dan bandingkan sebelum vs sesudah. Beberapa contoh metrik yang relevan tergantung topik:

- Waktu deteksi insiden (sebelum vs sesudah monitoring di-enhance)
- Jumlah vulnerability yang terdeteksi (sebelum vs sesudah scanning di-tambahkan)
- Waktu deployment (sebelum vs sesudah GitOps)
- Waktu dari push ke feedback (developer experience)
- False positive rate dari sistem deteksi yang diimplementasikan

Kalau tidak ada yang bisa diukur secara kuantitatif, diskusikan ini dengan dosen sebelum Hari 3.

**`docs/refleksi-kelompok.md`**

Jawab tiga pertanyaan berikut, masing-masing minimal 250 kata:

1. *"Apa yang paling mengejutkan dari paper yang kamu baca — sesuatu yang berbeda dari asumsimu sebelumnya? Bagaimana temuan itu mengubah keputusan implementasimu?"*
2. *"Di mana implementasimu berbeda dari yang diusulkan paper, dan mengapa? Apakah karena keterbatasan waktu/resources, atau karena kamu tidak setuju dengan pendekatannya?"*
3. *"Jika kamu punya waktu satu bulan penuh dan akses ke production cluster nyata, apa yang akan kamu lakukan berbeda atau tambahkan? Gunakan paper sebagai landasan argumenmu."*

---

## Bagian 6 — Presentasi

### Format (20 menit per kelompok)

| Segmen              | Durasi  | Isi                                               |
| ------------------- | ------- | ------------------------------------------------- |
| Topik & Paper       | 4 menit | Gap yang diselesaikan + mengapa paper ini relevan |
| Implementasi & Demo | 7 menit | Arsitektur + demo live atau rekaman               |
| Evaluasi            | 6 menit | Data sebelum vs sesudah + analisis jujur          |
| Tanya Jawab         | 3 menit | Dari peserta dan dosen                            |

### Pertanyaan yang Mungkin Diajukan Dosen

Bersiaplah untuk pertanyaan seperti:

- *"Bagaimana paper ini membuktikan klaimnya — dan kamu percaya metodologinya?"*
- *"Kenapa kamu pilih paper ini dan bukan paper lain tentang topik yang sama?"*
- *"Metrik apa yang kamu gunakan, dan mengapa metrik itu representatif?"*
- *"Kalau implementasimu tidak menunjukkan improvement — apa hipotesismu tentang penyebabnya?"*

Kelompok lain **wajib** mengajukan minimal satu pertanyaan substantif per sesi.

---

## Bagian 7 — Penilaian

| #               | Komponen                                                   | Bobot | Yang Dinilai                                                |
| --------------- | ---------------------------------------------------------- | ----- | ----------------------------------------------------------- |
| 1               | Kualitas pemilihan paper                                   | 15%   | Relevansi, reputasi venue, kejelasan metodologi             |
| 2               | Reading notes & pemahaman paper                            | 20%   | Kedalaman baca, kemampuan berpikir kritis tentang paper     |
| 3               | Design decisions berbasis paper                            | 20%   | Seberapa kuat paper mendukung keputusan teknis              |
| 4               | Implementasi berjalan & terdokumentasi                     | 20%   | Reproducible dari README                                    |
| 5               | Evaluasi dengan data nyata                                 | 15%   | Ada pengukuran bermakna, analisis jujur                     |
| 6               | Presentasi & tanya jawab                                   | 10%   | Terutama kemampuan menjawab pertanyaan tentang paper        |
| **Bonus** | Paper tambahan bereputasi yang digunakan dalam argumen     | +5%   | Harus ada dalam design decisions, bukan sekadar dicantumkan |
| **Bonus** | Kontribusi ke proyek open source terkait (PR, issue, docs) | +5%   | Sertakan bukti link                                         |

**Catatan penting**: Implementasi yang tidak sempurna tapi disertai evaluasi dan refleksi yang jujur nilainya lebih tinggi dari implementasi yang "sempurna" tanpa pemahaman mengapa keputusan teknis dibuat.

---

## Bagian 8 — Demo dan Pengumpulan

### Sesi Demo (Minggu 17 — via Zoom)

Demo dilakukan secara online di sesi Zoom minggu berikutnya. Setiap kelompok mendapat waktu **20 menit** dengan format:

| Segmen        | Durasi  | Isi                                                            |
| ------------- | ------- | -------------------------------------------------------------- |
| Topik & Paper | 4 menit | Gap yang diselesaikan + mengapa paper ini relevan              |
| Demo Live     | 8 menit | Jalankan implementasi secara langsung di Zoom — bukan rekaman |
| Evaluasi      | 5 menit | Tunjukkan data sebelum vs sesudah + analisis                   |
| Tanya Jawab   | 3 menit | Dari peserta dan dosen                                         |

**Catatan demo**: Demo harus *live* — bukan rekaman atau screenshot. Siapkan lingkungan yang sudah berjalan sebelum sesi dimulai agar tidak membuang waktu setup saat presentasi.

### Format Pengumpulan

Yang dikumpulkan ke LMS **sebelum sesi Zoom dimulai**:

1. **Link repositori GitHub** — harus *public*, commit history menunjukkan kontribusi tiap anggota
2. **Slide presentasi** sudah ada di `presentation/slides.pdf` di dalam repositori

Sebelum submit, pastikan satu anggota kelompok mencoba menjalankan setup dari nol menggunakan README — ini satu-satunya cara memastikan README benar-benar reproducible dan demo tidak gagal di tengah jalan.

---

*Kemampuan menemukan, mengevaluasi, dan mengimplementasikan ide dari literatur ilmiah adalah salah satu hal yang membedakan engineer yang sekadar mengikuti tren dari engineer yang memahami mengapa tren itu muncul.*
