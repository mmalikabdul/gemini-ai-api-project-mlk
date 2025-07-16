# 🔮 Gemini Flash API Server

API server berbasis Node.js yang menggunakan Google Gemini 1.5 Flash untuk menghasilkan konten dari berbagai jenis input seperti **teks, gambar, dokumen, dan audio**.

---

## ✨ Fitur Utama

- ✅ Generate konten dari prompt teks
- 🖼️ Analisis gambar (image-to-text)
- 📄 Analisis dokumen (PDF, DOCX, dll.)
- 🎧 Transkripsi atau analisis audio
- 🔐 Konfigurasi API key melalui `.env`
- 🧹 Upload file otomatis dibersihkan setelah proses selesai

---

## 📁 Struktur Project

gemini-flash-api/
├── server.js
├── .env.example
├── .gitignore
├── uploads/
├── package.json
└── README.md

yaml
Copy
Edit

---

## ⚙️ Instalasi dan Konfigurasi

### 1. Clone repo dan masuk ke folder:

```bash
git clone https://github.com/mmalikabdul/gemini-ai-api-project-mlk.git
cd gemini-ai-api-project-mlk
npm install
2. Konfigurasi .env
Buat file .env dari template .env.example:

env
Copy
Edit
GEMINI_API_KEY=your-gemini-api-key-here
PORT=3000
🔐 Jangan upload .env ke GitHub – sudah diabaikan oleh .gitignore

📡 API Endpoint
📍 POST /generate-text
Generate output teks dari prompt.

Request Body (JSON):

json
Copy
Edit
{
  "prompt": "Apa itu kecerdasan buatan?"
}
📍 POST /generate-from-image
Analisis gambar dengan prompt tambahan (opsional).

Form Data:

image (file)

prompt (opsional string)

📍 POST /generate-from-document
Analisis atau ringkasan dokumen (PDF, DOCX, dll.)

Form Data:

document (file)

📍 POST /generate-from-audio
Transkripsi atau interpretasi audio.

Form Data:

audio (file)

🧪 Contoh Penggunaan (curl)
bash
Copy
Edit
curl -X POST http://localhost:3000/generate-text \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Jelaskan dampak AI terhadap pendidikan"}'
📌 Catatan Tambahan
Semua file yang diupload akan otomatis dihapus setelah proses selesai (via fs.unlinkSync).

File upload disimpan sementara di folder uploads/.

👨‍💻 Author
Made with ❤️ by @mmalikabdul