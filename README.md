# 🌐 Simulasi Keamanan Digital — Penyuluhan Desa Kapur

Website interaktif untuk penyuluhan keamanan digital di Desa Kapur, Kubu Raya, Kalimantan Barat.

## 📁 Lokasi File
`/Users/apple/deepseekharness/komputaci-paralel-uts/digital-security-simulator/`

---

## 🚀 Cara Deploy ke Vercel (Project "tes-keamanan")

### **Cara 1: Melalui Web Dashboard (Recommended - 25 menit)**

#### **Langkah 1: GitHub - Upload Website**
1. Buka: `https://github.com/andra956/tes-keamanan`
2. Klik **Add file** → **Upload files**
3. **Drag dan lepaskan** folder `digital-security-simulator` dari komputer
4. Klik **Commit changes**

#### **Langkah 2: Vercel - Connect Repository**
1. Buka: `https://vercel.com` lalu **login** akun Anda
2. Klik **Add New** → **Project**
3. **Pilih**: **Import Git Repository**
4. Cari dan pilih repositori `andra956/tes-keamanan`
5. **Project Name**: `tes-keamanan`
6. **Framework Preset**: `Static HTML`
7. **Root Directory**: kosongkan (biarkan `/`)
8. Klik **Create**

#### **Langkah 3: Auto-Deploy**
1. Vercel akan **otomatis deploy** (1-2 menit)
2. URL website: `https://tes-keamanan.vercel.app`
3. Buka untuk test: pastikan welcome screen muncul

#### **Langkah 4: Supabase - Buat Database**
1. Buka: `https://supabase.com/dashboard` lalu **login**
2. Klik **New Project**
3. Isi:
   - **Name**: `tes-keamanan-progress`
   - **Password**: buat password (contoh: `postgres123`)
   - **Region**: `ap-southeast-1` (terdekat Indonesia)
4. Tunggu 2-3 menit project jadi
5. Klik **SQL Editor** → **New Query** → masukan:
```sql
CREATE TABLE IF NOT EXISTS user_progress (
  user_id TEXT PRIMARY KEY,
  progress_data JSONB DEFAULT '{}'::jsonb,
  updated_at TIMESTAMP DEFAULT now()
);
CREATE TABLE IF NOT EXISTS earned_badges (
  id SERIAL PRIMARY KEY,
  user_id TEXT,
  badge_type TEXT,
  badge_name TEXT,
  earned_at TIMESTAMP DEFAULT now()
);
```
6. Klik **Run**
7. Klik **Settings** → **API**
8. **Copy** dua nilai ini:
   - **Project URL**: contoh `https://xyzabc123.supabase.co`
   - **anon public key**: contoh `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...` (string panjang)

#### **Langkah 5: Vercel - Set Environment Variables**
1. Di halaman project Vercel `tes-keamanan`, klik **Settings** → **Environment Variables**
2. Klik **Add Variable** tiga kali:
   - **Key**: `VITE_SUPABASE_URL` | **Value**: masukin Project URL dari Supabase
   - **Key**: `VITE_SUPABASE_ANON_KEY` | **Value**: masukin anon key dari Supabase
   - **Key**: `NODE_ENV` | **Value**: `production`
3. Klik **Save**
4. Klik **Deployments** → **Trigger Redeploy**
5. Tunggu 1-2 menit deploy selesai

#### **Langkah 6: Test Semua Fitur**
1. Buka `https://tes-keamanan.vercel.app`
2. **Test User**: Masukkan nama "Budi", role "user" → Masuk
3. **Test Admin**: Pilih role "admin", nama "Admin", password `desa-kapur-2024` → Masuk
4. **Test Leaderboard**: Klik tombol 🏆 di nav
5. **Test Modul**: Coba phishing, password, quiz, dll

---

### **Cara 2: Pakai Git CLI (Jika Git Terinstall)**

```bash
cd /Users/apple/deepseekharness/komputaci-paralel-uts/digital-security-simulator
git init
git add .
git commit -m "Initial website commit"
git remote add origin https://github.com/andra956/tes-keamanan.git
git branch -M main
git push -u origin main
```
Lalu lanjut ke **Langkah 2: Vercel** di atas.

---

## 📊 Fitur yang Tersedia

Setelah deploy sukses, website memiliki fitur:

| Fitur | Deskripsi |
|-------|-----------|
| **👤 Welcome Screen** | Meminta nama + role (user/admin) |
| **🔒 Admin Panel** | Password: `desa-kapur-2024` untuk lihat leaderboard |
| **📊 Leaderboard** | Menampilkan pengguna terbaik dengan poin & badge |
| **📧 Simulasi Phishing** | Temani 5 tanda penipuan |
| **🔑 Kekuatan Password** | Meter kekuatan + estimasi waktu hacker |
| **💻 Serangan Hacker** | Simulasi brute-force 3 kategori |
| **🔒 2FA & Kode OTP** | Simulasi penipuan minta OTP |
| **🎯 Kuis Keamanan** | 10 pertanyaan pilihan ganda |
| **💡 Tips Keamanan** | 6 kategori tips praktis |

---

## 📦 Struktur Folder

```
digital-security-simulator/
├── index.html        (website utama, 123 KB)
├── vercel.json      (konfigurasi Vercel)
└── README.md        (bantuan ini)
```

---

## ⚠️ Troubleshooting

| Masalah | Solusi |
|---------|--------|
| Website tidak terbuka | Cek URL: `https://tes-keamanan.vercel.app` |
| Leaderboard tidak muncul | Pastikan login admin dengan password `desa-kapur-2024` |
| Progress tidak tersimpan | Cek Environment Variables di Vercel |
| Error "Cannot read property" | Refresh halaman, cek file sudah terupload ke GitHub |

---

## 📞 Bantuan

Jika mengalami kendala:
1. **GitHub**: Pastikan folder `digital-security-simulator` sudah diupload (lihat `Add file` → `Upload files`)
2. **Vercel**: Cek `Settings` → `Environment Variables` nilai `VITE_SUPABASE_URL` dan `VITE_SUPABASE_ANON_KEY`
3. **Supabase**: Cek `SQL Editor` query sudah sukses (tanda check) dan `API` credentials sudah di-copy benar

---

Dibuat untuk penyuluhan di **Desa Kapur, Kubu Raya, Kalimantan Barat, 2026**.