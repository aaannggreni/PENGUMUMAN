kelulusan-sdn1-astina/
├── index.html
├── style.css
└── script.js
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <title>Kelulusan SDN 1 ASTINA</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container" id="page1">
    <h1>Pengumuman Kelulusan</h1>
    <h2>SD Negeri 1 ASTINA<br>Tahun Ajaran 2025/2026</h2>
    <p class="sambutan">
      Om Swastiastu,<br/><br/>
      Selamat malam kepada seluruh siswa dan orang tua yang kami banggakan.<br/><br/>
      Dengan bangga kami umumkan hasil kelulusan siswa-siswi SD Negeri 1 ASTINA Tahun Ajaran 2025/2026.<br/><br/>
      Semoga hasil ini menjadi langkah awal menuju masa depan yang cerah.<br/><br/>
      Hormat kami,<br/>
      <strong>Sri Puspitasari, M.Pd.</strong><br/>
      Kepala Sekolah
    </p>
    <button onclick="scrollToPage2()">Cek Kelulusan</button>
    <footer>Jl. Gajah Mada No. 37 Singaraja</footer>
  </div>

  <div class="container" id="page2">
    <h2>🔍 Masukkan Nama untuk Mengecek Kelulusan</h2>
    <input type="text" id="studentName" placeholder="Masukkan Nama Lengkap..." />
    <button onclick="checkGraduation()">Cek Sekarang</button>
    <div id="resultArea"></div>
  </div>

  <script src="script.js"></script>
</body>
</html>
4. Isi File style.css
css
Salin
Edit
body {
  font-family: 'Poppins', sans-serif;
  margin: 0; padding: 0;
  background: linear-gradient(to bottom right, #2196F3, #BBDEFB);
  color: #fff;
}
.container {
  max-width: 700px;
  margin: 0 auto;
  padding: 40px;
  text-align: center;
}
h1, h2 { margin-bottom: 20px; }
button {
  background-color: #fff;
  color: #2196F3;
  padding: 10px 25px;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
}
input {
  padding: 10px;
  width: 80%;
  border-radius: 5px;
  border: none;
  font-size: 16px;
  margin: 20px 0;
}
#resultArea {
  margin-top: 20px;
  font-size: 18px;
  background-color: rgba(255,255,255,0.2);
  padding: 20px;
  border-radius: 10px;
}
footer {
  margin-top: 50px;
  font-size: 14px;
  color: #e0e0e0;
}
5. Isi File script.js
js
Salin
Edit
const dataKelulusan = [
  "NYOMAN ALINDYA AISHWARYA RASMIKA",
  "KOMANG DIMAS ADITYA ANGGASTA",
  /* ... semua nama sesuai list ... */
  "KADEK DEVAN MAHANTA"
];

function scrollToPage2() {
  document.getElementById('page2').scrollIntoView({ behavior: 'smooth' });
}

function checkGraduation() {
  const input = document.getElementById("studentName").value.toUpperCase().trim();
  const result = document.getElementById("resultArea");
  if (!input) {
    result.innerHTML = "❗ Silakan masukkan nama terlebih dahulu.";
    return;
  }
  if (dataKelulusan.includes(input)) {
    result.innerHTML = `🎉 Selamat! <strong>${input}</strong> dinyatakan <span style="color: #b0ff4d">LULUS</span>! 🥳🎓`;
  } else {
    result.innerHTML = `⚠️ Maaf, nama <strong>${input}</strong> tidak ditemukan.`;
  }
}
