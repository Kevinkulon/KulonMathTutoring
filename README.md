<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>KULON – Math Tutoring</title>
  <meta name="description" content="Bimbingan belajar matematika untuk TK, SMP, SMA, dan Kuliah. Online & offline, tutor berpengalaman, materi lengkap, dan jadwal fleksibel." />
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ccircle cx='50' cy='50' r='45' fill='%230F172A'/%3E%3Ctext x='50' y='58' text-anchor='middle' font-size='48' font-family='Arial' fill='%23FACC15'%3EK%3C/text%3E%3C/svg%3E" />
  <style>
    /* ====== Design Tokens ====== */
    :root{
      --bg: #0b1220;          /* navy-darker */
      --bg-soft:#0f172a;      /* slate-900 */
      --card:#111827;         /* gray-900 */
      --text:#e5e7eb;         /* gray-200 */
      --muted:#9ca3af;        /* gray-400 */
      --brand:#2563eb;        /* blue-600 */
      --brand-2:#f59e0b;      /* amber-500 */
      --accent:#22c55e;       /* green-500 */
      --danger:#ef4444;       /* red-500 */
      --ring: rgba(37, 99, 235, .45);
      --radius: 16px;
      --shadow: 0 10px 30px rgba(0,0,0,.35);
      --container: 1200px;
    }

    /* ====== Base ====== */
    *{ box-sizing: border-box }
    html,body{ height:100% }
    body{
      margin:0; font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, Arial, "Apple Color Emoji","Segoe UI Emoji";
      background: radial-gradient(1200px 600px at 80% -10%, rgba(59,130,246,.12), transparent 60%),
                  radial-gradient(1000px 500px at -10% 10%, rgba(245,158,11,.08), transparent 55%),
                  var(--bg);
      color:var(--text);
      line-height: 1.6;
    }
    img{ max-width:100%; display:block }
    a{ color:inherit; text-decoration:none }
    .container{ width: min(100% - 2rem, var(--container)); margin-inline:auto }
    .btn{
      display:inline-block; padding: .85rem 1.2rem; border-radius: 999px; font-weight:600; letter-spacing:.2px;
      background: linear-gradient(135deg, var(--brand), #3b82f6);
      color:white; box-shadow: var(--shadow); border: 0; cursor: pointer
    }
    .btn--ghost{ background: transparent; border:1px solid #334155 }
    .btn:focus{ outline: 3px solid var(--ring) }
    .badge{ display:inline-flex; gap:.5rem; align-items:center; color:#0b1220; background: linear-gradient(135deg, #fde68a, #facc15); padding:.35rem .7rem; border-radius:999px; font-weight:700; font-size:.8rem }

    /* ====== Header / Nav ====== */
    header{ position:sticky; top:0; z-index:50; backdrop-filter:saturate(180%) blur(8px); background: color-mix(in oklab, var(--bg-soft) 88%, transparent); border-bottom:1px solid #1f2937 }
    .nav{ display:flex; align-items:center; justify-content:space-between; padding:.8rem 0 }
    .logo{ display:flex; align-items:center; gap:.7rem; font-weight:800 }
    .logo .mark{ width:34px; height:34px; display:grid; place-items:center; border-radius:10px; background: conic-gradient(from 200deg at 50% 50%, var(--brand), var(--brand-2)); color:#0b1220; font-weight:900 }
    .menu{ display:flex; gap:1.2rem; align-items:center }
    .menu a{ color:var(--muted); font-weight:600 }
    .menu a:hover{ color:#fff }

    /* ====== Hero ====== */
    .hero{ padding: 4rem 0 2.5rem; display:grid; grid-template-columns: 1.1fr .9fr; gap:2rem; align-items:center }
    .hero h1{ font-size: clamp(2rem, 1.6rem + 2vw, 3.2rem); line-height:1.15; margin:.5rem 0 1rem; font-weight:900 }
    .hero p{ color: var(--muted); max-width:55ch }
    .hero .cta{ display:flex; gap:.8rem; margin-top:1.2rem; flex-wrap:wrap }
    .hero-ill{
      aspect-ratio: 4 / 3; border-radius: var(--radius); background: linear-gradient(135deg, #0b1220, #0f172a);
      padding:1rem; border:1px solid #1f2937; box-shadow: var(--shadow); position:relative; overflow:hidden
    }
    .hero-ill canvas{ width:100%; height:100%; background: transparent }
    .hero-ill .chip{ position:absolute; right:1rem; top:1rem }

    /* ====== Sections ====== */
    section{ padding: 3rem 0 }
    .section-title{ font-size: clamp(1.4rem, 1rem + 1vw, 2rem); margin:0 0 1.2rem; font-weight:800 }
    .muted{ color: var(--muted) }

    /* ====== Programs Grid ====== */
    .grid{ display:grid; gap:1rem }
    .grid.cols-3{ grid-template-columns: repeat(3, minmax(0, 1fr)) }
    .grid.cols-4{ grid-template-columns: repeat(4, minmax(0, 1fr)) }
    .card{
      background: linear-gradient(180deg, color-mix(in srgb, var(--card) 90%, transparent), var(--card));
      border:1px solid #1f2937; border-radius: var(--radius); padding:1.1rem; box-shadow: var(--shadow)
    }
    .card h3{ margin:.2rem 0 .5rem }
    .tag{ font-size:.75rem; color:#0b1220; background:#bae6fd; display:inline-block; padding:.2rem .5rem; border-radius:999px; font-weight:700 }

    /* ====== Pricing ====== */
    .pricing{ display:grid; grid-template-columns: repeat(3, minmax(0,1fr)); gap:1rem }
    .price{
      background: linear-gradient(135deg, #0f172a, #0b1220); border:1px solid #1f2937; padding:1.2rem; border-radius:var(--radius); box-shadow: var(--shadow)
    }
    .price h4{ margin:.2rem 0 }
    .price .amount{ font-size:2rem; font-weight:900 }
    .list{ padding-left:1rem }

    /* ====== FAQ ====== */
    details{ background:#0f172a; border:1px solid #1f2937; border-radius:12px; padding:.8rem 1rem }
    details+details{ margin-top:.6rem }
    summary{ cursor:pointer; font-weight:700 }

    /* ====== Contact ====== */
    form{ display:grid; gap:.8rem; max-width:580px }
    input, textarea, select{
      background:#0b1220; border:1px solid #1f2937; color:var(--text); padding:.9rem 1rem; border-radius:12px; font: inherit
    }
    input:focus, textarea:focus, select:focus{ outline:3px solid var(--ring); border-color: transparent }

    .contacts{ display:grid; grid-template-columns: repeat(2, minmax(0,1fr)); gap:.8rem; margin:1rem 0 1.2rem }
    .contact{ display:flex; align-items:center; gap:.8rem; background:#0f172a; border:1px solid #1f2937; border-radius:12px; padding:.9rem 1rem }
    .contact .icon{ width:22px; height:22px; display:grid; place-items:center }
    .contact a{ font-weight:700; word-break:break-word }

    /* ====== Footer ====== */
    footer{ border-top:1px solid #1f2937; padding:2rem 0; color:var(--muted) }

    /* ====== Responsive ====== */
    @media (max-width: 980px){
      .hero{ grid-template-columns: 1fr; }
      .grid.cols-3{ grid-template-columns: 1fr 1fr }
      .grid.cols-4{ grid-template-columns: 1fr 1fr }
      .pricing{ grid-template-columns: 1fr }
    }
    @media (max-width: 640px){
      .grid.cols-3, .grid.cols-4{ grid-template-columns: 1fr }
      .contacts{ grid-template-columns:1fr }
    }
  </style>
</head>
<body>
  <!-- ===== Header & Navigation ===== -->
  <header>
    <div class="container nav">
      <a href="#" class="logo" aria-label="KULON Home">
        <span class="mark">K</span>
        <span>KULON Math Tutoring</span>
      </a>
      <nav class="menu" aria-label="Primary">
        <a href="#program">Program</a>
        <a href="#harga">Harga</a>
        <a href="#testimoni">Testimoni</a>
        <a href="#faq">FAQ</a>
        <a href="#kontak" class="btn btn--ghost">Kontak</a>
      </nav>
    </div>
  </header>

  <!-- ===== Hero ===== -->
  <section class="hero container" id="home">
    <div>
      <span class="badge chip">✨ Buka pendaftaran gelombang baru</span>
      <h1>Bimbel Matematika untuk TK–Kuliah dengan pendekatan <em>fun</em> & terstruktur.</h1>
      <p>KULON membantu siswa memahami konsep, bukan sekadar menghafal rumus. Tersedia kelas privat & kelompok, online maupun tatap muka.</p>
      <div class="cta">
        <a href="#program" class="btn">Lihat Program</a>
        <a href="#kontak" class="btn btn--ghost">Konsultasi Gratis</a>
      </div>
    </div>
    <div class="hero-ill" role="img" aria-label="Ilustrasi guru mengajar matematika di papan tulis">
      <span class="chip badge">aⁿ × aᵐ = a⁽ⁿ⁺ᵐ⁾ • Δy/Δx • π ≈ 3.14</span>
      <canvas id="chalk"></canvas>
    </div>
  </section>

  <!-- ===== Programs ===== -->
  <section id="program">
    <div class="container">
      <h2 class="section-title">Program Belajar</h2>
      <p class="muted">Materi disesuaikan dengan kurikulum & kebutuhan siswa.</p>
      <div class="grid cols-4" style="margin-top:1rem">
        <article class="card">
          <span class="tag">TK/PAUD</span>
          <h3>Logika & Numerasi Dasar</h3>
          <p>Permainan angka, pola bentuk, pengenalan konsep banyak–sedikit, dan aktivitas motorik halus.</p>
        </article>
        <article class="card">
          <span class="tag">SMP</span>
          <h3>Aljabar & Geometri</h3>
          <p>Pertidaksamaan, persamaan garis, bangun ruang, peluang, dan strategi pemecahan masalah.</p>
        </article>
        <article class="card">
          <span class="tag">SMA</span>
          <h3>Persiapan Ujian & SNBT</h3>
          <p>Kalkulus dasar, trigonometri, statistika, dan tryout berkala dengan pembahasan mendalam.</p>
        </article>
        <article class="card">
          <span class="tag">Kuliah</span>
          <h3>Matematika Lanjut</h3>
          <p>Kalkulus lanjut, aljabar linear, statistik, analisis data, serta bimbingan tugas akhir.</p>
        </article>
      </div>
    </div>
  </section>

  <!-- ===== Features ===== -->
  <section>
    <div class="container">
      <h2 class="section-title">Kenapa pilih KULON?</h2>
      <div class="grid cols-3" style="margin-top:1rem">
        <div class="card">
          <h3>Pengajar Berpengalaman</h3>
          <p>Kurikulum terstruktur, pembelajaran adaptif, dan pendekatan <em>concept-first</em>.</p>
        </div>
        <div class="card">
          <h3>Modul Eksklusif</h3>
          <p>Ringkasan materi, bank soal bertingkat, dan latihan berbasis kompetensi.</p>
        </div>
        <div class="card">
          <h3>Jadwal Fleksibel</h3>
          <p>Pilihan kelas privat/kelompok, online/offline, durasi 60–90 menit.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== Pricing ===== -->
  <section id="harga">
    <div class="container">
      <h2 class="section-title">Paket & Harga</h2>
      <div class="pricing" style="margin-top:1rem">
        <div class="price">
          <h4>Starter</h4>
          <p class="muted">Kelompok • 60 menit</p>
          <p class="amount">Rp79.000<span style="font-size: .9rem; color:var(--muted)">/pertemuan</span></p>
          <ul class="list">
            <li>Bank soal & pembahasan</li>
            <li>Report progres bulanan</li>
            <li>Rekaman kelas online</li>
          </ul>
          <a class="btn" href="#kontak">Daftar</a>
        </div>
        <div class="price" style="outline:3px solid color-mix(in srgb, var(--brand), transparent 60%);">
          <h4>Pro (Rekomendasi)</h4>
          <p class="muted">Privat • 75 menit</p>
          <p class="amount">Rp149.000<span style="font-size: .9rem; color:var(--muted)">/pertemuan</span></p>
          <ul class="list">
            <li>Silabus personal</li>
            <li>Evaluasi mingguan</li>
            <li>Prioritas jadwal</li>
          </ul>
          <a class="btn" href="#kontak">Daftar</a>
        </div>
        <div class="price">
          <h4>Intensif SNBT</h4>
          <p class="muted">Kelompok kecil • 90 menit</p>
          <p class="amount">Rp219.000<span style="font-size: .9rem; color:var(--muted)">/pertemuan</span></p>
          <ul class="list">
            <li>Tryout mingguan</li>
            <li>Strategi pengerjaan cepat</li>
            <li>Bedah kisi-kisi</li>
          </ul>
          <a class="btn" href="#kontak">Daftar</a>
        </div>
      </div>
    </div>
  </section>

  <!-- ===== Testimonials ===== -->
  <section id="testimoni">
    <div class="container">
      <h2 class="section-title">Apa kata mereka?</h2>
      <div class="grid cols-3" style="margin-top:1rem">
        <figure class="card">
          <blockquote>"Awalnya benci matematika, sekarang malah jadi nilai tertinggi di kelas!"</blockquote>
          <figcaption class="muted">— Siswa SMA, Manado</figcaption>
        </figure>
        <figure class="card">
          <blockquote>"Tutor sabar dan penjelasannya mudah dimengerti. Rekomendasi banget!"</blockquote>
          <figcaption class="muted">— Mahasiswa Teknik</figcaption>
        </figure>
        <figure class="card">
          <blockquote>"Anak saya (SMP) makin percaya diri. PR jadi cepat selesai."</blockquote>
          <figcaption class="muted">— Orang tua murid</figcaption>
        </figure>
      </div>
    </div>
  </section>

  <!-- ===== FAQ ===== -->
  <section id="faq">
    <div class="container">
      <h2 class="section-title">Pertanyaan yang sering ditanyakan</h2>
      <details>
        <summary>Apakah tersedia kelas trial?</summary>
        <p>Ya, 1x pertemuan trial online 30 menit (gratis) untuk memetakan kebutuhan siswa.</p>
      </details>
      <details>
        <summary>Apakah bisa ganti jadwal?</summary>
        <p>Bisa, maksimal H-1. Jadwal sangat fleksibel mengikuti ketersediaan tutor & siswa.</p>
      </details>
      <details>
        <summary>Metode pembayaran?</summary>
        <p>Transfer bank/e-wallet. Invoicing otomatis dikirim ke email/WhatsApp.</p>
      </details>
    </div>
  </section>

  <!-- ===== Contact ===== -->
  <section id="kontak">
    <div class="container">
      <h2 class="section-title">Hubungi kami</h2>
      <p class="muted">Isi formulir di bawah ini. Kami akan menghubungi Anda dalam 24 jam (hari kerja).</p>

      <div class="contacts" aria-label="Kontak cepat">
        <div class="contact">
          <span class="icon" aria-hidden="true">📱</span>
          <div>
            <div>WhatsApp</div>
            <a href="https://wa.me/6289520710331?text=Halo%20KULON%2C%20saya%20ingin%20konsultasi%20bimbel%20matematika." target="_blank" rel="noopener">0895-2071-0331</a>
          </div>
        </div>
        <div class="contact">
          <span class="icon" aria-hidden="true">📷</span>
          <div>
            <div>Instagram</div>
            <a href="https://instagram.com/kulonmathtutoring" target="_blank" rel="noopener">@kulonmathtutoring</a>
          </div>
        </div>
        <div class="contact">
          <span class="icon" aria-hidden="true">🎵</span>
          <div>
            <div>TikTok</div>
            <a href="https://tiktok.com/@kulonmathtutoring" target="_blank" rel="noopener">@kulonmathtutoring</a>
          </div>
        </div>
        <div class="contact">
          <span class="icon" aria-hidden="true">✉️</span>
          <div>
            <div>Email</div>
            <a href="mailto:kulonmathtutoring@gmail.com">kulonmathtutoring@gmail.com</a>
          </div>
        </div>
      </div>

      <div class="cta" style="margin:.5rem 0 1rem;">
        <a class="btn" href="https://wa.me/6289520710331?text=Halo%20KULON%2C%20saya%20ingin%20konsultasi%20bimbel%20matematika." target="_blank" rel="noopener">Chat WhatsApp sekarang</a>
      </div>

      <form onsubmit="event.preventDefault(); alert('Terima kasih! Kami akan segera menghubungi Anda.');">
        <label>Nama
          <input type="text" name="nama" placeholder="Nama lengkap" required>
        </label>
        <label>Email
          <input type="email" name="email" placeholder="email@contoh.com" required>
        </label>
        <label>Jenjang
          <select name="jenjang" required>
            <option value="">Pilih jenjang</option>
            <option>TK/PAUD</option>
            <option>SMP</option>
            <option>SMA</option>
            <option>Kuliah</option>
          </select>
        </label>
        <label>Pesan
          <textarea name="pesan" rows="4" placeholder="Ceritakan kebutuhan belajar Anda..." required></textarea>
        </label>
        <button class="btn" type="submit">Kirim</button>
      </form>
    </div>
  </section>

  <footer>
    <div class="container" style="display:flex; justify-content:space-between; gap:1rem; flex-wrap:wrap;">
      <small>© <span id="year"></span> KULON Math Tutoring. All rights reserved.</small>
      <small>Made with ❤ in Indonesia.</small>
    </div>
  </footer>

  <script>
    // Tahun dinamis di footer
    document.getElementById('year').textContent = new Date().getFullYear();

    // Coret-coret "kapur" di kanvas hero (hiasan)
    const cvs = document.getElementById('chalk');
    const ctx = cvs.getContext('2d');
    function fit(){ cvs.width = cvs.clientWidth; cvs.height = cvs.clientHeight; draw(); }
    window.addEventListener('resize', fit, { passive: true });
    fit();
    function draw(){
      ctx.clearRect(0,0,cvs.width,cvs.height);
      ctx.strokeStyle = 'rgba(255,255,255,.85)';
      ctx.lineWidth = 2; ctx.setLineDash([4,3]);
      // Garis koordinat
      ctx.beginPath(); ctx.moveTo(20, cvs.height-30); ctx.lineTo(cvs.width-20, 40); ctx.stroke();
      // Beberapa simbol matematika
      ctx.setLineDash([]); ctx.font = '16px system-ui'; ctx.fillStyle = 'rgba(255,255,255,.9)';
      ctx.fillText('y = mx + c', 26, 40);
      ctx.fillText('∫ f(x) dx', cvs.width-140, cvs.height-40);
      ctx.fillText('π ≈ 3.14159', 40, cvs.height-60);
      // Titik-titik data
      for(let i=0;i<14;i++){
        const x = 40 + Math.random()*(cvs.width-80);
        const y = 50 + Math.random()*(cvs.height-100);
        ctx.beginPath(); ctx.arc(x,y,2,0,Math.PI*2); ctx.fill();
      }
    }
  </script>
</body>
</html>
