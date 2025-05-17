<head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1" name="viewport"/>
<title>X-TOVA</title>
<link href="https://fonts.googleapis.com/css2?family=Josefin+Slab&amp;display=swap" rel="stylesheet"/>
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet"/>
<style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body, html {
      font-family: 'Josefin Slab', serif;
      background-color: #000;
      color: #fff;
    }
    a {
      text-decoration: none;
      color: inherit;
    }
    .topbar {
      display: flex;
      align-items: center;
      padding: 18px;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1100;
      background: #000;
    }
    .hamburger {
      cursor: pointer;
      width: 30px;
      height: 22px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      margin-right: 15px;
    }
 .hamburger.open span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger.open span:nth-child(2) {
  opacity: 0;
}

.hamburger.open span:nth-child(3) {
  transform: rotate(-45deg) translate(6px, -6px);
}
    .hamburger span {
      display: block;
      height: 4px;
      background: #fff;
      border-radius: 2px;
      transition: 0.4s;
    }
    .logo img { height: 40px; 
     aspect-ratio: 16 / 9;
    }
    .sidebar {
      position: fixed;
      top: 0;
      left: -250px;
      width: 220px;
      height: 100%;
      background-color: #000;
      padding-top: 80px;
      transition: left 0.4s ease;
      z-index: 1000;
    }
    .sidebar.open { left: 0; }
    .sidebar a {
      display: block;
      padding: 15px 20px;
      color: #ccc;
    }
    .sidebar a:hover {
      background: #333;
      color: #fff;
    }
    .content { padding-top: 0px; }
    .page { display: none; }
    .page.active { display: block; }
    .hero-header {
      position: relative;
      width: 100%;
      aspect-ratio: 1 / 1;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: left;
      color: #fff;
    }
    .bg-image {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      object-fit: cover;
      z-index: 1;
    }
    .overlay {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      background: rgba(0, 0, 0, 0);
      z-index: 2;
    }
    .header-content {
      position: relative;
      z-index: 3;
      max-width: 600px;
      padding: 20px;
    }
    .header-content h1 { font-size: 2.5rem; margin-bottom: 1rem; }
    .header-content p { font-size: 1rem; line-height: 1.6; }

     /* ক্লাইমেট পোস্ট */
    .climate-post {
      position: relative;
      width: 90%;
      aspect-ratio: 1.4 / 1;
      overflow: hidden;
      margin: 40px 20px;
      border-radius: 0px;
    }

    .climate-link {
      display: block;
      height: 100%;
      color: white;
      text-decoration: none;
      position: relative;
    }

    .climate-bg {
      width: 100%;
      height: 100%;
      object-fit: cover;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 1;
    }

    .climate-overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(to top, rgba(0, 0, 0, 1), rgba(0, 0, 0, 0));
      z-index: 2;
    }

    .climate-text {
      position: relative;
      z-index: 4;
      padding: 40% 20px;
      max-width: 500px;
    }

    .climate-text h2 { font-size: 2rem; margin-bottom: 10px; }
    .climate-text p { font-size: 1rem; line-height: 1.3;}

   /* ব্যাকড্রপ ওভারলে */
    #overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 900;
    }
  
  .page * {
  animation: slideUp 0.7s ease-out forwards;
}

/* এনিমেশন ডিফাইন করা */
@keyframes slideUp {
  0% {
    opacity: 1;
    transform: translateY(60px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
  
    /* Footer */
    footer {
      background-color: #111;
      color: #ccc;
      padding: 60px 20px 30px;
    }
    .footer-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      max-width: 1200px;
      margin: auto;
    }
    .footer-section {
      flex: 1 1 220px;
      padding: 20px;
    }
    .footer-section h3 {
      color: #fff;
      margin-bottom: 15px;
      font-size: 18px;
      border-bottom: 1px solid #333;
      padding-bottom: 5px;
    }
    .footer-section ul {
      list-style: none;
    }
    .footer-section ul li {
      margin-bottom: 10px;
    }
    .footer-section ul li a:hover {
      color: #fff;
    }
    .footer-logo img {
      height: 60px;
    }
  .center-logo {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
    .social-icons {
      margin-top: 20px;
    }
    .social-icons a {
      margin-right: 15px;
      font-size: 16px;
      color: #ccc;
      transition: 0.3s;
    }
    .social-icons a:hover {
      color: #1da1f2;
    }
    .footer-bottom {
      text-align: center;
      margin-top: 40px;
      font-size: 14px;
      color: #777;
    }
    #overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 900;
    }
  </style>
</head>
<body>
<!-- টপবার -->
<div class="topbar">
<!-- হ্যামবার্গার বাটন -->
<div class="hamburger" id="hamburger">
<span></span><span></span><span></span>
</div>
<!-- লোগো -->
<div class="logo">
<img alt="X-TOVA Logo" src="https://i.ibb.co/fdM82wTP/20250515-121149.jpg"/>
</div>
</div>
<!-- সাইডবার -->
<div class="sidebar" id="sidebar">
<!-- সাইডবারের লিংকসমূহ -->
<a href="https://x-tova.blogspot.com/">Home</a>
<a href="https://x-tova.blogspot.com/p/news-events.html" onclick="showPage('news')">News &amp; Events</a>
<a href="https://x-tova.blogspot.com/p/missions.html">Missions</a>
<a href="https://x-tova.blogspot.com/p/solar-system.html">Solar System</a>
<a href="https://x-tova.blogspot.com/p/earth.html">Earth</a>
<a href="https://x-tova.blogspot.com/p/universe.html">The Universe</a>
<a href="https://x-tova.blogspot.com/p/technology.html">Technology</a>
<a href="https://x-tova.blogspot.com/p/about.html">About X-TOVA</a>
</div>
<!-- ওভারলে ব্যাকড্রপ -->
<div id="overlay"></div>
<!-- মূল কন্টেন্ট এরিয়া -->
<div class="content" id="mainContent">
<!-- হোম পেজ -->
<div class="page active" id="home">
<!-- হিরো ব্যানার -->
<header class="hero-header" style="aspect-ratio: auto; height: 70vh;">
<img class="bg-image" src="https://media-hosting.imagekit.io/7a2e66f9938d438d/1000009881.jpg?Expires=1840348330&amp;Key-Pair-Id=K2ZIVPTIP2VGHC&amp;Signature=kMQX9TyNxcFviLRN1rs2N5-I91xg84CRR-Qlw4~LpEG1fVbRk390soriNq3pryLyZG5WsODtXQdtysRQI7ya0N697J2ccYfcwerWAyxMP3epf9ua94oX8R0vEbryU56C~GHw6w3TJKShmdiOu3AynbDf8ambW-yvrY2orQMrD0A6piIZcsp7GEdmW3XwvUG1qrRa3~yG-rI7CxSvsWbd93xS1~Qg-YKZj2AFmrgA9T5pMrSoyGyhhk1oI2OozmDE8z~TH2t4C5NUIR8dPv1gkaUkyB5TJl5sa71LrAVypSXtaAqhgxJHiA52v2zyVbnU6Vww1lICpzU~pOfadiSIyA__"/>
<div class="overlay"></div>
<div class="header-content">
<h1>X-TOVA</h1>
<p>X-TOVA explores the unknown in air and space, innovates for the benefit of humanity, and inspires the world through discovery.</p>
</div>
</header>
<!-- নিউজ অংশ -->
<h1></h1>
<p></p>
<!--<p>&nbsp;</p><div class="separator" style="clear: both; text-align: center;"><iframe allowfullscreen="" height="274" src="https://www.youtube.com/embed/zT3l1lT-_Wk" width="351" youtube-src-id="zT3l1lT-_Wk"></iframe></div><br /><p></p>-->
   
<!-- পোস্ট ১ -->

<section class="climate-post">

  <a href="#" class="climate-link" onclick="showPage('climate')">

    <img src="https://i.postimg.cc/vTzfK4jL/IMG-20250425-145649.jpg" class="climate-bg" alt="Climate Change">

    <div class="climate-overlay"></div>

    <div class="climate-text">

      <h2>Climate Change</h2>

      <p>NASA is a global leader in studying Earth’s changing climate.</p>

    </div>

  </a>

</section>

<!-- পোস্ট ২ -->

<section class="climate-post">

  <a href="#" class="climate-link" onclick="showPage('pop')">

    <img src="https://i.ibb.co/DPz5sVDS/73f436678910.jpg" class="climate-bg" alt="Earth Climate">

    <div class="climate-overlay"></div>

    <div class="climate-text">

      <h2>Earth Climate is changing!</h2>

      <p>NASA is a global leader in studying Earth’s changing climate.</p>

    </div>

  </a>

</section>






.
<!-- ফুটার -->
  <!--<footer>
<div><img alt="X-TOVA Logo" src="https://i.ibb.co.com/k6y15d01/20250502-113509.jpg" style="height: 50px;"/></div>
<h1>X-TOVA</h1>
<p>Exploration is in our nature. We will never stop exploring the unknown, innovating for the benefit of humanity, and inspiring the world through discovery.</p>
<br/><br/><p> <br/>All Pages</p>
<div class="footer-links">
<div>
<h2><a href="https://x-tova.blogspot.com/" onclick="showPage('home')">Home</a></h2>
<h2><a href="https://x-tova.blogspot.com/p/news-events.html" onclick="showPage('news')">News &amp; Events</a></h2>
<h2><a href="https://x-tova.blogspot.com/p/missions.html" onclick="showPage('missions')">Missions</a></h2>
<h2><a href="https://x-tova.blogspot.com/p/solar-system.html" onclick="showPage('solar-system')">Solar System</a></h2>
</div>
<div>
<h2><a href="https://x-tova.blogspot.com/p/earth.html" onclick="showPage('earth')">Earth</a></h2>
<h2><a href="https://x-tova.blogspot.com/p/universe.html" onclick="showPage('universe')">The Universe</a></h2>
<h2><a href="https://x-tova.blogspot.com/p/technology.html" onclick="showPage('technology')">Technology</a></h2>
<h2><a href="https://x-tova.blogspot.com/p/about.html" onclick="showPage('about')">About</a></h2>
</div>
</div>
<br/><br/><br/>
<p>Join Us <span style="color: red;">➔</span></p>
<!-- সোশ্যাল আইকন 
<div class="social-icons">
<a href="https://facebook.com/@XTOVAofficial" target="_blank"><img alt="Facebook" src="https://i.ibb.co/0Rn3cY0N/8fedea3b4ab9.png"/></a>
<a href="https://instagram.com/XTOVAofficial" target="_blank"><img alt="Instagram" src="https://i.ibb.co/fzDwQZ0F/54a6d7f094cb.png"/></a>
<a href="https://x.com/XTOVAofficial" target="_blank"><img alt="X" src="https://i.ibb.co/1fG6k8Ww/93ada2da4eee.png"/></a>
<a href="https://youtube.com/@XTOVAofficial" target="_blank"><img alt="YouTube" src="https://i.ibb.co/mCrxw2YM/b21e91fe0afb.png"/></a>
</div>
<br/><br/><br/>
<a>2025 | © X-TOVA</a>
</footer>
</div>-->
<!-- জাভাস্ক্রিপ্ট শুরু -->
<script>
  // হ্যামবার্গার ক্লিক করলে সাইডবার খুলবে/বন্ধ হবে
  const hamburger = document.getElementById('hamburger');
  const sidebar = document.getElementById('sidebar');
  const overlay = document.getElementById('overlay');

  hamburger.addEventListener('click', () => {
    sidebar.classList.toggle('open');
    hamburger.classList.toggle('open');
    overlay.style.display = sidebar.classList.contains('open') ? 'block' : 'none';
  });

  overlay.addEventListener('click', () => {
    sidebar.classList.remove('open');
    hamburger.classList.remove('open');
    overlay.style.display = 'none';
  });
</script>
<!-- জাভাস্ক্রিপ্ট শেষ -->
<footer>
<div class="footer-container">
<div class="footer-section footer-logo">
<img alt="X-TOVA Logo" class="center-logo" src="https://i.ibb.co/Cqx8pF5/20250515-190817.jpg"/>
<p> <br/>We will never stop exploring the unknown, innovating for the benefit of humanity, and inspiring the world through discovery.</p>
<div class="social-icons">
<h4>Join Us <span style="color: red;">➔</span><br/><br/></h4>
<a href="https://facebook.com/@XTOVAofficial" target="_blank"><i class="fab fa-facebook-f"></i></a>
<a href="https://instagram.com/XTOVAofficial" target="_blank"><i class="fab fa-instagram"></i></a>
<a href="https://x.com/XTOVAofficial" target="_blank"><i class="fab fa-x-twitter"></i></a>
<a href="https://youtube.com/@XTOVAofficial" target="_blank"><i class="fab fa-youtube"></i></a>
</div>
</div>
<div class="footer-section">
<h3>All Pages</h3>
<ul>
<li><a href="https://x-tova.blogspot.com/">Home</a></li>
<li><a href="https://x-tova.blogspot.com/p/news-events.html">News &amp; Events</a></li>
<li><a href="https://x-tova.blogspot.com/p/missions.html">Missions</a></li>
<li><a href="https://x-tova.blogspot.com/p/solar-system.html">Solar System</a></li>
</ul>
</div>
<div class="footer-section">
<h3><span style="color: transparent;">~</span></h3>
<ul>
<li><a href="https://x-tova.blogspot.com/p/earth.html">Earth</a></li>
<li><a href="https://x-tova.blogspot.com/p/universe.html">The Universe</a></li>
<li><a href="https://x-tova.blogspot.com/p/technology.html">Technology</a></li>
<li><a href="https://x-tova.blogspot.com/p/about.html">About</a></li>
</ul>
</div>
</div>
<div class="footer-bottom">
        © 2025 X-TOVA. All rights reserved.
      </div>
</footer></body>