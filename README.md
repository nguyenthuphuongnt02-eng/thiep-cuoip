<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Thiệp cưới | Văn Quân & Thu Phương</title>

  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=Montserrat:wght@300;400;500&display=swap" rel="stylesheet">

  <style>
    :root{
      --main:#c59d5f;
      --dark:#2b2b2b;
      --light:#faf7f2;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:'Montserrat',sans-serif;
      background:var(--light);
      color:var(--dark);
      scroll-behavior:smooth;
    }
    section{padding:70px 20px; text-align:center}
    h1,h2,h3{font-family:'Playfair Display',serif; margin:0 0 15px}

    /* HERO */
    .hero{
      height:100vh;
      background:url('https://images.unsplash.com/photo-1529634806980-85c3dd6d34ac') center/cover no-repeat;
      color:#fff;
      display:flex;
      align-items:center;
      justify-content:center;
      flex-direction:column;
      position:relative;
    }
    .hero::after{
      content:"";
      position:absolute; inset:0;
      background:rgba(0,0,0,.45);
    }
    .hero *{position:relative}
    .hero h1{font-size:48px}
    .hero p{letter-spacing:2px}

    /* COUNTDOWN */
    .countdown{display:flex; gap:20px; justify-content:center; flex-wrap:wrap}
    .box{background:#fff; padding:15px 20px; border-radius:10px; min-width:90px}
    .box span{display:block; font-size:26px; font-weight:600; color:var(--main)}

    /* SECTIONS */
    .card{
      max-width:700px; margin:0 auto;
      background:#fff; padding:40px 25px;
      border-radius:20px; box-shadow:0 10px 30px rgba(0,0,0,.08)
    }

    /* GALLERY */
    .gallery{display:grid; grid-template-columns:repeat(auto-fit,minmax(180px,1fr)); gap:15px}
    .gallery img{width:100%; border-radius:15px}

    /* RSVP */
    form{max-width:500px; margin:0 auto; display:grid; gap:15px}
    input,textarea,button{
      padding:12px 15px; border-radius:10px; border:1px solid #ddd; font-family:inherit
    }
    button{background:var(--main); color:#fff; border:none; font-weight:500; cursor:pointer}

    footer{padding:30px; background:#111; color:#fff; text-align:center}
  </style>
</head>
<body>

<!-- MUSIC -->
<audio autoplay loop>
  <source src="https://cdn.pixabay.com/audio/2022/08/04/audio_7fbe89e4b6.mp3" type="audio/mpeg">
</audio>

<!-- HERO -->
<section class="hero" id="home">
  <p>WE ARE GETTING MARRIED</p>
  <h1>Phạm Văn Quân & Nguyễn Thu Phương</h1>
  <p>25 • 01 • 2026</p>
</section>

<!-- COUNTDOWN -->
<section>
  <h2>Đếm ngược ngày cưới</h2>
  <div class="countdown" id="countdown"></div>
</section>

<!-- INFO -->
<section>
  <div class="card">
    <h2>Trân trọng kính mời</h2>
    <p>Tới tham dự lễ thành hôn của chúng tôi</p>
    <h3>08:30 – Chủ Nhật, 25/01/2026</h3>
    <p>(Tức ngày 07/12 năm Ất Tỵ)</p>
    <p><b>Tư gia nhà trai</b><br>Thôn Bá Nha – Xã Hà Đông – TP. Hải Phòng</p>
  </div>
</section>

<!-- GALLERY -->
<section>
  <h2>Khoảnh khắc hạnh phúc</h2>
  <div class="gallery">
    <img src="https://images.unsplash.com/photo-1523438885200-e635ba2c371e">
    <img src="https://images.unsplash.com/photo-1519741497674-611481863552">
    <img src="https://images.unsplash.com/photo-1522335789203-aabd1fc54bc9">
  </div>
</section>

<!-- MAP -->
<section>
  <h2>Chỉ đường</h2>
  <p>Thôn Bá Nha – Xã Hà Đông – TP. Hải Phòng</p>
  <a href="https://www.google.com/maps/search/Thôn+Bá+Nha+Hà+Đông+Hải+Phòng" target="_blank">Mở Google Maps</a>
</section>

<!-- RSVP -->
<section>
  <h2>Xác nhận tham dự</h2>
  <form>
    <input type="text" placeholder="Tên khách mời" required>
    <input type="number" placeholder="Số người tham dự" required>
    <textarea placeholder="Gửi lời chúc"></textarea>
    <button type="submit">Gửi xác nhận</button>
  </form>
</section>

<footer>
  <p>Phạm Văn Quân ❤️ Nguyễn Thu Phương</p>
</footer>

<script>
  const target = new Date("2026-01-25T08:30:00").getTime();
  const cd = document.getElementById('countdown');
  setInterval(()=>{
    const now = new Date().getTime();
    let d = target - now;
    if(d<0) return;
    const days = Math.floor(d/(1000*60*60*24));
    const hours = Math.floor((d%(1000*60*60*24))/(1000*60*60));
    const mins = Math.floor((d%(1000*60*60))/(1000*60));
    const secs = Math.floor((d%(1000*60))/1000);
    cd.innerHTML = `
      <div class='box'><span>${days}</span>Ngày</div>
      <div class='box'><span>${hours}</span>Giờ</div>
      <div class='box'><span>${mins}</span>Phút</div>
      <div class='box'><span>${secs}</span>Giây</div>`;
  },1000);
</script>

</body>
</html>
