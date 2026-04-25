# 🔬 Virtual Optics Laboratory

![Project Status](https://img.shields.io/badge/Status-In_Development-blue)
![Tech Stack](https://img.shields.io/badge/Tech-React_|_Konva_|_Zustand-informational)

Sebuah simulasi interaktif berbasis web untuk memvisualisasikan perilaku cahaya (optik geometrik). Aplikasi ini memungkinkan pengguna untuk bereksperimen dengan laser, cermin, dan medium transparan di atas "meja lab" virtual untuk memahami konsep pemantulan dan pembiasan cahaya secara *real-time*.

## ✨ Fitur Utama

* **Interactive Workspace:** Sistem *drag-and-drop* untuk menempatkan dan memutar komponen optik (laser, cermin, kaca).
* **Real-time Raycasting:** Sinar cahaya otomatis dikalkulasi dan digambar ulang secara instan setiap kali posisi benda berubah.
* **Simulasi Pemantulan:** Cahaya memantul dengan sudut yang presisi saat mengenai permukaan cermin.
* **Simulasi Pembiasan (Hukum Snellius):** Cahaya membiak (berbelok) saat memasuki dan keluar dari medium dengan indeks bias yang berbeda (seperti balok kaca).
* **Customizable Properties:** Pengguna dapat mengubah indeks bias medium, warna laser, dan sudut rotasi benda.

## 🛠️ Teknologi yang Digunakan

* **Framework:** [React.js](https://reactjs.org/) (di-*bootstrap* dengan [Vite](https://vitejs.dev/))
* **Rendering 2D:** [react-konva](https://github.com/konvajs/react-konva) (HTML5 Canvas API)
* **State Management:** [Zustand](https://github.com/pmndrs/zustand)
* **Styling:** [Tailwind CSS](https://tailwindcss.com/)

## 🧮 Konsep Fisika & Matematika

Proyek ini dibangun menggunakan *custom raycasting engine* yang menerapkan hukum-hukum fisika berikut:

### 1. Hukum Pemantulan (Cermin)
Vektor arah pantulan dihitung menggunakan rumus pantulan vektor. Jika $\vec{v}$ adalah arah datang cahaya dan $\vec{n}$ adalah garis normal permukaan:

$$\vec{r} = \vec{v} - 2(\vec{v} \cdot \vec{n})\vec{n}$$

### 2. Hukum Pembiasan (Snellius)
Ketika sinar melewati dua medium dengan indeks bias berbeda ($n_1$ dan $n_2$), sudut bias ($\theta_2$) dihitung berdasarkan sudut datang ($\theta_1$):

$$n_1 \sin(\theta_1) = n_2 \sin(\theta_2)$$

## 📂 Struktur Direktori Utama

\`\`\`text
src/
├── components/
│   ├── ui/               # Komponen antarmuka (Toolbar, Properties Panel)
│   └── canvas/           # Komponen react-konva (Scene, Laser, Mirror, Ray)
├── physics/
│   ├── engine.js         # Algoritma raycasting dan deteksi tabrakan
│   └── opticsMath.js     # Fungsi vektor dan trigonometri
├── store/
│   └── useOpticsStore.js # Global state (menyimpan posisi dan data benda)
└── App.jsx               # Main container
\`\`\`

## 🚀 Cara Menjalankan Proyek Secara Lokal

1. **Clone repositori ini:**
   \`\`\`bash
   git clone https://github.com/Ms-Ulfiyahrustam/Laboratorium-Optik-Virtual.git
   cd virtual-optics-lab
   \`\`\`

2. **Instal dependensi:**
   \`\`\`bash
   npm install
   # atau
   yarn install
   \`\`\`

3. **Jalankan *development server*:**
   \`\`\`bash
   npm run dev
   # atau
   yarn dev
   \`\`\`

4. Buka browser dan navigasikan ke URL yang disediakan oleh Vite (biasanya `http://localhost:5173`).

## 🗺️ Rencana Pengembangan (Roadmap)

- [x] Basic Canvas & Drag-and-Drop
- [x] Deteksi Pemantulan (Cermin Datar)
- [ ] Deteksi Pembiasan (Balok Kaca)
- [ ] Implementasi Lensa Cembung & Cekung
- [ ] Prisma dan Dispersi Cahaya (Pemecahan warna spektrum)



---
*Dibuat untuk mempermudah visualisasi fisika melalui baris kode.* 🚀
