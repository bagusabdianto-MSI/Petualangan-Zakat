<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PAI Ceria : Materi Kelas 6 Smt 1 Zakat Fitrah Dan Zakat Mal</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Google Font Poppins -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    html, body {
      font-family: 'Poppins', sans-serif;
      touch-action: pan-y;
      -webkit-overflow-scrolling: touch;
    }
    .fade-in { animation: fadeIn 0.25s ease-out forwards; }
    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }
    canvas {
      touch-action: none;
    }
  </style>
</head>
<body class="bg-slate-100 text-slate-800 min-h-screen flex flex-col justify-between overflow-x-hidden overflow-y-auto">

  <!-- ================= HEADER UTAMA ================= -->
  <header class="bg-emerald-600 text-white shadow-lg p-3 md:p-4 sticky top-0 z-40">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row justify-between items-center gap-2">
      <div class="flex items-center space-x-2 text-center md:text-left">
        <span class="text-2xl">🕌</span>
        <h1 class="font-bold text-sm md:text-base tracking-wide">
          PAI Ceria : Materi Kelas 6 Smt 1 Zakat Fitrah Dan Zakat Mal
        </h1>
      </div>
      <div id="userBadge" class="hidden text-xs bg-emerald-800 px-3 py-1.5 rounded-full flex items-center space-x-2 border border-emerald-400">
        <span id="badgeName" class="font-medium"></span>
        <button type="button" onclick="logout()" class="text-amber-300 hover:text-white underline font-semibold ml-2">Ganti Siswa</button>
      </div>
    </div>
  </header>

  <!-- ================= CONTAINER UTAMA ================= -->
  <main class="max-w-6xl mx-auto w-full p-3 md:p-4 flex-1">

    <!-- 1. HALAMAN REGISTER -->
    <section id="viewRegister" class="bg-white p-6 md:p-8 rounded-3xl shadow-2xl max-w-lg mx-auto my-6 border-t-8 border-emerald-500">
      <div class="text-center mb-6">
        <span class="inline-block bg-emerald-100 text-emerald-800 text-xs px-3 py-1 rounded-full font-bold uppercase tracking-wider mb-2">Media Edukasi Interaktif PAI</span>
        <h2 class="text-xl md:text-2xl font-black text-slate-800 leading-snug">
          PAI Ceria : Materi Kelas 6 Smt 1 Zakat Fitrah Dan Zakat Mal
        </h2>
        <div class="mt-2 inline-flex items-center gap-1.5 px-3 py-1 bg-amber-50 border border-amber-300 rounded-full">
          <span class="text-xs">✨</span>
          <span class="text-xs font-bold text-amber-900 tracking-wide">By : Bagus Abdianto</span>
        </div>
      </div>

      <form id="formRegister" onsubmit="handleRegister(event)" class="space-y-4">
        <div>
          <label class="block text-xs font-bold text-slate-700 uppercase mb-1">Nama Lengkap Siswa:</label>
          <input type="text" id="regName" required placeholder="Contoh: Muhammad Rizky" 
            class="w-full px-4 py-2.5 border-2 border-slate-200 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:border-emerald-500 focus:outline-none text-sm font-medium">
        </div>
        <div>
          <label class="block text-xs font-bold text-slate-700 uppercase mb-1">Nomor Absen:</label>
          <input type="number" id="regAbsen" required min="1" max="60" placeholder="Contoh: 14" 
            class="w-full px-4 py-2.5 border-2 border-slate-200 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:border-emerald-500 focus:outline-none text-sm font-medium">
        </div>
        <div>
          <label class="block text-xs font-bold text-slate-700 uppercase mb-1">Jenis Kelamin (Karakter Game):</label>
          <select id="regGender" required class="w-full px-4 py-2.5 border-2 border-slate-200 rounded-xl focus:ring-2 focus:ring-emerald-500 focus:border-emerald-500 focus:outline-none bg-white text-sm font-medium">
            <option value="">-- Pilih Jenis Kelamin --</option>
            <option value="Laki-laki">👦 Laki-laki (Karakter Berpeci)</option>
            <option value="Perempuan">👧 Perempuan (Karakter Berjilbab)</option>
          </select>
        </div>
        <button type="submit" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-black py-3.5 rounded-xl shadow-lg transition duration-200 mt-4 flex justify-center items-center gap-2 tracking-wide uppercase text-sm cursor-pointer">
          <span>Masuk Ke Menu Utama</span> 🚀
        </button>
      </form>
    </section>

    <!-- 2. MENU UTAMA -->
    <section id="viewMenu" class="hidden">
      <div class="bg-gradient-to-r from-emerald-600 via-teal-700 to-emerald-800 text-white p-6 md:p-8 rounded-3xl shadow-xl mb-6 relative overflow-hidden">
        <div class="relative z-10">
          <p class="text-xs font-bold text-emerald-200 uppercase tracking-widest">Gelanggang Belajar PAI Interaktif</p>
          <h2 class="text-xl md:text-3xl font-black mt-1">Ahlan wa Sahlan, <span id="greetingName" class="text-amber-300"></span>! 👋</h2>
          <p class="text-xs md:text-sm text-emerald-100 mt-2 max-w-2xl leading-relaxed">
            Yuk perdalam materi zakat fitrah & zakat mal, coba simulasi hitung otomatis, lalu uji pemahaman di <strong>2 Game 3D Luas</strong> dengan sistem <strong>Soal Acak & Dinamis</strong>!
          </p>
        </div>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
        <!-- 1. Petunjuk -->
        <div onclick="showView('viewPetunjuk')" class="cursor-pointer bg-white p-5 rounded-2xl shadow hover:shadow-xl transition border-b-4 border-sky-500 flex items-center space-x-4">
          <div class="text-3xl p-3 bg-sky-100 rounded-2xl">📋</div>
          <div>
            <h3 class="font-bold text-base text-slate-800">1. Petunjuk Aplikasi</h3>
            <p class="text-xs text-gray-500">Panduan belajar dan tata cara bermain.</p>
          </div>
        </div>

        <!-- 2. Materi Lengkap -->
        <div onclick="showView('viewMateri')" class="cursor-pointer bg-white p-5 rounded-2xl shadow hover:shadow-xl transition border-b-4 border-emerald-500 flex items-center space-x-4">
          <div class="text-3xl p-3 bg-emerald-100 rounded-2xl">📖</div>
          <div>
            <h3 class="font-bold text-base text-slate-800">2. Materi Lengkap & Ilustrasi</h3>
            <p class="text-xs text-gray-500">Zakat Fitrah, Zakat Mal, & 8 Asnaf.</p>
          </div>
        </div>

        <!-- 3. Simulasi Hitung -->
        <div onclick="showView('viewSimulasi')" class="cursor-pointer bg-white p-5 rounded-2xl shadow hover:shadow-xl transition border-b-4 border-amber-500 flex items-center space-x-4">
          <div class="text-3xl p-3 bg-amber-100 rounded-2xl">🧮</div>
          <div>
            <h3 class="font-bold text-base text-slate-800">3. Simulasi Hitung Zakat</h3>
            <p class="text-xs text-gray-500">Kalkulator beras & tabungan mal.</p>
          </div>
        </div>

        <!-- 4. Game 1: Balap Lari 3D -->
        <div onclick="startGame()" class="cursor-pointer bg-gradient-to-br from-purple-600 to-indigo-700 text-white p-5 rounded-2xl shadow-lg hover:shadow-2xl transition border-b-4 border-amber-400 flex items-center space-x-4 transform hover:-translate-y-1">
          <div class="text-3xl p-3 bg-white/20 rounded-2xl animate-pulse">🏃</div>
          <div>
            <span class="text-[10px] uppercase font-black bg-amber-400 text-slate-900 px-2 py-0.5 rounded-full">Game 1 • Soal Acak</span>
            <h3 class="font-black text-base mt-0.5">Balap Lari Stadion 3D Realistis</h3>
            <p class="text-xs text-purple-200">Area finis luas, podium juara, piala & kembang api!</p>
          </div>
        </div>

        <!-- 5. Game 2: Taman Labirin 3D Broadcast -->
        <div onclick="startMazeGame()" class="cursor-pointer bg-gradient-to-br from-rose-700 via-amber-700 to-emerald-800 text-white p-5 rounded-2xl shadow-lg hover:shadow-2xl transition border-b-4 border-emerald-400 flex items-center space-x-4 transform hover:-translate-y-1 sm:col-span-2 lg:col-span-2">
          <div class="text-4xl p-3 bg-black/30 rounded-2xl animate-bounce">🧭</div>
          <div>
            <div class="flex items-center gap-2">
              <span class="text-[10px] uppercase font-black bg-rose-400 text-slate-900 px-2.5 py-0.5 rounded-full">Game 2 • Soal Acak</span>
              <span class="text-[10px] uppercase font-bold bg-white/20 px-2 py-0.5 rounded-full">Iblis 2 Telah Normal</span>
            </div>
            <h3 class="font-black text-lg mt-0.5">Taman Labirin: Taklukkan 10 Bisikan Iblis 3D</h3>
            <p class="text-xs text-amber-100">Jalur telah dioptimasi, 10 iblis siap menantang dengan kombinasi soal baru!</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 3. PETUNJUK PEMAKAIAN -->
    <section id="viewPetunjuk" class="hidden bg-white p-6 rounded-3xl shadow-lg">
      <div class="flex items-center justify-between mb-4 border-b pb-3">
        <h2 class="text-lg font-bold text-sky-700 flex items-center gap-2">📋 Petunjuk Pemakaian Aplikasi</h2>
        <button type="button" onclick="showView('viewMenu')" class="text-xs bg-slate-100 hover:bg-slate-200 px-3 py-1.5 rounded-xl font-bold">Kembali ↩</button>
      </div>
      <div class="space-y-4 text-xs md:text-sm text-slate-600">
        <div class="p-4 bg-sky-50 rounded-2xl border border-sky-200">
          <h4 class="font-bold text-sky-900 mb-1 text-sm">🏃 Game 1: Balap Lari Stadion 3D</h4>
          <ul class="list-disc pl-5 space-y-1">
            <li>Gunakan tombol <strong>Maju (⏩)</strong> atau <strong>Mundur (⏪)</strong> (keyboard panah kanan/kiri / D dan A).</li>
            <li>Jawab 10 soal acak di setiap gawang untuk melompat mulus (+10 poin).</li>
            <li>Pilihan ganda dan nomor urut soal selalu diacak setiap bermain kembali!</li>
            <li>Karakter tetap bebas berjalan di pelataran stadion sehabis finis.</li>
          </ul>
        </div>
        <div class="p-4 bg-emerald-50 rounded-2xl border border-emerald-200">
          <h4 class="font-bold text-emerald-900 mb-1 text-sm">🧭 Game 2: Taman Labirin 3D Broadcast View</h4>
          <ul class="list-disc pl-5 space-y-1">
            <li>Karakter memulai dari <strong>Pintu Masuk (START) paling bawah</strong>.</li>
            <li>Gunakan <strong>D-Pad Arah (⬆️ ⬇️ ⬅️ ➡️)</strong> atau keyboard (W A S D / Panah).</li>
            <li>Hadapi 10 iblis merah di sepanjang jalur yang membisikkan soal zakat secara acak. Seluruh iblis (termasuk Iblis ke-2) kini aktif sempurna.</li>
            <li>Kalahkan semua iblis untuk meraih skor iman penuh dan masuk ke halaman istana emas di atas.</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- 4. MATERI ZAKAT LENGKAP & BERILUSTRASI -->
    <section id="viewMateri" class="hidden bg-white p-5 md:p-8 rounded-3xl shadow-lg">
      <div class="flex items-center justify-between mb-6 border-b pb-4">
        <div>
          <span class="bg-emerald-100 text-emerald-800 text-[11px] font-black px-3 py-1 rounded-full uppercase">Kurikulum PAI Kelas 6 Semester 1</span>
          <h2 class="text-xl md:text-2xl font-black text-emerald-800 mt-1 flex items-center gap-2">📖 Pendalaman Materi Zakat Fitrah & Zakat Mal</h2>
        </div>
        <button type="button" onclick="showView('viewMenu')" class="text-xs bg-slate-100 hover:bg-slate-200 px-4 py-2 rounded-xl font-bold">Kembali ↩</button>
      </div>

      <!-- KARTU 1: ZAKAT FITRAH -->
      <div class="mb-8 bg-gradient-to-br from-emerald-50 to-teal-50 border-2 border-emerald-200 rounded-3xl p-5 md:p-6 shadow-sm">
        <div class="flex flex-col md:flex-row gap-6 items-center">
          <div class="w-full md:w-1/3 flex flex-col items-center justify-center p-4 bg-white rounded-2xl border border-emerald-100 shadow-inner">
            <svg class="w-36 h-36 drop-shadow-md" viewBox="0 0 160 160" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M40 70C40 50 60 45 80 45C100 45 120 50 120 70C120 110 115 135 110 140C105 145 55 145 50 140C45 135 40 110 40 70Z" fill="#D97706"/>
              <path d="M48 75C48 58 64 54 80 54C96 54 112 58 112 75C112 110 108 132 104 136C100 140 60 140 56 136C52 132 48 110 48 75Z" fill="#F59E0B"/>
              <ellipse cx="80" cy="50" rx="36" ry="10" fill="#92400E"/>
              <ellipse cx="80" cy="48" rx="32" ry="8" fill="#FBBF24"/>
              <ellipse cx="80" cy="45" rx="26" ry="8" fill="#FEF3C7"/>
              <circle cx="75" cy="43" r="2.5" fill="#FFFFFF"/>
              <circle cx="85" cy="44" r="2.5" fill="#FFFFFF"/>
              <circle cx="80" cy="46" r="2" fill="#FFFFFF"/>
              <rect x="58" y="80" width="44" height="34" rx="6" fill="#FFFFFF" stroke="#B45309" stroke-width="2"/>
              <text x="80" y="94" font-size="9" font-weight="bold" fill="#047857" text-anchor="middle">ZAKAT</text>
              <text x="80" y="106" font-size="10" font-weight="900" fill="#B45309" text-anchor="middle">2,5 KG</text>
              <path d="M25 135C25 100 40 85 45 80" stroke="#10B981" stroke-width="3" stroke-linecap="round"/>
              <circle cx="38" cy="95" r="4" fill="#FBBF24"/>
              <circle cx="32" cy="110" r="4" fill="#FBBF24"/>
              <circle cx="28" cy="125" r="4" fill="#FBBF24"/>
            </svg>
            <span class="text-xs font-black text-emerald-800 mt-2">🌾 Zakat Fitrah (Zakat Jiwa)</span>
            <span class="text-[11px] text-gray-500 font-semibold">1 Sha' = 2,5 Kg / 3,5 Liter Beras</span>
          </div>

          <div class="w-full md:w-2/3 space-y-3 text-xs md:text-sm">
            <h3 class="font-black text-emerald-900 text-base flex items-center gap-2">
              <span>🌾</span> A. Ketentuan Lengkap Zakat Fitrah
            </h3>
            <p class="text-slate-700 leading-relaxed">
              <strong>Pengertian:</strong> Zakat jiwa (*zakatun nafs*) yang wajib ditunaikan oleh setiap muslim pada bulan Ramadan hingga sebelum salat Idul Fitri untuk menyucikan jiwa serta melengkapi ibadah puasa.
            </p>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 pt-1">
              <div class="bg-white p-2.5 rounded-xl border border-emerald-100 shadow-sm">
                <span class="font-bold text-emerald-800 block mb-0.5">Syarat Wajib:</span>
                <ul class="list-disc pl-4 text-[12px] text-slate-600 space-y-0.5">
                  <li>Beragama Islam (laki-laki maupun perempuan, tua/muda/bayi).</li>
                  <li>Lahir sebelum terbenam matahari akhir Ramadan.</li>
                  <li>Memiliki kelebihan makanan pokok untuk malam & hari raya Idul Fitri.</li>
                </ul>
              </div>
              <div class="bg-white p-2.5 rounded-xl border border-emerald-100 shadow-sm">
                <span class="font-bold text-emerald-800 block mb-0.5">Takaran & Makanan:</span>
                <ul class="list-disc pl-4 text-[12px] text-slate-600 space-y-0.5">
                  <li>Makanan pokok setempat (beras, gandum, kurma).</li>
                  <li>Kadar: 1 sha' setara <strong>2,5 kg atau 3,5 liter</strong> per jiwa.</li>
                  <li>Boleh diganti uang senilai harga beras tersebut.</li>
                </ul>
              </div>
            </div>

            <div class="bg-white p-3 rounded-2xl border border-emerald-200">
              <span class="font-bold text-slate-800 block mb-1 text-xs">⏰ Waktu Membayar Zakat Fitrah:</span>
              <div class="grid grid-cols-2 sm:grid-cols-5 gap-1.5 text-[11px] text-center font-semibold">
                <div class="bg-emerald-50 text-emerald-800 p-1.5 rounded-lg border border-emerald-200">
                  <span class="block font-black text-emerald-900">Mubah</span> Awal Ramadan
                </div>
                <div class="bg-blue-50 text-blue-800 p-1.5 rounded-lg border border-blue-200">
                  <span class="block font-black text-blue-900">Wajib</span> Akhir Ramadan
                </div>
                <div class="bg-amber-100 text-amber-900 p-1.5 rounded-lg border border-amber-300 ring-1 ring-amber-400">
                  <span class="block font-black text-amber-900">Afdhal</span> Pagi sblm Salat Id
                </div>
                <div class="bg-orange-50 text-orange-800 p-1.5 rounded-lg border border-orange-200">
                  <span class="block font-black text-orange-900">Makruh</span> Selesai Salat Id
                </div>
                <div class="bg-rose-50 text-rose-800 p-1.5 rounded-lg border border-rose-200 col-span-2 sm:col-span-1">
                  <span class="block font-black text-rose-900">Haram</span> Lewat 1 Syawal
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- KARTU 2: ZAKAT MAL -->
      <div class="mb-8 bg-gradient-to-br from-amber-50 to-orange-50 border-2 border-amber-200 rounded-3xl p-5 md:p-6 shadow-sm">
        <div class="flex flex-col md:flex-row gap-6 items-center">
          <div class="w-full md:w-1/3 flex flex-col items-center justify-center p-4 bg-white rounded-2xl border border-amber-100 shadow-inner">
            <svg class="w-36 h-36 drop-shadow-md" viewBox="0 0 160 160" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="25" y="70" width="110" height="65" rx="10" fill="#78350F"/>
              <rect x="30" y="75" width="100" height="55" rx="8" fill="#B45309"/>
              <rect x="68" y="85" width="24" height="20" rx="4" fill="#FBBF24" stroke="#78350F" stroke-width="2"/>
              <circle cx="80" cy="95" r="3" fill="#78350F"/>
              <polygon points="55,55 85,55 100,68 40,68" fill="#FDE047"/>
              <polygon points="40,68 100,68 95,78 35,78" fill="#EAB308"/>
              <polygon points="95,78 100,68 85,55 80,65" fill="#CA8A04"/>
              <circle cx="115" cy="55" r="16" fill="#FACC15" stroke="#CA8A04" stroke-width="2"/>
              <text x="115" y="60" font-size="12" font-weight="900" fill="#78350F" text-anchor="middle">2,5%</text>
              <circle cx="45" cy="58" r="13" fill="#FBBF24" stroke="#B45309" stroke-width="2"/>
              <text x="45" y="63" font-size="9" font-weight="bold" fill="#78350F" text-anchor="middle">85g</text>
            </svg>
            <span class="text-xs font-black text-amber-800 mt-2">💰 Zakat Mal (Harta Kekayaan)</span>
            <span class="text-[11px] text-gray-500 font-semibold">Nisab Emas 85g & Haul 1 Tahun</span>
          </div>

          <div class="w-full md:w-2/3 space-y-3 text-xs md:text-sm">
            <h3 class="font-black text-amber-900 text-base flex items-center gap-2">
              <span>💰</span> B. Ketentuan Lengkap Zakat Mal
            </h3>
            <p class="text-slate-700 leading-relaxed">
              <strong>Pengertian:</strong> Zakat atas harta tertentu yang dimiliki seseorang bila telah mencapai batas minimal (*nisab*) dan lama kepemilikan 1 tahun penuh (*haul*).
            </p>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2 pt-1">
              <div class="bg-white p-2.5 rounded-xl border border-amber-100 shadow-sm">
                <span class="font-bold text-amber-800 block mb-0.5">Syarat Harta Wajib Zakat:</span>
                <ul class="list-disc pl-4 text-[12px] text-slate-600 space-y-0.5">
                  <li>Milik penuh secara sah (halal).</li>
                  <li>Harta dapat berkembang secara produktif.</li>
                  <li>Mencapai <strong>Nisab</strong> (batas minimal).</li>
                  <li>Genap berjalan <strong>1 Haul</strong> (1 tahun hijriah).</li>
                </ul>
              </div>
              <div class="bg-white p-2.5 rounded-xl border border-amber-100 shadow-sm">
                <span class="font-bold text-amber-800 block mb-0.5">Nisab & Kadar Zakat:</span>
                <ul class="list-disc pl-4 text-[12px] text-slate-600 space-y-0.5">
                  <li><strong>Emas:</strong> Nisab 85 gram &bull; Kadar: <strong>2,5%</strong></li>
                  <li><strong>Perak:</strong> Nisab 595 gram &bull; Kadar: <strong>2,5%</strong></li>
                  <li><strong>Uang/Tabungan:</strong> Setara nilai 85g emas &bull; Kadar: <strong>2,5%</strong></li>
                  <li><strong>Pertanian:</strong> 653 kg gabah/beras &bull; Kadar: <strong>10%</strong> (hujan) / <strong>5%</strong> (irigasi biaya).</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- KARTU 3: 8 GOLONGAN ASNAF -->
      <div class="bg-slate-50 border-2 border-slate-200 rounded-3xl p-5 md:p-6 shadow-sm">
        <div class="text-center max-w-xl mx-auto mb-4">
          <span class="text-xs font-bold text-emerald-700 bg-emerald-100 px-3 py-0.5 rounded-full uppercase">Al-Qur'an Surat At-Taubah Ayat 60</span>
          <h3 class="text-base font-black text-slate-800 mt-1">👥 8 Golongan Penerima Zakat (Mustahiq)</h3>
          <p class="text-xs text-gray-500">Zakat hanya disalurkan kepada 8 asnaf berikut ini:</p>
        </div>

        <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 text-xs">
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">🏚️</span>
            <span class="font-black text-slate-800 block text-xs">1. Fakir</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Tak punya harta & pekerjaan halal, tak cukup separuh kebutuhan pokok.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">🛖</span>
            <span class="font-black text-slate-800 block text-xs">2. Miskin</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Memiliki penghasilan tapi masih kurang memenuhi kebutuhan dasar harian.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">📋</span>
            <span class="font-black text-slate-800 block text-xs">3. Amil</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Panitia resmi yang bertugas mengumpulkan dan membagikan zakat.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">🤝</span>
            <span class="font-black text-slate-800 block text-xs">4. Mualaf</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Orang yang baru masuk Islam agar semakin mantap keimanannya.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">⛓️</span>
            <span class="font-black text-slate-800 block text-xs">5. Riqab</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Hamba sahaya atau upaya memerdekakan tawanan muslim.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">📜</span>
            <span class="font-black text-slate-800 block text-xs">6. Gharim</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Orang berhutang untuk kepentingan halal dan tak mampu melunasi.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">⚔️</span>
            <span class="font-black text-slate-800 block text-xs">7. Fisabilillah</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Pejuang yang berjuang menegakkan kebaikan di jalan Allah SWT.</p>
          </div>
          <div class="bg-white p-3 rounded-2xl border border-slate-200 text-center shadow-sm">
            <span class="text-2xl block mb-1">🧭</span>
            <span class="font-black text-slate-800 block text-xs">8. Ibnu Sabil</span>
            <p class="text-[11px] text-gray-500 mt-0.5">Musafir yang kehabisan bekal dalam perjalanan ketaatan kepada Allah.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- 5. SIMULASI HITUNG -->
    <section id="viewSimulasi" class="hidden bg-white p-6 rounded-3xl shadow-lg">
      <div class="flex items-center justify-between mb-4 border-b pb-3">
        <h2 class="text-lg font-bold text-amber-700 flex items-center gap-2">🧮 Simulasi Hitung Zakat Otomatis</h2>
        <button type="button" onclick="showView('viewMenu')" class="text-xs bg-slate-100 hover:bg-slate-200 px-3 py-1.5 rounded-xl font-bold">Kembali ↩</button>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
        <div class="p-4 bg-emerald-50 rounded-2xl border border-emerald-200 text-xs">
          <h3 class="font-bold text-emerald-900 text-sm mb-2">🍚 Hitung Zakat Fitrah Keluarga</h3>
          <label class="block font-semibold mb-1">Jumlah Jiwa:</label>
          <input type="number" id="calcJiwa" value="5" min="1" class="w-full p-2 border rounded-xl mb-2 font-bold">
          <label class="block font-semibold mb-1">Harga Beras per Kg (Rp):</label>
          <input type="number" id="calcHarga" value="15000" class="w-full p-2 border rounded-xl mb-3 font-bold">
          <button type="button" onclick="runHitungFitrah()" class="w-full bg-emerald-600 text-white font-bold py-2 rounded-xl shadow cursor-pointer">Hitung 🧮</button>
          <div id="resFitrah" class="mt-2 font-medium text-slate-700"></div>
        </div>
        <div class="p-4 bg-amber-50 rounded-2xl border border-amber-200 text-xs">
          <h3 class="font-bold text-amber-900 text-sm mb-2">💰 Hitung Zakat Mal (Tabungan)</h3>
          <p class="text-[11px] text-gray-500 mb-2">Nisab = 85 gram emas (asumsi Rp 1.000.000/g = Rp 85.000.000) & Haul 1 tahun.</p>
          <label class="block font-semibold mb-1">Total Tabungan (Rp):</label>
          <input type="number" id="calcTabungan" value="100000000" class="w-full p-2 border rounded-xl mb-3 font-bold">
          <button type="button" onclick="runHitungMal()" class="w-full bg-amber-600 text-white font-bold py-2 rounded-xl shadow cursor-pointer">Hitung 🧮</button>
          <div id="resMal" class="mt-2 font-medium text-slate-700"></div>
        </div>
      </div>
    </section>

    <!-- 6. GAME 1: BALAP LARI RINTANGAN STADION 3D REALISTIS -->
    <section id="viewGame" class="hidden">
      <!-- Status Bar Game 1 -->
      <div class="bg-white p-3 md:p-4 rounded-2xl shadow mb-3 flex flex-wrap items-center justify-between gap-2 text-xs md:text-sm">
        <div class="flex items-center gap-2">
          <span class="px-2.5 py-1 bg-purple-100 text-purple-900 font-bold rounded-lg" id="runnerInfoBadge">Pelari: -</span>
          <span class="px-2.5 py-1 bg-amber-100 text-amber-900 font-bold rounded-lg">Rintangan: <span id="hurdleCounter">0/10</span></span>
        </div>
        <div class="flex items-center gap-3">
          <span class="font-black text-emerald-600 text-base md:text-lg">Skor: <span id="gameScoreText">0</span></span>
          <button type="button" onclick="showExitConfirmation('game1')" class="bg-rose-100 hover:bg-rose-200 text-rose-800 font-bold px-3 py-1 rounded-xl cursor-pointer">Keluar Game</button>
        </div>
      </div>

      <!-- Canvas Stadion 3D -->
      <div class="relative bg-slate-900 rounded-3xl overflow-hidden shadow-2xl border-4 border-slate-800">
        <canvas id="raceCanvas" width="900" height="420" class="w-full h-auto block"></canvas>
      </div>

      <!-- Tombol Navigasi Maju & Mundur Game 1 -->
      <div class="mt-4 bg-white p-3 rounded-2xl shadow flex items-center justify-center gap-4">
        <button id="btnBackward" class="flex-1 max-w-[200px] bg-slate-200 active:bg-slate-300 hover:bg-slate-300 text-slate-800 font-black py-3.5 rounded-2xl flex items-center justify-center gap-2 text-sm shadow cursor-pointer">
          <span>⏪</span> MUNDUR
        </button>
        <button id="btnForward" class="flex-1 max-w-[240px] bg-emerald-600 active:bg-emerald-700 hover:bg-emerald-700 text-white font-black py-3.5 rounded-2xl flex items-center justify-center gap-2 text-base shadow-lg cursor-pointer">
          MAJU <span>⏩</span>
        </button>
      </div>
      <p class="text-center text-[11px] text-gray-500 mt-2 font-medium">Bisa juga gunakan tombol keyboard panah (➡️ / ⬅️) atau tombol A / D.</p>
    </section>

    <!-- 7. GAME 2: TAMAN LABIRIN 3D BROADCAST VIEW (HALAMAN ISTANA LUAS) -->
    <section id="viewMazeGame" class="hidden">
      <!-- Status Bar Labirin -->
      <div class="bg-white p-3 md:p-4 rounded-2xl shadow mb-3 flex flex-wrap items-center justify-between gap-2 text-xs md:text-sm">
        <div class="flex items-center gap-2">
          <span class="px-2.5 py-1 bg-emerald-100 text-emerald-900 font-bold rounded-lg" id="mazePlayerBadge">Siswa: -</span>
          <span class="px-2.5 py-1 bg-rose-100 text-rose-900 font-bold rounded-lg">Iblis Diatasi: <span id="mazeDemonCounter">0/10</span></span>
        </div>
        <div class="flex items-center gap-3">
          <span class="font-black text-amber-600 text-base md:text-lg">Skor Iman: <span id="mazeScoreText">0</span></span>
          <button type="button" onclick="showExitConfirmation('game2')" class="bg-rose-100 hover:bg-rose-200 text-rose-800 font-bold px-3 py-1 rounded-xl cursor-pointer">Keluar Game</button>
        </div>
      </div>

      <!-- Area Canvas Labirin 3D -->
      <div class="relative bg-slate-950 rounded-3xl overflow-hidden shadow-2xl border-4 border-emerald-900 max-w-2xl mx-auto">
        <canvas id="mazeCanvas" width="640" height="640" class="w-full h-auto block mx-auto"></canvas>
      </div>

      <!-- Kontrol Navigasi D-Pad Virtual Labirin (Atas, Bawah, Kiri, Kanan) -->
      <div class="mt-4 bg-white p-4 rounded-3xl shadow-lg max-w-xs mx-auto text-center">
        <p class="text-[11px] font-bold text-slate-500 uppercase tracking-wider mb-2">Tombol Kendali Karakter 3D</p>
        <div class="grid grid-cols-3 gap-2 w-48 mx-auto">
          <div></div>
          <button id="btnMazeUp" class="bg-emerald-600 active:bg-emerald-800 text-white font-black p-3.5 rounded-2xl shadow hover:bg-emerald-700 text-lg cursor-pointer">⬆️</button>
          <div></div>
          <button id="btnMazeLeft" class="bg-emerald-600 active:bg-emerald-800 text-white font-black p-3.5 rounded-2xl shadow hover:bg-emerald-700 text-lg cursor-pointer">⬅️</button>
          <button id="btnMazeDown" class="bg-emerald-600 active:bg-emerald-800 text-white font-black p-3.5 rounded-2xl shadow hover:bg-emerald-700 text-lg cursor-pointer">⬇️</button>
          <button id="btnMazeRight" class="bg-emerald-600 active:bg-emerald-800 text-white font-black p-3.5 rounded-2xl shadow hover:bg-emerald-700 text-lg cursor-pointer">➡️</button>
        </div>
        <p class="text-[11px] text-gray-400 mt-2">Dapat menggunakan keyboard panah atau tombol W, A, S, D.</p>
      </div>
    </section>

  </main>

  <!-- ================= MODAL DIALOG SOAL (FIXED OVERLAY) ================= -->
  <!-- Modal Soal Game 1: Balap Lari -->
  <div id="quizOverlay" class="hidden fixed inset-0 z-50 flex items-center justify-center p-3 md:p-4 bg-slate-950/85 backdrop-blur-sm overflow-y-auto">
    <div class="bg-white rounded-3xl p-5 md:p-6 max-w-lg w-full shadow-2xl border-4 border-amber-400 fade-in my-auto max-h-[92vh] overflow-y-auto">
      <div class="flex justify-between items-center mb-3">
        <span class="bg-amber-100 text-amber-800 text-xs font-black px-2.5 py-1 rounded-full" id="quizObstacleTitle">Rintangan ke-1</span>
        <span class="text-xs text-gray-500 font-bold">PAI SD Kelas 6</span>
      </div>
      <h3 class="text-xs md:text-base font-bold text-slate-800 mb-4 leading-snug" id="quizQuestionText">Pertanyaan</h3>
      <div class="grid grid-cols-1 gap-2 text-xs md:text-sm" id="quizOptionsContainer"></div>
    </div>
  </div>

  <!-- Modal Soal Game 2: Taman Labirin 3D -->
  <div id="mazeQuizOverlay" class="hidden fixed inset-0 z-50 flex items-center justify-center p-3 md:p-4 bg-slate-950/85 backdrop-blur-sm overflow-y-auto">
    <div class="bg-gradient-to-b from-slate-900 to-rose-950 text-white rounded-3xl p-5 md:p-6 max-w-md w-full shadow-2xl border-4 border-rose-500 fade-in my-auto max-h-[92vh] overflow-y-auto">
      <div class="flex items-center justify-between mb-3 border-b border-rose-800/60 pb-2">
        <div class="flex items-center gap-2">
          <span class="text-2xl animate-bounce">👿</span>
          <div>
            <h4 class="text-xs font-black text-rose-400 uppercase tracking-widest" id="demonTitle">Bisikan Iblis Ke-1</h4>
            <p class="text-[10px] text-rose-200">"Tolak bisikanku dengan ilmu zakatmu!"</p>
          </div>
        </div>
        <span class="px-2 py-0.5 bg-rose-900/60 text-amber-300 font-bold text-[11px] rounded-full border border-rose-600">PAI Kelas 6</span>
      </div>

      <p class="text-xs md:text-sm font-semibold text-rose-100 mb-4 bg-black/50 p-3 rounded-2xl border border-rose-900/40 leading-snug" id="mazeQuestionText">
        Pertanyaan Zakat...
      </p>

      <div class="space-y-2 text-xs md:text-sm" id="mazeOptionsContainer"></div>
    </div>
  </div>

  <!-- ================= MODAL KONFIRMASI PINTU KELUAR GAME ================= -->
  <div id="exitConfirmModal" class="hidden fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-950/80 backdrop-blur-sm overflow-y-auto">
    <div class="bg-white rounded-3xl p-6 max-w-sm w-full shadow-2xl border-4 border-emerald-500 text-center fade-in my-auto">
      <div class="text-5xl mb-3 animate-bounce">🚪✨</div>
      <h3 class="text-lg font-black text-slate-800 mb-1">Pintu Keluar Ditemukan!</h3>
      <p class="text-xs text-slate-600 mb-3" id="exitConfirmSubtext">
        Kamu telah berada di pintu keluar. Apakah kamu ingin menyudahi permainan dan kembali ke Menu Utama?
      </p>
      <div class="bg-emerald-50 border border-emerald-200 rounded-2xl p-2.5 mb-4">
        <span class="text-[11px] font-bold text-emerald-800 uppercase block">Pencapaian Kamu</span>
        <span class="text-xl font-black text-emerald-600" id="exitConfirmScoreText">100 / 100 Poin</span>
      </div>
      <div class="flex flex-col gap-2">
        <button type="button" onclick="handleExitDecision(true)" class="w-full bg-emerald-600 hover:bg-emerald-700 active:bg-emerald-800 text-white font-bold py-3 px-4 rounded-xl shadow-md text-sm transition cursor-pointer flex items-center justify-center gap-2">
          <span>🏠 Ya, Kembali ke Menu Utama</span>
        </button>
        <button type="button" onclick="handleExitDecision(false)" class="w-full bg-slate-200 hover:bg-slate-300 active:bg-slate-400 text-slate-800 font-bold py-2.5 px-4 rounded-xl text-xs transition cursor-pointer flex items-center justify-center gap-2">
          <span>🏃‍♂️ Tidak, Lanjut Jalan-Jalan di Finis</span>
        </button>
      </div>
    </div>
  </div>

  <!-- ================= FOOTER ================= -->
  <footer class="bg-slate-200 border-t py-2.5 text-center text-xs text-slate-600 font-medium">
    PAI Ceria : Materi Kelas 6 Smt 1 Zakat Fitrah Dan Zakat Mal &bull; <strong class="text-slate-800">By : Bagus Abdianto</strong>
  </footer>

  <!-- ================= LOGIKA INTERAKTIF (JAVASCRIPT) ================= -->
  <script>
    // ----------------------------------------------------
    // 1. DATA USER & DEKLARASI GLOBAL VARIABLE LENGKAP
    // ----------------------------------------------------
    let student = null;
    let gameLoopId = null;
    let mazeGameLoopId = null;
    let audioCtx = null;
    let fireworks = [];
    let cameraShake = 0;
    let waitingQuiz = false;
    let mazeWaitingQuiz = false;
    let activeDemon = null;

    let activeExitGameType = null;
    let exitConfirmOpen = false;

    let mazeKeys = {
      up: false,
      down: false,
      left: false,
      right: false
    };

    // ====================================================
    // BANK SOAL LENGKAP (20 SOAL GAME 1 & 20 SOAL GAME 2)
    // ====================================================
    const rawBankGame1 = [
      { q: "Zakat yang wajib dikeluarkan setiap muslim menjelang Idul Fitri untuk menyucikan jiwa dinamakan...", options: ["Zakat Fitrah", "Zakat Mal", "Zakat Tijarah", "Wakaf Tunai"], correct: "Zakat Fitrah" },
      { q: "Takaran zakat fitrah berupa makanan pokok (beras) per orang adalah seberat...", options: ["2,5 kg", "1,5 kg", "3,0 kg", "5,0 kg"], correct: "2,5 kg" },
      { q: "Waktu yang paling utama (afdhal) untuk membayarkan zakat fitrah adalah...", options: ["Pagi hari menjelang shalat Idul Fitri", "Awal bulan Ramadan", "Pertengahan bulan Ramadan", "Setelah selesai shalat Idul Fitri"], correct: "Pagi hari menjelang shalat Idul Fitri" },
      { q: "Zakat atas harta kekayaan tertentu yang telah memenuhi syarat nisab dan haul disebut...", options: ["Zakat Mal", "Zakat Fitrah", "Fidyah", "Kafarat"], correct: "Zakat Mal" },
      { q: "Batas minimal jumlah harta kekayaan sehingga wajib dikeluarkan zakatnya disebut istilah...", options: ["Nisab", "Haul", "Kifarat", "Mustahiq"], correct: "Nisab" },
      { q: "Syarat lama kepemilikan harta yang telah mencapai jangka waktu satu tahun hijriah dinamakan...", options: ["Haul", "Nisab", "Kadar", "Asnaf"], correct: "Haul" },
      { q: "Nisab zakat mal untuk simpanan emas murni adalah setara dengan...", options: ["85 gram", "50 gram", "100 gram", "75 gram"], correct: "85 gram" },
      { q: "Berapakah persentase kadar zakat mal yang harus dikeluarkan untuk tabungan emas atau uang simpanan?", options: ["2,5%", "1%", "5%", "10%"], correct: "2,5%" },
      { q: "Orang yang baru saja memeluk agama Islam dan berhak menerima zakat disebut golongan...", options: ["Mualaf", "Amil", "Gharim", "Sabilillah"], correct: "Mualaf" },
      { q: "Petugas yang ditunjuk resmi bertugas menghimpun dan membagikan zakat dinamakan...", options: ["Amil", "Muzakki", "Ibnu Sabil", "Fakir"], correct: "Amil" },
      { q: "Hukum membayar zakat fitrah setelah matahari terbenam pada tanggal 1 Syawal (tanpa uzur syar'i) adalah...", options: ["Haram", "Makruh", "Mubah", "Sunnah"], correct: "Haram" },
      { q: "Zakat fitrah bila diukur dengan satuan volume takaran adalah sebesar...", options: ["3,5 liter", "2,0 liter", "4,5 liter", "5,0 liter"], correct: "3,5 liter" },
      { q: "Orang yang memiliki kewajiban untuk mengeluarkan zakat disebut dengan istilah...", options: ["Muzakki", "Mustahiq", "Munfiq", "Mukallaf"], correct: "Muzakki" },
      { q: "Nisab zakat perak murni yang wajib dizakati adalah seberat...", options: ["595 gram", "85 gram", "200 gram", "500 gram"], correct: "595 gram" },
      { q: "Kadar zakat hasil pertanian yang diairi hanya dengan air hujan murni (tadah hujan) adalah sebesar...", options: ["10%", "5%", "2,5%", "20%"], correct: "10%" },
      { q: "Kadar zakat hasil pertanian yang menggunakan irigasi berbayar atau tenaga mesin pompa adalah...", options: ["5%", "10%", "2,5%", "15%"], correct: "5%" },
      { q: "Surat dalam Al-Qur'an yang secara khusus menegaskan 8 golongan penerima zakat adalah...", options: ["QS. At-Taubah ayat 60", "QS. Al-Baqarah ayat 43", "QS. Al-Ma'un ayat 1-7", "QS. Ali 'Imran ayat 92"], correct: "QS. At-Taubah ayat 60" },
      { q: "Orang yang tidak memiliki harta dan pekerjaan serta tidak mampu memenuhi separuh kebutuhan pokoknya disebut...", options: ["Fakir", "Miskin", "Gharim", "Riqab"], correct: "Fakir" },
      { q: "Salah satu hikmah sosial utama dari pelaksanaan ibadah zakat adalah...", options: ["Mempererat persaudaraan dan mengurangi kesenjangan", "Memamerkan status kekayaan kepada sesama", "Menghabiskan harta yang dimiliki", "Mendapatkan pujian dari masyarakat"], correct: "Mempererat persaudaraan dan mengurangi kesenjangan" },
      { q: "Orang yang kehabisan bekal dalam perjalanan ketaatan atau musafir yang berhak menerima zakat disebut...", options: ["Ibnu Sabil", "Fisabilillah", "Gharimin", "Mualaf"], correct: "Ibnu Sabil" }
    ];

    const rawBankGame2 = [
      { q: "Iblis berbisik agar menunda bayar zakat fitrah sampai selesai salat Id. Jika dibayar setelah salat Idul Fitri tanpa uzur, hukumnya...", options: ["Menjadi sedekah biasa & berdosa jika sengaja", "Tetap sah sebagai zakat fitrah utama", "Pahalanya berlipat ganda", "Cukup diganti istighfar tanpa qadha"], correct: "Menjadi sedekah biasa & berdosa jika sengaja" },
      { q: "Iblis menghasut bahwa zakat hanya membuat miskin. Padahal secara bahasa, kata 'zakat' bermakna...", options: ["Berkembang, bertumbuh, dan menyucikan", "Menahan dan menimbun harta", "Mengurangi nilai tabungan", "Pinjaman yang berbunga"], correct: "Berkembang, bertumbuh, dan menyucikan" },
      { q: "Iblis membisikkan bahwa zakat boleh dibagikan kepada siapa saja. Siapakah yang berhak menerima zakat (Mustahiq)?", options: ["Hanya 8 golongan asnaf yang telah ditentukan syariat", "Pejabat tinggi dan saudagar kaya", "Teman akrab yang berkecukupan", "Kolega bisnis terdekat"], correct: "Hanya 8 golongan asnaf yang telah ditentukan syariat" },
      { q: "Iblis menggoda agar menahan zakat panen sawah. Berapa kadar zakat pertanian jika sawah diairi air hujan alami?", options: ["10%", "2,5%", "5%", "20%"], correct: "10%" },
      { q: "Iblis berbisik bahwa orang yang berhutang karena judi berhak dapat zakat. Syarat Gharimin yang berhak dibantu zakat adalah...", options: ["Berhutang demi kebutuhan pokok halal dan tak mampu melunasi", "Berhutang untuk taruhan dan foya-foya", "Orang kaya yang enggan membayar utang", "Berhutang demi gengsi membeli barang mewah"], correct: "Berhutang demi kebutuhan pokok halal dan tak mampu melunasi" },
      { q: "Iblis menghasut muzakki agar berbuat riya' (pamer). Apa akibat riya' dalam mengeluarkan zakat?", options: ["Menghapus pahala amal zakat", "Menambah kelipatan berkah harta", "Menjadikan zakat lebih afdhal", "Menggugurkan kewajiban salat"], correct: "Menghapus pahala amal zakat" },
      { q: "Iblis berbisik bahwa bayi yang lahir akhir Ramadan tak perlu dizakati. Bagaimana hukum zakat fitrah bagi bayi yang lahir sebelum matahari terbenam akhir Ramadan?", options: ["Wajib dibayarkan zakat fitrahnya oleh orang tua", "Tidak wajib karena belum baligh", "Hanya sunnah muakkad", "Cukup dibayar separuh takaran"], correct: "Wajib dibayarkan zakat fitrahnya oleh orang tua" },
      { q: "Iblis menyamarkan nisab emas. Berapakah batas minimal (nisab) simpanan emas batangan untuk wajib zakat mal?", options: ["85 gram emas murni", "50 gram emas murni", "100 gram emas murni", "65 gram emas murni"], correct: "85 gram emas murni" },
      { q: "Iblis berbisik agar Amil mengambil seluruh harta zakat untuk diri sendiri. Apa tugas Amil yang benar menurut syariat?", options: ["Menghimpun dan membagikan zakat secara amanah kepada mustahiq", "Menjual kembali beras zakat demi laba pribadi", "Menyimpan zakat di rekening pribadi selamanya", "Menyerahkan zakat hanya kepada keluarganya"], correct: "Menghimpun dan membagikan zakat secara amanah kepada mustahiq" },
      { q: "Iblis menganggap zakat amalan sepele. Dalam Al-Qur'an, perintah zakat seringkali digandengkan bersama perintah...", options: ["Mendirikan salat", "Berpuasa Ramadan", "Ibadah haji", "Membaca Al-Qur'an"], correct: "Mendirikan salat" },
      { q: "Iblis membisikkan bahwa harta warisan yang baru diterima sehari langsung wajib zakat mal tahunan. Syarat haul zakat mal adalah...", options: ["Harta telah dimiliki penuh genap selama 1 tahun hijriah", "Harta dimiliki minimal 1 bulan", "Cukup dimiliki selama 1 minggu", "Tidak ada syarat haul sama sekali"], correct: "Harta telah dimiliki penuh genap selama 1 tahun hijriah" },
      { q: "Iblis menggoda agar membayar zakat fitrah dengan beras yang sudah berjamur atau busuk. Ketentuan makanan zakat fitrah adalah...", options: ["Makanan pokok yang layak dan berkualitas baik yang biasa dimakan", "Sisa makanan yang sudah basi", "Biji-bijian yang telah rusak", "Bahan makanan apa pun yang paling murah tanpa peduli mutu"], correct: "Makanan pokok yang layak dan berkualitas baik yang biasa dimakan" },
      { q: "Iblis berbisik bahwa seorang mualaf yang kaya tidak boleh dirangkul. Mengapa mualaf berhak mendapat zakat?", options: ["Untuk memperteguh hati dan mempererat tali persaudaraan iman", "Sebagai upah karena telah berpindah agama", "Karena mereka pasti orang termiskin", "Untuk membeli aset milik mualaf"], correct: "Untuk memperteguh hati dan mempererat tali persaudaraan iman" },
      { q: "Iblis menghasut agar kita membenci amil zakat. Lembaga resmi yang menghimpun zakat di Indonesia secara sah adalah...", options: ["BAZNAS (Badan Amil Zakat Nasional)", "BUMN", "Dinas Pendapatan Daerah", "Koperasi Simpan Pinjam"], correct: "BAZNAS (Badan Amil Zakat Nasional)" },
      { q: "Iblis berbisik bahwa zakat mal uang tabungan hanya 1%. Berapakah kadar persentase zakat simpanan uang tabungan yang benar?", options: ["2,5%", "5%", "1%", "10%"], correct: "2,5%" },
      { q: "Iblis menggoda pejuang kebaikan agar pamrih. Golongan yang berjuang murni di jalan Allah dan berhak atas zakat disebut...", options: ["Fisabilillah", "Ibnu Sabil", "Mualaf", "Amil"], correct: "Fisabilillah" },
      { q: "Iblis berbisik bahwa zakat hanya simbol upacara. Apakah fungsi pensucian zakat sebagaimana tercantum dalam QS. At-Taubah ayat 103?", options: ["Membersihkan diri dari dosa dan menyucikan harta dari hak orang lain", "Hanya sekadar formalitas tahunan", "Mengumumkan nama dermawan kepada publik", "Menghapus catatan utang piutang negara"], correct: "Membersihkan diri dari dosa dan menyucikan harta dari hak orang lain" },
      { q: "Iblis meremehkan kaum dhuafa. Siapakah yang disebut asnaf 'Miskin' dalam pembagian zakat?", options: ["Orang yang punya mata pencaharian tetapi tidak mencukupi kebutuhan pokok", "Orang yang sama sekali tidak berdaya dan tanpa tempat tinggal", "Orang kaya yang sedang berhemat", "Pengusaha yang mengalami penurunan laba sementara"], correct: "Orang yang punya mata pencaharian tetapi tidak mencukupi kebutuhan pokok" },
      { q: "Iblis menghasut agar zakat fitrah dibayar di bulan Safar. Kapan batas awal waktu diperbolehkannya (mubah) membayar zakat fitrah?", options: ["Sejak hari pertama bulan Ramadan", "Sejak bulan Rajab", "Setelah Idul Adha", "Pada bulan Muharram"], correct: "Sejak hari pertama bulan Ramadan" },
      { q: "Iblis berbisik agar kita takut kekurangan bila berzakat. Hadis riwayat Muslim menegaskan bahwa sedekah dan zakat...", options: ["Tidak akan mengurangi harta, melainkan menambah keberkahan", "Pasti membuat pelakunya jatuh miskin", "Hanya membuang rezeki dengan sia-sia", "Membuat tabungan habis tanpa bekas"], correct: "Tidak akan mengurangi harta, melainkan menambah keberkahan" }
    ];

    // ====================================================
    // FUNGSI SHUFFLE (ALGORITMA FISHER-YATES ACAK AMAN)
    // ====================================================
    function shuffleArray(arr) {
      const copy = [...arr];
      for (let i = copy.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [copy[i], copy[j]] = [copy[j], copy[i]];
      }
      return copy;
    }

    function generateRandomSessionQuestions(bankPool, totalNeeded = 10) {
      const shuffledBank = shuffleArray(bankPool);
      const chosenQuestions = shuffledBank.slice(0, totalNeeded);

      return chosenQuestions.map(item => {
        const shuffledOptions = shuffleArray(item.options);
        const correctIndex = shuffledOptions.indexOf(item.correct);
        return {
          q: item.q,
          options: shuffledOptions,
          correct: correctIndex
        };
      });
    }

    function drawRoundedRect(context, x, y, width, height, radius) {
      if (context.roundRect) {
        context.beginPath();
        context.roundRect(x, y, width, height, radius);
      } else {
        context.beginPath();
        context.rect(x, y, width, height);
      }
    }

    // ----------------------------------------------------
    // 2. SYNTHESIZER AUDIO (Web Audio API)
    // ----------------------------------------------------
    function getAudioCtx() {
      try {
        if (!audioCtx) {
          audioCtx = new (window.AudioContext || window.webkitAudioContext)();
        }
        if (audioCtx && audioCtx.state === 'suspended') {
          audioCtx.resume();
        }
      } catch (err) {}
      return audioCtx;
    }

    function sfxStart() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.frequency.setValueAtTime(1800, ctx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(2400, ctx.currentTime + 0.1);
        gain.gain.setValueAtTime(0.25, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.35);
        osc.start();
        osc.stop(ctx.currentTime + 0.35);
      } catch (e) {}
    }

    function sfxJump() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.type = 'triangle';
        osc.frequency.setValueAtTime(320, ctx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(750, ctx.currentTime + 0.25);
        gain.gain.setValueAtTime(0.3, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.3);
        osc.start();
        osc.stop(ctx.currentTime + 0.3);
      } catch (e) {}
    }

    function sfxCrash() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.type = 'sawtooth';
        osc.frequency.setValueAtTime(160, ctx.currentTime);
        osc.frequency.linearRampToValueAtTime(50, ctx.currentTime + 0.35);
        gain.gain.setValueAtTime(0.4, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.4);
        osc.start();
        osc.stop(ctx.currentTime + 0.4);
      } catch (e) {}
    }

    function sfxCorrect() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.type = 'sine';
        osc.frequency.setValueAtTime(523.25, ctx.currentTime);
        osc.frequency.setValueAtTime(659.25, ctx.currentTime + 0.1);
        osc.frequency.setValueAtTime(783.99, ctx.currentTime + 0.2);
        gain.gain.setValueAtTime(0.3, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.4);
        osc.start();
        osc.stop(ctx.currentTime + 0.4);
      } catch (e) {}
    }

    function sfxHolyDefeat() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.type = 'sine';
        osc.frequency.setValueAtTime(440, ctx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(880, ctx.currentTime + 0.2);
        osc.frequency.exponentialRampToValueAtTime(1320, ctx.currentTime + 0.4);
        gain.gain.setValueAtTime(0.35, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.45);
        osc.start();
        osc.stop(ctx.currentTime + 0.45);
      } catch (e) {}
    }

    function sfxDemonHurt() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.type = 'sawtooth';
        osc.frequency.setValueAtTime(120, ctx.currentTime);
        osc.frequency.linearRampToValueAtTime(40, ctx.currentTime + 0.35);
        gain.gain.setValueAtTime(0.5, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.4);
        osc.start();
        osc.stop(ctx.currentTime + 0.4);
      } catch (e) {}
    }

    function sfxFirework() {
      try {
        const ctx = getAudioCtx();
        if (!ctx) return;
        const osc = ctx.createOscillator();
        const gain = ctx.createGain();
        osc.connect(gain);
        gain.connect(ctx.destination);
        osc.type = 'triangle';
        osc.frequency.setValueAtTime(400 + Math.random() * 300, ctx.currentTime);
        osc.frequency.exponentialRampToValueAtTime(100, ctx.currentTime + 0.25);
        gain.gain.setValueAtTime(0.2, ctx.currentTime);
        gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.3);
        osc.start();
        osc.stop(ctx.currentTime + 0.3);
      } catch (e) {}
    }

    // ----------------------------------------------------
    // 3. REGISTRASI & NAVIGASI SISTEM
    // ----------------------------------------------------
    function handleRegister(e) {
      if (e) e.preventDefault();

      const nameInput = document.getElementById('regName');
      const absenInput = document.getElementById('regAbsen');
      const genderInput = document.getElementById('regGender');

      if (!nameInput || !absenInput || !genderInput) return;

      student = {
        name: nameInput.value.trim(),
        absen: absenInput.value.trim(),
        gender: genderInput.value
      };

      if (!student.name || !student.absen || !student.gender) {
        alert("Harap lengkapi semua data diri terlebih dahulu!");
        return;
      }

      getAudioCtx();

      const greeting = document.getElementById('greetingName');
      if (greeting) greeting.innerText = student.name;

      const badgeName = document.getElementById('badgeName');
      if (badgeName) badgeName.innerText = `${student.name} (Absen ${student.absen}) - ${student.gender}`;

      const userBadge = document.getElementById('userBadge');
      if (userBadge) userBadge.classList.remove('hidden');

      showView('viewMenu');
    }

    function logout() {
      student = null;
      const form = document.getElementById('formRegister');
      if (form) form.reset();

      const userBadge = document.getElementById('userBadge');
      if (userBadge) userBadge.classList.add('hidden');

      resetGameStates();
      showView('viewRegister');
    }

    function resetGameStates() {
      if (gameLoopId) {
        cancelAnimationFrame(gameLoopId);
        gameLoopId = null;
      }
      if (mazeGameLoopId) {
        cancelAnimationFrame(mazeGameLoopId);
        mazeGameLoopId = null;
      }

      if (typeof player !== 'undefined' && player) {
        player.movingForward = false;
        player.movingBackward = false;
      }

      if (typeof mazePlayer !== 'undefined' && mazePlayer) {
        mazePlayer.vx = 0;
        mazePlayer.vy = 0;
      }

      mazeKeys.up = false;
      mazeKeys.down = false;
      mazeKeys.left = false;
      mazeKeys.right = false;

      waitingQuiz = false;
      mazeWaitingQuiz = false;
      cameraShake = 0;
      exitConfirmOpen = false;
      activeExitGameType = null;

      const q1 = document.getElementById('quizOverlay');
      if (q1) q1.classList.add('hidden');
      const q2 = document.getElementById('mazeQuizOverlay');
      if (q2) q2.classList.add('hidden');
      const exitModal = document.getElementById('exitConfirmModal');
      if (exitModal) exitModal.classList.add('hidden');

      document.body.style.overflow = 'auto';
      document.documentElement.style.overflow = 'auto';
    }

    function showView(viewId) {
      resetGameStates();

      const views = ['viewRegister', 'viewMenu', 'viewPetunjuk', 'viewMateri', 'viewSimulasi', 'viewGame', 'viewMazeGame'];
      views.forEach(id => {
        const el = document.getElementById(id);
        if (el) el.classList.add('hidden');
      });

      const target = document.getElementById(viewId);
      if (target) {
        target.classList.remove('hidden');
      }

      window.scrollTo({ top: 0, behavior: 'instant' });
    }

    function showExitConfirmation(gameType) {
      activeExitGameType = gameType;
      exitConfirmOpen = true;

      const scoreText = gameType === 'game1' ? `${gameScore} / 100 Poin` : `${mazeScore} / 100 Poin`;
      const scoreEl = document.getElementById('exitConfirmScoreText');
      if (scoreEl) scoreEl.innerText = scoreText;

      const modal = document.getElementById('exitConfirmModal');
      if (modal) modal.classList.remove('hidden');
    }

    function handleExitDecision(isConfirmed) {
      const modal = document.getElementById('exitConfirmModal');
      if (modal) modal.classList.add('hidden');
      exitConfirmOpen = false;

      if (isConfirmed) {
        if (activeExitGameType === 'game1') {
          exitGame();
        } else {
          exitMazeGame();
        }
      } else {
        if (activeExitGameType === 'game1') {
          player.worldX = EXIT_DOOR_X - 160;
          player.movingForward = false;
          player.movingBackward = false;
        } else {
          mazePlayer.y = 2.2 * TILE_SIZE;
          mazePlayer.vx = 0;
          mazePlayer.vy = 0;
        }
      }
    }

    // ----------------------------------------------------
    // 4. SIMULASI KALKULATOR
    // ----------------------------------------------------
    function runHitungFitrah() {
      const jiwa = parseInt(document.getElementById('calcJiwa').value) || 0;
      const harga = parseInt(document.getElementById('calcHarga').value) || 0;
      const kg = (jiwa * 2.5).toFixed(1);
      const liter = (jiwa * 3.5).toFixed(1);
      const uang = (jiwa * 2.5 * harga).toLocaleString('id-ID');
      document.getElementById('resFitrah').innerHTML = `
        🌾 Beras: <strong>${kg} kg</strong> atau <strong>${liter} liter</strong><br>
        💵 Setara Uang: <strong>Rp ${uang}</strong>
      `;
    }

    function runHitungMal() {
      const tab = parseInt(document.getElementById('calcTabungan').value) || 0;
      const nisab = 85000000;
      if (tab >= nisab) {
        const zakat = (tab * 0.025).toLocaleString('id-ID');
        document.getElementById('resMal').innerHTML = `
          <span class="text-emerald-700 font-bold">✅ Mencapai Nisab!</span><br>
          Kewajiban Zakat (2,5%): <strong>Rp ${zakat}</strong>
        `;
      } else {
        document.getElementById('resMal').innerHTML = `
          <span class="text-rose-600 font-bold">❌ Belum Mencapai Nisab!</span><br>
          (Kurang Rp ${(nisab - tab).toLocaleString('id-ID')} lagi).
        `;
      }
    }

    // ====================================================
    // PARTIKEL KEMBANG API (FIREWORKS)
    // ====================================================
    function spawnFirework(x, y) {
      sfxFirework();
      const colors = ['#f59e0b', '#ef4444', '#10b981', '#38bdf8', '#ec4899', '#facc15', '#a855f7'];
      for (let i = 0; i < 35; i++) {
        const angle = Math.random() * Math.PI * 2;
        const speed = 2 + Math.random() * 4.5;
        fireworks.push({
          x: x,
          y: y,
          vx: Math.cos(angle) * speed,
          vy: Math.sin(angle) * speed,
          color: colors[Math.floor(Math.random() * colors.length)],
          alpha: 1,
          size: 2 + Math.random() * 3,
          decay: 0.02 + Math.random() * 0.02
        });
      }
    }

    function updateAndRenderFireworks(context) {
      for (let i = fireworks.length - 1; i >= 0; i--) {
        const p = fireworks[i];
        p.x += p.vx;
        p.y += p.vy;
        p.vy += 0.05;
        p.alpha -= p.decay;
        if (p.alpha <= 0) {
          fireworks.splice(i, 1);
        } else {
          context.save();
          context.globalAlpha = p.alpha;
          context.fillStyle = p.color;
          context.beginPath();
          context.arc(p.x, p.y, p.size, 0, Math.PI * 2);
          context.fill();
          context.restore();
        }
      }
    }

    // ====================================================
    // 5. ENGINE GAME 1: BALAP LARI STADION 3D REALISTIS
    // ====================================================
    const canvas = document.getElementById('raceCanvas');
    const ctx = canvas.getContext('2d');

    let gameScore = 0;
    let hurdles = [];
    const FINISH_LINE_X = 5000;
    const EXIT_DOOR_X = 6800;
    const TRACK_TOTAL_LENGTH = 7100;
    const HURDLE_SPACING = 440;

    let player = {
      worldX: 150,
      laneY: 310,
      jumpY: 0,
      state: 'run',
      timer: 0,
      rotation: 0,
      movingForward: false,
      movingBackward: false,
      hasFinished: false
    };

    function initHurdles() {
      hurdles = [];
      const sessionQuestions = generateRandomSessionQuestions(rawBankGame1, 10);
      for (let i = 0; i < 10; i++) {
        hurdles.push({
          index: i,
          worldX: 600 + (i * HURDLE_SPACING),
          solved: false,
          knockedDown: false,
          question: sessionQuestions[i]
        });
      }
    }

    function startGame() {
      if (!student) { showView('viewRegister'); return; }
      resetGameStates();
      showView('viewGame');

      document.getElementById('runnerInfoBadge').innerText = `Pelari: ${student.name} (${student.gender === 'Laki-laki' ? '👦 Berpeci' : '👧 Berhijab'})`;

      gameScore = 0;
      player.worldX = 150;
      player.jumpY = 0;
      player.state = 'run';
      player.timer = 0;
      player.rotation = 0;
      player.movingForward = false;
      player.movingBackward = false;
      player.hasFinished = false;
      waitingQuiz = false;
      fireworks = [];

      initHurdles();
      updateGameUI();
      sfxStart();

      gameLoop();
    }

    function updateGameUI() {
      document.getElementById('gameScoreText').innerText = gameScore;
      const cleared = hurdles.filter(h => h.solved).length;
      document.getElementById('hurdleCounter').innerText = `${cleared}/10`;
    }

    function exitGame() {
      resetGameStates();
      showView('viewMenu');
    }

    const btnFwd = document.getElementById('btnForward');
    const btnBwd = document.getElementById('btnBackward');

    btnFwd.onmousedown = () => { player.movingForward = true; };
    btnFwd.onmouseup = () => { player.movingForward = false; };
    btnFwd.ontouchstart = (e) => { e.preventDefault(); player.movingForward = true; };
    btnFwd.ontouchend = (e) => { e.preventDefault(); player.movingForward = false; };

    btnBwd.onmousedown = () => { player.movingBackward = true; };
    btnBwd.onmouseup = () => { player.movingBackward = false; };
    btnBwd.ontouchstart = (e) => { e.preventDefault(); player.movingBackward = true; };
    btnBwd.ontouchend = (e) => { e.preventDefault(); player.movingBackward = false; };

    window.addEventListener('keydown', (e) => {
      if (document.getElementById('viewGame').classList.contains('hidden')) return;
      if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') player.movingForward = true;
      if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') player.movingBackward = true;
    });
    window.addEventListener('keyup', (e) => {
      if (document.getElementById('viewGame').classList.contains('hidden')) return;
      if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') player.movingForward = false;
      if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') player.movingBackward = false;
    });

    function gameLoop() {
      updateGamePhysics();
      renderBroadcastStadium();
      gameLoopId = requestAnimationFrame(gameLoop);
    }

    function updateGamePhysics() {
      player.timer++;

      if (player.hasFinished && player.timer % 35 === 0) {
        const camX = player.worldX - 250;
        spawnFirework(camX + 150 + Math.random() * 500, 60 + Math.random() * 80);
      }

      if (player.state === 'jump') {
        player.worldX += 4.5;
        if (player.jumpProgress < Math.PI) {
          player.jumpProgress += 0.08;
          player.jumpY = Math.sin(player.jumpProgress) * 72;
        } else {
          player.state = 'run';
          player.jumpY = 0;
        }
        return;
      }

      if (player.state === 'stumble') {
        player.stumbleTimer--;
        if (player.stumbleTimer > 20) {
          player.rotation = Math.min(Math.PI / 2, player.rotation + 0.15);
          player.worldX += 1.5;
        } else {
          player.rotation = Math.max(0, player.rotation - 0.1);
        }
        if (player.stumbleTimer <= 0) {
          player.state = 'run';
          player.rotation = 0;
        }
        return;
      }

      if (!waitingQuiz) {
        if (player.movingForward) {
          player.worldX += 5.2;
        }
        if (player.movingBackward && player.worldX > 120) {
          player.worldX -= 4.2;
        }

        if (player.worldX >= FINISH_LINE_X && !player.hasFinished) {
          player.hasFinished = true;
          spawnFirework(player.worldX - 50, 90);
          spawnFirework(player.worldX + 50, 70);
        }

        if (player.worldX >= EXIT_DOOR_X && !exitConfirmOpen) {
          player.movingForward = false;
          player.movingBackward = false;
          showExitConfirmation('game1');
          return;
        }

        for (let h of hurdles) {
          if (!h.solved) {
            if (player.worldX >= h.worldX - 60 && player.worldX <= h.worldX) {
              player.movingForward = false;
              triggerHurdleQuiz(h);
              break;
            }
          }
        }
      }
    }

    function triggerHurdleQuiz(hurdle) {
      waitingQuiz = true;
      const q = hurdle.question;

      document.getElementById('quizObstacleTitle').innerText = `Rintangan ${hurdle.index + 1} dari 10`;
      document.getElementById('quizQuestionText').innerText = `${hurdle.index + 1}. ${q.q}`;

      const optContainer = document.getElementById('quizOptionsContainer');
      optContainer.innerHTML = '';

      q.options.forEach((opt, idx) => {
        const btn = document.createElement('button');
        btn.type = "button";
        btn.className = "w-full text-left p-3.5 rounded-2xl border-2 border-slate-200 hover:border-emerald-500 hover:bg-emerald-50 font-semibold transition active:scale-95 text-xs md:text-sm flex items-start gap-2 shadow-sm cursor-pointer";
        btn.innerHTML = `<span class="inline-flex items-center justify-center min-w-[22px] h-[22px] bg-slate-200 text-slate-800 rounded-full font-bold text-xs shrink-0">${String.fromCharCode(65+idx)}</span> <span>${opt}</span>`;
        btn.onclick = () => answerHurdle(idx, hurdle);
        optContainer.appendChild(btn);
      });

      document.getElementById('quizOverlay').classList.remove('hidden');
    }

    function answerHurdle(chosenIdx, hurdle) {
      document.getElementById('quizOverlay').classList.add('hidden');
      waitingQuiz = false;
      hurdle.solved = true;

      const isCorrect = (chosenIdx === hurdle.question.correct);

      if (isCorrect) {
        gameScore += 10;
        player.state = 'jump';
        player.jumpProgress = 0;
        sfxCorrect();
        setTimeout(sfxJump, 100);
      } else {
        hurdle.knockedDown = true;
        player.state = 'stumble';
        player.stumbleTimer = 45;
        sfxCrash();
      }
      updateGameUI();
    }

    function renderBroadcastStadium() {
      const W = canvas.width;
      const H = canvas.height;
      const cameraX = player.worldX - 250;

      ctx.clearRect(0, 0, W, H);

      const skyGrad = ctx.createLinearGradient(0, 0, 0, 110);
      skyGrad.addColorStop(0, '#0f172a');
      skyGrad.addColorStop(0.6, '#1e293b');
      skyGrad.addColorStop(1, '#334155');
      ctx.fillStyle = skyGrad;
      ctx.fillRect(0, 0, W, 110);

      for (let lx = 60; lx < W; lx += 240) {
        ctx.fillStyle = '#64748b';
        ctx.fillRect(lx, 15, 6, 60);
        ctx.fillStyle = 'rgba(254, 240, 138, 0.25)';
        ctx.beginPath();
        ctx.moveTo(lx + 3, 15);
        ctx.lineTo(lx - 60, 220);
        ctx.lineTo(lx + 65, 220);
        ctx.fill();
        ctx.fillStyle = '#fef08a';
        ctx.beginPath();
        ctx.arc(lx + 3, 15, 6, 0, Math.PI * 2);
        ctx.fill();
      }

      for (let tier = 0; tier < 4; tier++) {
        const ty = 75 + (tier * 22);
        ctx.fillStyle = (tier % 2 === 0) ? '#334155' : '#475569';
        ctx.fillRect(0, ty, W, 22);

        const crowdColors = ['#f43f5e', '#3b82f6', '#10b981', '#f59e0b', '#ec4899', '#ffffff', '#a855f7'];
        for (let cx = 0; cx < W; cx += 22) {
          const shift = Math.sin((cx + player.timer * 3) * 0.06) * 3;
          ctx.fillStyle = crowdColors[(cx + tier * 3) % crowdColors.length];
          ctx.beginPath();
          ctx.arc(cx + 10, ty + 12 + shift, 5.5, 0, Math.PI * 2);
          ctx.fill();
        }
      }

      ctx.fillStyle = '#090d16';
      ctx.fillRect(0, 165, W, 30);
      ctx.fillStyle = '#38bdf8';
      ctx.font = 'bold 11px sans-serif';
      const bannerScroll = (cameraX * 0.5) % 360;
      for (let bx = -bannerScroll; bx < W; bx += 360) {
        ctx.fillText("🌟 PAI SD KELAS 6 • ZAKAT FITRAH & ZAKAT MAL • BY BAGUS ABDIANTO 🌟", bx, 184);
      }

      const fieldGrad = ctx.createLinearGradient(0, 195, 0, 235);
      fieldGrad.addColorStop(0, '#166534');
      fieldGrad.addColorStop(1, '#15803d');
      ctx.fillStyle = fieldGrad;
      ctx.fillRect(0, 195, W, 40);

      const trackGrad = ctx.createLinearGradient(0, 235, 0, H);
      trackGrad.addColorStop(0, '#b91c1c');
      trackGrad.addColorStop(0.5, '#991b1b');
      trackGrad.addColorStop(1, '#7f1d1d');
      ctx.fillStyle = trackGrad;
      ctx.fillRect(0, 235, W, H - 235);

      ctx.strokeStyle = '#ffffff';
      ctx.lineWidth = 2.5;
      [240, 290, 345, 400].forEach(laneY => {
        ctx.beginPath();
        ctx.moveTo(0, laneY);
        ctx.lineTo(W, laneY);
        ctx.stroke();
      });

      ctx.fillStyle = 'rgba(255,255,255,0.7)';
      ctx.font = 'bold 12px sans-serif';
      for (let markX = 300; markX <= TRACK_TOTAL_LENGTH; markX += 300) {
        const screenMarkX = markX - cameraX;
        if (screenMarkX > -50 && screenMarkX < W + 50) {
          ctx.fillText(`${markX / 10} m`, screenMarkX, 395);
        }
      }

      const screenStartX = 150 - cameraX;
      if (screenStartX > -100 && screenStartX < W + 100) {
        drawChequeredLine(screenStartX, 240, 400, "START");
      }

      const screenFinishX = FINISH_LINE_X - cameraX;
      if (screenFinishX > -150 && screenFinishX < W + 150) {
        drawChequeredLine(screenFinishX, 240, 400, "FINIS");
        ctx.fillStyle = '#d97706';
        ctx.fillRect(screenFinishX - 10, 110, 18, 290);
        ctx.fillStyle = '#b45309';
        ctx.fillRect(screenFinishX - 6, 110, 6, 290);
        ctx.fillStyle = '#dc2626';
        ctx.fillRect(screenFinishX - 70, 110, 140, 40);
        ctx.fillStyle = '#ffffff';
        ctx.font = '900 14px sans-serif';
        ctx.textAlign = 'center';
        ctx.fillText("🏆 GARIS FINIS 🏆", screenFinishX, 135);
      }

      const podiumX = 5400 - cameraX;
      if (podiumX > -150 && podiumX < W + 150) {
        ctx.fillStyle = '#64748b';
        ctx.fillRect(podiumX - 60, 260, 40, 60);
        ctx.fillStyle = '#ffffff';
        ctx.font = 'bold 16px sans-serif';
        ctx.fillText("2", podiumX - 40, 295);

        ctx.fillStyle = '#f59e0b';
        ctx.fillRect(podiumX - 20, 240, 40, 80);
        ctx.fillStyle = '#ffffff';
        ctx.fillText("1", podiumX, 280);

        ctx.fillStyle = '#b45309';
        ctx.fillRect(podiumX + 20, 280, 40, 40);
        ctx.fillStyle = '#ffffff';
        ctx.fillText("3", podiumX + 40, 305);

        ctx.font = 'bold 11px sans-serif';
        ctx.fillStyle = '#fef08a';
        ctx.fillText("🏆 PODIUM JUARA PAI 🏆", podiumX, 230);
      }

      const fountainX = 6000 - cameraX;
      if (fountainX > -150 && fountainX < W + 150) {
        ctx.fillStyle = 'rgba(0,0,0,0.3)';
        ctx.beginPath();
        ctx.ellipse(fountainX, 320, 50, 18, 0, 0, Math.PI * 2);
        ctx.fill();

        ctx.fillStyle = '#e2e8f0';
        ctx.beginPath();
        ctx.ellipse(fountainX, 310, 46, 16, 0, 0, Math.PI * 2);
        ctx.fill();

        ctx.fillStyle = '#38bdf8';
        ctx.beginPath();
        ctx.ellipse(fountainX, 308, 40, 12, 0, 0, Math.PI * 2);
        ctx.fill();

        ctx.strokeStyle = '#ffffff';
        ctx.lineWidth = 3;
        const sprayH = Math.sin(player.timer * 0.1) * 6;
        ctx.beginPath();
        ctx.moveTo(fountainX, 308);
        ctx.lineTo(fountainX, 260 + sprayH);
        ctx.stroke();

        ctx.fillStyle = '#38bdf8';
        ctx.font = 'bold 11px sans-serif';
        ctx.fillText("⛲ Air Mancur Selebrasi", fountainX, 250);
      }

      const screenExitX = EXIT_DOOR_X - cameraX;
      if (screenExitX > -200 && screenExitX < W + 200) {
        ctx.fillStyle = '#064e3b';
        ctx.fillRect(screenExitX - 35, 170, 70, 230);
        ctx.fillStyle = '#10b981';
        ctx.fillRect(screenExitX - 25, 180, 50, 215);

        ctx.fillStyle = '#047857';
        ctx.beginPath();
        ctx.arc(screenExitX, 230, 22, Math.PI, 0);
        ctx.fillRect(screenExitX - 22, 230, 44, 160);
        ctx.fill();

        ctx.fillStyle = '#ffffff';
        ctx.font = 'bold 12px sans-serif';
        ctx.textAlign = 'center';
        ctx.fillText("🚪 PINTU KELUAR", screenExitX, 150);
        ctx.font = '900 11px sans-serif';
        ctx.fillStyle = '#fef08a';
        ctx.fillText("(MENU UTAMA)", screenExitX, 165);
      }

      hurdles.forEach(h => {
        const screenHX = h.worldX - cameraX;
        if (screenHX > -50 && screenHX < W + 50) {
          drawHurdle(screenHX, 300, h);
        }
      });

      updateAndRenderFireworks(ctx);

      const screenPX = player.worldX - cameraX;
      const screenPY = player.laneY - player.jumpY;
      draw3DAthlete(screenPX, screenPY);

      if (player.hasFinished) {
        ctx.save();
        ctx.fillStyle = 'rgba(15, 23, 42, 0.88)';
        ctx.strokeStyle = '#f59e0b';
        ctx.lineWidth = 3;
        const boxW = Math.min(540, W - 40);
        const boxX = (W - boxW) / 2;
        drawRoundedRect(ctx, boxX, 15, boxW, 82, 16);
        ctx.fill();
        ctx.stroke();

        ctx.textAlign = 'center';
        ctx.font = '900 15px sans-serif';
        ctx.fillStyle = '#fde047';
        ctx.fillText(`🏆 SELAMAT! ${student.name.toUpperCase()} TUNTAS FINIS! 🏆`, W / 2, 38);

        ctx.font = 'bold 12px sans-serif';
        ctx.fillStyle = '#ffffff';
        ctx.fillText(`Skor Akhir: ${gameScore} / 100 Poin  •  Jalan bebas di pelataran menuju PINTU KELUAR ➡️`, W / 2, 58);

        ctx.font = '500 11px sans-serif';
        ctx.fillStyle = '#38bdf8';
        ctx.fillText("Karakter masih leluasa maju mundur mengunjungi podium & air mancur!", W / 2, 78);
        ctx.restore();
      }
    }

    function drawChequeredLine(x, topY, botY, label) {
      const squareSize = 10;
      let toggle = false;
      for (let y = topY; y < botY; y += squareSize) {
        ctx.fillStyle = toggle ? '#ffffff' : '#0f172a';
        ctx.fillRect(x - 5, y, 10, squareSize);
        toggle = !toggle;
      }
      ctx.fillStyle = '#ffffff';
      ctx.font = '900 13px sans-serif';
      ctx.textAlign = 'center';
      ctx.fillText(label, x, topY - 10);
    }

    function drawHurdle(x, y, hurdle) {
      ctx.save();
      if (hurdle.knockedDown) {
        ctx.translate(x + 20, y + 25);
        ctx.rotate(Math.PI / 2.8);
      } else {
        ctx.translate(x, y);
      }

      ctx.fillStyle = 'rgba(0,0,0,0.3)';
      ctx.fillRect(-2, 12, 48, 6);

      ctx.fillStyle = '#cbd5e1';
      ctx.fillRect(0, -30, 6, 42);
      ctx.fillRect(36, -30, 6, 42);

      ctx.fillStyle = hurdle.solved ? (hurdle.knockedDown ? '#ef4444' : '#10b981') : '#f97316';
      ctx.fillRect(-4, -36, 50, 14);
      ctx.fillStyle = '#ffffff';
      ctx.fillRect(8, -36, 12, 14);
      ctx.fillRect(28, -36, 12, 14);

      ctx.fillStyle = '#0f172a';
      ctx.font = 'bold 9px sans-serif';
      ctx.textAlign = 'center';
      ctx.fillText(`R${hurdle.index + 1}`, 21, -25);

      ctx.restore();
    }

    function draw3DAthlete(x, y) {
      ctx.save();
      ctx.translate(x, y);
      ctx.rotate(player.rotation);

      const isMale = (student && student.gender === 'Laki-laki');
      const isMoving = (player.movingForward || player.movingBackward);
      const swing = isMoving ? Math.sin(player.timer * 0.35) * 16 : 0;

      ctx.fillStyle = 'rgba(0,0,0,0.3)';
      ctx.beginPath();
      ctx.ellipse(0, 16 + player.jumpY * 0.5, 20, 8, 0, 0, Math.PI * 2);
      ctx.fill();

      ctx.lineWidth = 6;
      ctx.lineCap = 'round';
      ctx.strokeStyle = '#0f172a';

      ctx.beginPath();
      ctx.moveTo(-3, 0);
      ctx.lineTo(-7 - swing, 14);
      ctx.stroke();

      ctx.beginPath();
      ctx.moveTo(3, 0);
      ctx.lineTo(7 + swing, 14);
      ctx.stroke();

      ctx.fillStyle = '#f59e0b';
      ctx.fillRect(-9 - swing, 12, 9, 6);
      ctx.fillRect(5 + swing, 12, 9, 6);

      const jerseyGrad = ctx.createLinearGradient(-10, -24, 10, 0);
      jerseyGrad.addColorStop(0, '#047857');
      jerseyGrad.addColorStop(1, '#059669');
      ctx.fillStyle = jerseyGrad;
      drawRoundedRect(ctx, -11, -24, 22, 24, 4);
      ctx.fill();

      ctx.fillStyle = '#ffffff';
      ctx.font = '900 10px sans-serif';
      ctx.textAlign = 'center';
      ctx.fillText(student.absen || "6", 0, -8);

      if (player.hasFinished) {
        ctx.strokeStyle = '#fcd34d';
        ctx.lineWidth = 4;
        ctx.beginPath();
        ctx.moveTo(-8, -18);
        ctx.lineTo(-12, -38);
        ctx.stroke();

        ctx.beginPath();
        ctx.moveTo(8, -18);
        ctx.lineTo(12, -38);
        ctx.stroke();

        ctx.fillStyle = '#fbbf24';
        ctx.beginPath();
        ctx.arc(0, -50, 10, 0, Math.PI);
        ctx.fill();
        ctx.fillRect(-4, -40, 8, 8);
        ctx.fillRect(-8, -32, 16, 4);

        ctx.strokeStyle = '#f59e0b';
        ctx.lineWidth = 2.5;
        ctx.strokeRect(-13, -51, 26, 6);
      } else {
        ctx.strokeStyle = '#fbcfe8';
        ctx.lineWidth = 4.5;
        ctx.beginPath();
        ctx.moveTo(-8, -18);
        ctx.lineTo(-15 + swing, -8);
        ctx.stroke();

        ctx.beginPath();
        ctx.moveTo(8, -18);
        ctx.lineTo(15 - swing, -8);
        ctx.stroke();
      }

      ctx.fillStyle = '#fcd34d';
      ctx.beginPath();
      ctx.arc(0, -34, 10, 0, Math.PI * 2);
      ctx.fill();

      ctx.fillStyle = '#1e293b';
      ctx.beginPath();
      ctx.arc(3, -35, 1.8, 0, Math.PI * 2);
      ctx.fill();

      if (player.state === 'stumble') {
        ctx.strokeStyle = '#ef4444';
        ctx.lineWidth = 2;
        ctx.strokeText("x", 2, -33);
      } else {
        ctx.strokeStyle = '#1e293b';
        ctx.lineWidth = 1.5;
        ctx.beginPath();
        ctx.arc(2, -32, 4, 0, Math.PI * 0.7);
        ctx.stroke();
      }

      if (isMale) {
        ctx.fillStyle = '#0f172a';
        ctx.fillRect(-9, -44, 18, 9);
        ctx.fillStyle = '#334155';
        ctx.fillRect(-9, -44, 18, 2);
      } else {
        ctx.fillStyle = '#ec4899';
        ctx.beginPath();
        ctx.arc(0, -36, 12, Math.PI * 0.8, Math.PI * 2.2);
        ctx.fill();
        ctx.beginPath();
        ctx.moveTo(-11, -32);
        ctx.lineTo(-13, -20);
        ctx.lineTo(6, -20);
        ctx.lineTo(11, -29);
        ctx.closePath();
        ctx.fill();
      }

      ctx.restore();
    }

    // ====================================================
    // 6. ENGINE GAME 2: TAMAN LABIRIN 3D BROADCAST VIEW
    // ====================================================
    const mazeCanvas = document.getElementById('mazeCanvas');
    const mCtx = mazeCanvas.getContext('2d');

    const MAZE_WORLD_COLS = 22;
    const MAZE_WORLD_ROWS = 27;
    const TILE_SIZE = 48;

    const baseGrid = [
      [1, 1, 1, 1, 1, 1, 0, 0, 1, 1, 1, 1, 1, 1],
      [1, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 1],
      [1, 0, 1, 0, 1, 1, 1, 1, 0, 1, 0, 1, 0, 1],
      [1, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1],
      [1, 0, 1, 1, 1, 1, 0, 1, 1, 1, 0, 1, 0, 1],
      [1, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1, 0, 1],
      [1, 1, 1, 1, 0, 1, 1, 1, 0, 1, 0, 1, 0, 1],
      [1, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1],
      [1, 0, 1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 1],
      [1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 1, 0, 1],
      [1, 1, 1, 1, 0, 1, 1, 1, 1, 1, 0, 1, 0, 1],
      [1, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 1],
      [1, 0, 1, 1, 1, 1, 1, 1, 0, 1, 1, 1, 0, 1],
      [1, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 1, 0, 1],
      [1, 0, 0, 0, 1, 1, 0, 0, 0, 1, 0, 0, 0, 1],
      [1, 1, 1, 1, 1, 1, 0, 0, 1, 1, 1, 1, 1, 1]
    ];

    const mazeWorld = [];
    const OFFSET_COL = 4;
    const OFFSET_ROW = 7;

    for (let r = 0; r < MAZE_WORLD_ROWS; r++) {
      mazeWorld[r] = [];
      for (let c = 0; c < MAZE_WORLD_COLS; c++) {
        if (r < OFFSET_ROW) {
          if (c < 3 || c >= MAZE_WORLD_COLS - 3) {
            mazeWorld[r][c] = 2;
          } else {
            mazeWorld[r][c] = 0;
          }
        } else if (r >= OFFSET_ROW + 16) {
          if (c < 3 || c >= MAZE_WORLD_COLS - 3) {
            mazeWorld[r][c] = 2;
          } else {
            mazeWorld[r][c] = 0;
          }
        } else {
          if (c < OFFSET_COL || c >= OFFSET_COL + 14) {
            mazeWorld[r][c] = 2;
          } else {
            mazeWorld[r][c] = baseGrid[r - OFFSET_ROW][c - OFFSET_COL];
          }
        }
      }
    }

    // POSISI 10 IBLIS DI LORONG TERBUKA JALUR UTAMA
    // Posisi Iblis ke-2 telah diperbaiki ke (col: OFFSET_COL + 8, row: OFFSET_ROW + 13) yang bebas dari semak
    const demonPositions = [
      { col: OFFSET_COL + 6, row: OFFSET_ROW + 14 }, // Iblis 1: Koridor masuk
      { col: OFFSET_COL + 8, row: OFFSET_ROW + 13 }, // Iblis 2: Telah dipindahkan ke lorong terbuka
      { col: OFFSET_COL + 8, row: OFFSET_ROW + 11 }, // Iblis 3: Persimpangan bawah
      { col: OFFSET_COL + 4, row: OFFSET_ROW + 11 }, // Iblis 4: Lorong sayap kiri
      { col: OFFSET_COL + 4, row: OFFSET_ROW + 9  }, // Iblis 5: Jalur tengah naik
      { col: OFFSET_COL + 6, row: OFFSET_ROW + 7  }, // Iblis 6: Tengah labirin
      { col: OFFSET_COL + 6, row: OFFSET_ROW + 5  }, // Iblis 7: Jalur penghubung atas
      { col: OFFSET_COL + 10, row: OFFSET_ROW + 5 }, // Iblis 8: Jalur timur atas
      { col: OFFSET_COL + 6, row: OFFSET_ROW + 3  }, // Iblis 9: Menuju gerbang istana
      { col: OFFSET_COL + 6, row: OFFSET_ROW + 1  }  // Iblis 10: Tepat sebelum pintu gapura emas
    ];

    let mazeDemons = [];
    let mazeScore = 0;
    let mazePlayer = {
      x: (OFFSET_COL + 6.5) * TILE_SIZE,
      y: (OFFSET_ROW + 15.5) * TILE_SIZE,
      vx: 0,
      vy: 0,
      dir: 'up',
      animFrame: 0,
      state: 'idle',
      effectTimer: 0,
      radius: 13,
      hasFinished: false
    };

    function initMazeDemons() {
      const sessionQuestions = generateRandomSessionQuestions(rawBankGame2, 10);
      mazeDemons = demonPositions.map((spot, idx) => ({
        index: idx,
        col: spot.col,
        row: spot.row,
        x: (spot.col + 0.5) * TILE_SIZE,
        y: (spot.row + 0.5) * TILE_SIZE,
        status: 'active',
        question: sessionQuestions[idx],
        pulse: Math.random() * Math.PI
      }));
    }

    function startMazeGame() {
      if (!student) { showView('viewRegister'); return; }
      resetGameStates();
      showView('viewMazeGame');

      document.getElementById('mazePlayerBadge').innerText = `Siswa: ${student.name} (${student.gender === 'Laki-laki' ? '👦 Berpeci' : '👧 Berhijab'})`;

      mazeScore = 0;
      mazePlayer.x = (OFFSET_COL + 6.5) * TILE_SIZE;
      mazePlayer.y = (OFFSET_ROW + 15.5) * TILE_SIZE;
      mazePlayer.vx = 0;
      mazePlayer.vy = 0;
      mazePlayer.dir = 'up';
      mazePlayer.state = 'idle';
      mazePlayer.effectTimer = 0;
      mazePlayer.hasFinished = false;
      mazeWaitingQuiz = false;
      activeDemon = null;
      cameraShake = 0;
      fireworks = [];

      initMazeDemons();
      updateMazeUI();
      sfxStart();

      mazeGameLoop();
    }

    function updateMazeUI() {
      document.getElementById('mazeScoreText').innerText = mazeScore;
      const count = mazeDemons.filter(d => d.status !== 'active').length;
      document.getElementById('mazeDemonCounter').innerText = `${count}/10`;
    }

    function exitMazeGame() {
      resetGameStates();
      showView('viewMenu');
    }

    const btnMUp = document.getElementById('btnMazeUp');
    const btnMDown = document.getElementById('btnMazeDown');
    const btnMLeft = document.getElementById('btnMazeLeft');
    const btnMRight = document.getElementById('btnMazeRight');

    function bindBtn(btn, vx, vy, dir) {
      btn.onmousedown = () => {
        if (mazeWaitingQuiz || mazePlayer.state === 'hurt' || exitConfirmOpen) return;
        mazePlayer.vx = vx; mazePlayer.vy = vy; mazePlayer.dir = dir;
      };
      btn.onmouseup = () => {
        if (mazePlayer.vx === vx) mazePlayer.vx = 0;
        if (mazePlayer.vy === vy) mazePlayer.vy = 0;
      };
      btn.ontouchstart = (e) => {
        e.preventDefault();
        if (mazeWaitingQuiz || mazePlayer.state === 'hurt' || exitConfirmOpen) return;
        mazePlayer.vx = vx; mazePlayer.vy = vy; mazePlayer.dir = dir;
      };
      btn.ontouchend = (e) => {
        e.preventDefault();
        if (mazePlayer.vx === vx) mazePlayer.vx = 0;
        if (mazePlayer.vy === vy) mazePlayer.vy = 0;
      };
    }

    bindBtn(btnMUp, 0, -3.2, 'up');
    bindBtn(btnMDown, 0, 3.2, 'down');
    bindBtn(btnMLeft, -3.2, 0, 'left');
    bindBtn(btnMRight, 3.2, 0, 'right');

    window.addEventListener('keydown', (e) => {
      if (document.getElementById('viewMazeGame').classList.contains('hidden')) return;
      if (mazeWaitingQuiz || mazePlayer.state === 'hurt' || exitConfirmOpen) return;

      if (e.key === 'ArrowUp' || e.key === 'w' || e.key === 'W') {
        mazePlayer.vy = -3.2; mazePlayer.vx = 0; mazePlayer.dir = 'up';
      } else if (e.key === 'ArrowDown' || e.key === 's' || e.key === 'S') {
        mazePlayer.vy = 3.2; mazePlayer.vx = 0; mazePlayer.dir = 'down';
      } else if (e.key === 'ArrowLeft' || e.key === 'a' || e.key === 'A') {
        mazePlayer.vx = -3.2; mazePlayer.vy = 0; mazePlayer.dir = 'left';
      } else if (e.key === 'ArrowRight' || e.key === 'd' || e.key === 'D') {
        mazePlayer.vx = 3.2; mazePlayer.vy = 0; mazePlayer.dir = 'right';
      }
    });

    window.addEventListener('keyup', (e) => {
      if (document.getElementById('viewMazeGame').classList.contains('hidden')) return;
      if (['ArrowUp', 'w', 'W', 'ArrowDown', 's', 'S'].includes(e.key)) mazePlayer.vy = 0;
      if (['ArrowLeft', 'a', 'A', 'ArrowRight', 'd', 'D'].includes(e.key)) mazePlayer.vx = 0;
    });

    function mazeGameLoop() {
      updateMazePhysics();
      render3DBroadcastMaze();
      mazeGameLoopId = requestAnimationFrame(mazeGameLoop);
    }

    function isMazeWall(col, row) {
      if (col < 0 || col >= MAZE_WORLD_COLS || row < 0 || row >= MAZE_WORLD_ROWS) return true;
      const tile = mazeWorld[row][col];
      return tile === 1 || tile === 2;
    }

    function checkCollision(nx, ny) {
      const r = mazePlayer.radius - 2;
      const points = [
        { x: nx - r, y: ny - r },
        { x: nx + r, y: ny - r },
        { x: nx - r, y: ny + r },
        { x: nx + r, y: ny + r }
      ];

      for (let p of points) {
        const col = Math.floor(p.x / TILE_SIZE);
        const row = Math.floor(p.y / TILE_SIZE);
        if (isMazeWall(col, row)) return true;
      }
      return false;
    }

    function updateMazePhysics() {
      mazePlayer.animFrame++;

      if (cameraShake > 0) cameraShake--;

      if (mazePlayer.effectTimer > 0) {
        mazePlayer.effectTimer--;
        if (mazePlayer.effectTimer === 0) {
          mazePlayer.state = 'idle';
        }
      }

      if (mazePlayer.hasFinished && mazePlayer.animFrame % 40 === 0) {
        const exitX = (OFFSET_COL + 6.5) * TILE_SIZE;
        spawnFirework(exitX - 120 + Math.random() * 240, 2 * TILE_SIZE + Math.random() * 80);
      }

      if (mazeWaitingQuiz || mazePlayer.state === 'hurt') return;

      if (mazePlayer.vx !== 0 || mazePlayer.vy !== 0) {
        const nextX = mazePlayer.x + mazePlayer.vx;
        const nextY = mazePlayer.y + mazePlayer.vy;

        if (!checkCollision(nextX, mazePlayer.y)) {
          mazePlayer.x = nextX;
        }
        if (!checkCollision(mazePlayer.x, nextY)) {
          mazePlayer.y = nextY;
        }
        mazePlayer.state = 'move';
      } else {
        if (mazePlayer.state !== 'attack' && mazePlayer.state !== 'hurt') {
          mazePlayer.state = 'idle';
        }
      }

      const currentGridRow = Math.floor(mazePlayer.y / TILE_SIZE);
      if (currentGridRow < OFFSET_ROW && !mazePlayer.hasFinished) {
        mazePlayer.hasFinished = true;
        const fxX = (OFFSET_COL + 6.5) * TILE_SIZE;
        spawnFirework(fxX - 60, 3 * TILE_SIZE);
        spawnFirework(fxX + 60, 3 * TILE_SIZE);
      }

      if (currentGridRow <= 0 && !exitConfirmOpen) {
        mazePlayer.vx = 0;
        mazePlayer.vy = 0;
        showExitConfirmation('game2');
        return;
      }

      // Deteksi jarak dengan iblis (jarak diperlebar menjadi 35px agar trigger mulus)
      for (let demon of mazeDemons) {
        if (demon.status === 'active') {
          const dist = Math.hypot(mazePlayer.x - demon.x, mazePlayer.y - demon.y);
          if (dist < 35) {
            mazePlayer.vx = 0;
            mazePlayer.vy = 0;
            triggerDemonQuiz(demon);
            break;
          }
        }
      }
    }

    function triggerDemonQuiz(demon) {
      mazeWaitingQuiz = true;
      activeDemon = demon;
      const q = demon.question;

      document.getElementById('demonTitle').innerText = `Bisikan Iblis Ke-${demon.index + 1} dari 10`;
      document.getElementById('mazeQuestionText').innerText = `${demon.index + 1}. ${q.q}`;

      const optContainer = document.getElementById('mazeOptionsContainer');
      optContainer.innerHTML = '';

      q.options.forEach((opt, idx) => {
        const btn = document.createElement('button');
        btn.type = "button";
        btn.className = "w-full text-left p-3.5 rounded-2xl bg-slate-800/90 hover:bg-rose-700/80 border border-rose-500/50 hover:border-amber-400 font-medium transition active:scale-95 text-xs md:text-sm flex items-start gap-2.5 shadow cursor-pointer";
        btn.innerHTML = `<span class="inline-flex items-center justify-center min-w-[22px] h-[22px] bg-rose-950 text-amber-300 font-bold rounded-full text-xs border border-rose-400 shrink-0">${String.fromCharCode(65+idx)}</span> <span>${opt}</span>`;
        btn.onclick = () => answerDemonQuiz(idx, demon);
        optContainer.appendChild(btn);
      });

      document.getElementById('mazeQuizOverlay').classList.remove('hidden');
    }

    function answerDemonQuiz(chosenIdx, demon) {
      document.getElementById('mazeQuizOverlay').classList.add('hidden');
      mazeWaitingQuiz = false;

      const isCorrect = (chosenIdx === demon.question.correct);

      if (isCorrect) {
        mazeScore += 10;
        demon.status = 'defeated';
        mazePlayer.state = 'attack';
        mazePlayer.effectTimer = 50;
        sfxHolyDefeat();
      } else {
        demon.status = 'hurt_player';
        mazePlayer.state = 'hurt';
        mazePlayer.effectTimer = 50;
        cameraShake = 15;
        sfxDemonHurt();
      }
      updateMazeUI();
    }

    function render3DBroadcastMaze() {
      const W = mazeCanvas.width;
      const H = mazeCanvas.height;

      const camX = mazePlayer.x - W * 0.5;
      const camY = mazePlayer.y - H * 0.52;

      mCtx.clearRect(0, 0, W, H);

      mCtx.save();
      if (cameraShake > 0) {
        const sx = (Math.random() - 0.5) * cameraShake * 1.5;
        const sy = (Math.random() - 0.5) * cameraShake * 1.5;
        mCtx.translate(sx, sy);
      }

      mCtx.translate(-camX, -camY);

      mCtx.fillStyle = '#064e3b';
      mCtx.fillRect(0, 0, MAZE_WORLD_COLS * TILE_SIZE, MAZE_WORLD_ROWS * TILE_SIZE);

      for (let r = 0; r < MAZE_WORLD_ROWS; r++) {
        for (let c = 0; c < MAZE_WORLD_COLS; c++) {
          const x = c * TILE_SIZE;
          const y = r * TILE_SIZE;
          const tile = mazeWorld[r][c];

          if (tile === 0) {
            if (r < OFFSET_ROW) {
              mCtx.fillStyle = (r + c) % 2 === 0 ? '#f8fafc' : '#f1f5f9';
              mCtx.fillRect(x, y, TILE_SIZE, TILE_SIZE);
              mCtx.strokeStyle = '#cbd5e1';
              mCtx.lineWidth = 1;
              mCtx.strokeRect(x, y, TILE_SIZE, TILE_SIZE);
            } else {
              mCtx.fillStyle = '#fef3c7';
              mCtx.fillRect(x, y, TILE_SIZE, TILE_SIZE);
              mCtx.strokeStyle = '#fde68a';
              mCtx.lineWidth = 1.5;
              mCtx.strokeRect(x + 2, y + 2, TILE_SIZE - 4, TILE_SIZE - 4);
            }
          } else if (tile === 2) {
            mCtx.fillStyle = '#022c22';
            mCtx.fillRect(x, y, TILE_SIZE, TILE_SIZE);
            draw3DTree(x + TILE_SIZE / 2, y + TILE_SIZE / 2);
          }
        }
      }

      const istanaFountainX = (OFFSET_COL + 6.5) * TILE_SIZE;
      const istanaFountainY = 3.5 * TILE_SIZE;
      mCtx.fillStyle = 'rgba(0,0,0,0.3)';
      mCtx.beginPath();
      mCtx.ellipse(istanaFountainX, istanaFountainY + 10, 48, 18, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#e2e8f0';
      mCtx.beginPath();
      mCtx.ellipse(istanaFountainX, istanaFountainY, 44, 15, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#38bdf8';
      mCtx.beginPath();
      mCtx.ellipse(istanaFountainX, istanaFountainY - 2, 38, 12, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.strokeStyle = '#ffffff';
      mCtx.lineWidth = 2.5;
      mCtx.beginPath();
      mCtx.moveTo(istanaFountainX, istanaFountainY - 2);
      mCtx.lineTo(istanaFountainX, istanaFountainY - 30);
      mCtx.stroke();

      mCtx.fillStyle = '#0369a1';
      mCtx.font = 'bold 11px sans-serif';
      mCtx.textAlign = 'center';
      mCtx.fillText("⛲ Air Mancur Istana", istanaFountainX, istanaFountainY - 35);

      const gateX = (OFFSET_COL + 6.5) * TILE_SIZE;
      mCtx.fillStyle = '#065f46';
      mCtx.fillRect(gateX - 55, 0, 110, 32);
      mCtx.fillStyle = '#fbbf24';
      mCtx.fillRect(gateX - 48, 4, 96, 24);
      mCtx.fillStyle = '#064e3b';
      mCtx.font = '900 11px sans-serif';
      mCtx.fillText("🚪 PINTU KELUAR MENU", gateX, 20);

      const gapuraY = OFFSET_ROW * TILE_SIZE;
      mCtx.fillStyle = '#f59e0b';
      mCtx.beginPath();
      mCtx.arc(gateX, gapuraY, 32, Math.PI, 0);
      mCtx.fill();
      mCtx.fillStyle = '#fbbf24';
      mCtx.beginPath();
      mCtx.arc(gateX, gapuraY - 32, 10, 0, Math.PI * 2);
      mCtx.fill();

      const startGateY = (OFFSET_ROW + 16) * TILE_SIZE;
      mCtx.fillStyle = '#78350f';
      mCtx.fillRect(gateX - 40, startGateY, 80, 14);
      mCtx.fillStyle = '#ffffff';
      mCtx.font = 'bold 10px sans-serif';
      mCtx.fillText("🚪 PINTU MASUK START", gateX, startGateY + 11);

      const WALL_HEIGHT = 16;
      for (let r = 0; r < MAZE_WORLD_ROWS; r++) {
        for (let c = 0; c < MAZE_WORLD_COLS; c++) {
          if (mazeWorld[r][c] === 1) {
            const x = c * TILE_SIZE;
            const y = r * TILE_SIZE;

            mCtx.fillStyle = '#064e3b';
            mCtx.fillRect(x, y + TILE_SIZE - WALL_HEIGHT, TILE_SIZE, WALL_HEIGHT);
            mCtx.fillStyle = 'rgba(0,0,0,0.25)';
            mCtx.fillRect(x, y + TILE_SIZE, TILE_SIZE, 6);

            mCtx.fillStyle = '#059669';
            mCtx.fillRect(x, y - WALL_HEIGHT, TILE_SIZE, TILE_SIZE);
            mCtx.fillStyle = '#10b981';
            mCtx.fillRect(x + 3, y - WALL_HEIGHT + 3, TILE_SIZE - 6, TILE_SIZE - 6);

            if ((r + c) % 3 === 0) {
              mCtx.fillStyle = '#f43f5e';
              mCtx.beginPath();
              mCtx.arc(x + 14, y - WALL_HEIGHT + 14, 3.5, 0, Math.PI * 2);
              mCtx.fill();
            } else if ((r * c) % 4 === 0) {
              mCtx.fillStyle = '#facc15';
              mCtx.beginPath();
              mCtx.arc(x + 32, y - WALL_HEIGHT + 30, 3, 0, Math.PI * 2);
              mCtx.fill();
            }
          }
        }
      }

      mazeDemons.forEach(demon => {
        draw3DMazeDemon(demon);
      });

      updateAndRenderFireworks(mCtx);

      draw3DMazePlayer(mazePlayer.x, mazePlayer.y);

      mCtx.restore();

      if (mazePlayer.hasFinished) {
        mCtx.save();
        mCtx.fillStyle = 'rgba(15, 23, 42, 0.9)';
        mCtx.strokeStyle = '#10b981';
        mCtx.lineWidth = 3;
        const bW = Math.min(520, W - 40);
        const bX = (W - bW) / 2;
        drawRoundedRect(mCtx, bX, 15, bW, 82, 16);
        mCtx.fill();
        mCtx.stroke();

        mCtx.textAlign = 'center';
        mCtx.font = '900 14px sans-serif';
        mCtx.fillStyle = '#fde047';
        mCtx.fillText(`🌟 ALHAMDULILLAH! ${student.name.toUpperCase()} LOLOS! 🌟`, W / 2, 38);

        mCtx.font = 'bold 12px sans-serif';
        mCtx.fillStyle = '#ffffff';
        mCtx.fillText(`Skor Kebaikan: ${mazeScore} / 100  •  Silakan kelilingi istana lalu ke PINTU KELUAR ⬆️`, W / 2, 58);

        mCtx.font = '500 11px sans-serif';
        mCtx.fillStyle = '#38bdf8';
        mCtx.fillText("Karakter leluasa berjalan-jalan di pelataran istana yang luas!", W / 2, 78);
        mCtx.restore();
      }
    }

    function draw3DTree(x, y) {
      mCtx.save();
      mCtx.fillStyle = 'rgba(0,0,0,0.35)';
      mCtx.beginPath();
      mCtx.ellipse(x, y + 10, 18, 9, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#78350f';
      mCtx.fillRect(x - 4, y - 6, 8, 16);

      mCtx.fillStyle = '#047857';
      mCtx.beginPath();
      mCtx.arc(x, y - 10, 18, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#059669';
      mCtx.beginPath();
      mCtx.arc(x - 3, y - 14, 14, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#10b981';
      mCtx.beginPath();
      mCtx.arc(x - 5, y - 18, 9, 0, Math.PI * 2);
      mCtx.fill();
      mCtx.restore();
    }

    function draw3DMazeDemon(demon) {
      if (demon.status === 'defeated') {
        mCtx.save();
        mCtx.fillStyle = 'rgba(250, 204, 21, 0.4)';
        mCtx.beginPath();
        mCtx.ellipse(demon.x, demon.y, 18, 9, 0, 0, Math.PI * 2);
        mCtx.fill();
        mCtx.font = '18px sans-serif';
        mCtx.textAlign = 'center';
        mCtx.fillText("✨", demon.x, demon.y - 12);
        mCtx.restore();
        return;
      }

      if (demon.status === 'hurt_player') {
        mCtx.save();
        mCtx.fillStyle = 'rgba(76, 5, 25, 0.4)';
        mCtx.beginPath();
        mCtx.ellipse(demon.x, demon.y, 16, 8, 0, 0, Math.PI * 2);
        mCtx.fill();
        mCtx.font = '16px sans-serif';
        mCtx.textAlign = 'center';
        mCtx.fillText("💨", demon.x, demon.y - 10);
        mCtx.restore();
        return;
      }

      mCtx.save();
      demon.pulse += 0.08;
      const floatY = Math.sin(demon.pulse) * 4;
      const scalePulse = 1 + Math.sin(demon.pulse * 1.5) * 0.08;

      mCtx.translate(demon.x, demon.y + floatY);

      mCtx.fillStyle = 'rgba(0, 0, 0, 0.35)';
      mCtx.beginPath();
      mCtx.ellipse(0, 16 - floatY, 18, 8, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.scale(scalePulse, scalePulse);

      const fireGrad = mCtx.createRadialGradient(0, 0, 4, 0, 0, 24);
      fireGrad.addColorStop(0, 'rgba(225, 29, 72, 0.85)');
      fireGrad.addColorStop(0.6, 'rgba(159, 18, 57, 0.4)');
      fireGrad.addColorStop(1, 'rgba(0, 0, 0, 0)');
      mCtx.fillStyle = fireGrad;
      mCtx.beginPath();
      mCtx.arc(0, 0, 24, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#4c0519';
      mCtx.beginPath();
      mCtx.arc(0, 0, 14, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#ef4444';
      mCtx.beginPath();
      mCtx.moveTo(-8, -8);
      mCtx.lineTo(-15, -24);
      mCtx.lineTo(-3, -12);
      mCtx.fill();

      mCtx.beginPath();
      mCtx.moveTo(8, -8);
      mCtx.lineTo(15, -24);
      mCtx.lineTo(3, -12);
      mCtx.fill();

      mCtx.fillStyle = '#facc15';
      mCtx.beginPath();
      mCtx.arc(-5, -2, 3, 0, Math.PI * 2);
      mCtx.arc(5, -2, 3, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#dc2626';
      mCtx.beginPath();
      mCtx.arc(-5, -2, 1.5, 0, Math.PI * 2);
      mCtx.arc(5, -2, 1.5, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#ffffff';
      mCtx.font = 'bold 10px sans-serif';
      mCtx.textAlign = 'center';
      mCtx.fillText(`${demon.index + 1}`, 0, 16);

      mCtx.restore();
    }

    function draw3DMazePlayer(x, y) {
      mCtx.save();
      mCtx.translate(x, y);

      const isMale = (student && student.gender === 'Laki-laki');
      const swing = (mazePlayer.state === 'move') ? Math.sin(mazePlayer.animFrame * 0.4) * 8 : 0;

      if (mazePlayer.state === 'attack') {
        const beamGrad = mCtx.createLinearGradient(0, -120, 0, 10);
        beamGrad.addColorStop(0, 'rgba(56, 189, 248, 0.8)');
        beamGrad.addColorStop(0.5, 'rgba(250, 204, 21, 0.9)');
        beamGrad.addColorStop(1, 'rgba(250, 204, 21, 0)');
        mCtx.fillStyle = beamGrad;
        mCtx.fillRect(-20, -120, 40, 130);

        mCtx.font = '900 13px sans-serif';
        mCtx.fillStyle = '#f59e0b';
        mCtx.textAlign = 'center';
        mCtx.fillText("⚡ALLAHU AKBAR!⚡", 0, -32);
      } else if (mazePlayer.state === 'hurt') {
        mCtx.fillStyle = 'rgba(225, 29, 72, 0.45)';
        mCtx.beginPath();
        mCtx.arc(0, 0, 28, 0, Math.PI * 2);
        mCtx.fill();

        mCtx.strokeStyle = '#ef4444';
        mCtx.lineWidth = 3;
        mCtx.beginPath();
        mCtx.moveTo(-18, -18); mCtx.lineTo(18, 18);
        mCtx.moveTo(18, -18); mCtx.lineTo(-18, 18);
        mCtx.stroke();

        mCtx.font = 'bold 12px sans-serif';
        mCtx.fillStyle = '#f43f5e';
        mCtx.textAlign = 'center';
        mCtx.fillText("Aduh!", 0, -26);
      }

      mCtx.fillStyle = 'rgba(0,0,0,0.35)';
      mCtx.beginPath();
      mCtx.ellipse(0, 12, 14, 7, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#059669';
      mCtx.beginPath();
      mCtx.ellipse(0, 2, 12, 14, 0, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#1e293b';
      mCtx.fillRect(-7 - swing, 10, 5, 6);
      mCtx.fillRect(2 + swing, 10, 5, 6);

      mCtx.fillStyle = '#fcd34d';
      mCtx.beginPath();
      mCtx.arc(0, -10, 9, 0, Math.PI * 2);
      mCtx.fill();

      mCtx.fillStyle = '#0f172a';
      let ex = 0; let ey = -10;
      if (mazePlayer.dir === 'left') ex = -3;
      if (mazePlayer.dir === 'right') ex = 3;
      if (mazePlayer.dir === 'up') ey = -13;
      if (mazePlayer.dir === 'down') ey = -8;

      mCtx.beginPath();
      mCtx.arc(ex - 2.5, ey, 1.3, 0, Math.PI * 2);
      mCtx.arc(ex + 2.5, ey, 1.3, 0, Math.PI * 2);
      mCtx.fill();

      if (isMale) {
        mCtx.fillStyle = '#0f172a';
        mCtx.fillRect(-8, -20, 16, 8);
        mCtx.fillStyle = '#334155';
        mCtx.fillRect(-8, -20, 16, 2);
      } else {
        mCtx.fillStyle = '#ec4899';
        mCtx.beginPath();
        mCtx.arc(0, -11, 11, Math.PI * 0.75, Math.PI * 2.25);
        mCtx.fill();
        mCtx.beginPath();
        mCtx.moveTo(-10, -8);
        mCtx.lineTo(-12, 6);
        mCtx.lineTo(12, 6);
        mCtx.lineTo(10, -8);
        mCtx.closePath();
        mCtx.fill();
      }

      if (mazePlayer.hasFinished) {
        mCtx.fillStyle = '#fbbf24';
        mCtx.beginPath();
        mCtx.arc(0, -32, 9, 0, Math.PI);
        mCtx.fill();
        mCtx.fillRect(-3, -24, 6, 6);
        mCtx.fillRect(-6, -18, 12, 3);
      }

      mCtx.restore();
    }
  </script>
</body>
</html>
