# index-html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>S.R.K Studio | Premium Wedding Photography & Cinematography</title>

  <meta name="description" content="S.R.K Studio - Premium wedding photography, cinematic videography, drone coverage and wedding planning assistance in Saharsa, Bihar." />

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --burgundy: #4b0016;
      --deep-burgundy: #170006;
      --gold: #d7aa32;
      --light-gold: #ffe28a;
      --silver: #d8d8d8;
      --white: #ffffff;
      --soft-red: #ff8c8c;
      --yellow: #ffd15c;
      --glass: rgba(255, 255, 255, 0.08);
      --border: rgba(215, 170, 50, 0.35);
      --text: #f8eeee;
      --muted: #cdbfc4;
      --shadow: 0 35px 90px rgba(0, 0, 0, 0.55);
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Segoe UI", Arial, sans-serif;
      background:
        radial-gradient(circle at 20% 10%, rgba(215, 170, 50, 0.18), transparent 32%),
        radial-gradient(circle at 90% 20%, rgba(255, 140, 140, 0.12), transparent 35%),
        linear-gradient(180deg, #120005, #23000c 40%, #0a0003);
      color: var(--white);
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      background-image:
        linear-gradient(rgba(255,255,255,0.035) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,0.035) 1px, transparent 1px);
      background-size: 46px 46px;
      mask-image: linear-gradient(to bottom, black, transparent);
      z-index: -1;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    img {
      max-width: 100%;
      display: block;
    }

    .container {
      width: min(1180px, calc(100% - 36px));
      margin: auto;
    }

    .welcome-screen {
      position: fixed;
      inset: 0;
      z-index: 9999;
      display: grid;
      place-items: center;
      background:
        radial-gradient(circle, rgba(215,170,50,0.22), transparent 30%),
        linear-gradient(135deg, #080002, #3a0011, #090003);
      animation: welcomeOut 3s ease forwards;
    }

    .welcome-inner {
      text-align: center;
      perspective: 1200px;
    }

    .welcome-logo {
      width: 115px;
      height: 115px;
      margin: 0 auto 26px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      font-weight: 900;
      font-size: 2rem;
      color: #150005;
      background: conic-gradient(from 180deg, var(--gold), var(--silver), var(--light-gold), var(--burgundy), var(--gold));
      border: 3px solid rgba(255,255,255,0.5);
      box-shadow: 0 0 70px rgba(215,170,50,0.55);
      animation: logoSpin 2.4s ease;
    }

    .welcome-screen h1 {
      font-family: Georgia, serif;
      color: var(--light-gold);
      font-size: clamp(2.6rem, 9vw, 7.5rem);
      letter-spacing: clamp(8px, 2vw, 24px);
      text-transform: uppercase;
      transform-origin: center;
      animation: title3d 2.4s ease;
    }

    .welcome-screen p {
      margin-top: 20px;
      color: var(--silver);
      letter-spacing: 8px;
      font-size: 0.9rem;
      text-transform: uppercase;
      animation: fadeUp 1.6s ease 0.4s both;
    }

    @keyframes welcomeOut {
      0%, 78% {
        opacity: 1;
        visibility: visible;
      }
      100% {
        opacity: 0;
        visibility: hidden;
      }
    }

    @keyframes logoSpin {
      from {
        transform: rotateY(90deg) scale(0.6);
        opacity: 0;
      }
      to {
        transform: rotateY(0) scale(1);
        opacity: 1;
      }
    }

    @keyframes title3d {
      from {
        opacity: 0;
        transform: rotateX(72deg) translateY(60px) scale(0.75);
      }
      to {
        opacity: 1;
        transform: rotateX(0) translateY(0) scale(1);
      }
    }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(22px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: rgba(15, 0, 5, 0.78);
      backdrop-filter: blur(22px);
      border-bottom: 1px solid var(--border);
    }

    .navbar {
      min-height: 92px;
      display: grid;
      grid-template-columns: 1fr auto 1fr;
      align-items: center;
      gap: 20px;
    }

    .nav-left,
    .nav-right {
      display: flex;
      align-items: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .nav-right {
      justify-content: flex-end;
    }

    .brand-area {
      text-align: center;
    }

    .brand-logo {
      width: 58px;
      height: 58px;
      margin: 0 auto 6px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--gold), var(--silver), var(--yellow));
      color: #180006;
      font-weight: 900;
      border: 2px solid rgba(255,255,255,0.65);
      box-shadow: 0 0 35px rgba(215,170,50,0.35);
    }

    .brand-name {
      font-family: Georgia, serif;
      color: var(--gold);
      font-size: 1.45rem;
      letter-spacing: 5px;
      text-transform: uppercase;
    }

    .brand-ceo {
      color: var(--silver);
      font-size: 0.74rem;
      letter-spacing: 1px;
      margin-top: 4px;
    }

    .nav-link,
    .btn {
      border: 1px solid var(--border);
      padding: 10px 16px;
      border-radius: 999px;
      background: rgba(255,255,255,0.055);
      color: var(--text);
      font-size: 0.9rem;
      transition: 0.3s ease;
      cursor: pointer;
    }

    .nav-link:hover,
    .btn:hover {
      transform: translateY(-3px);
      background: var(--gold);
      color: #160005;
      box-shadow: 0 12px 30px rgba(215,170,50,0.25);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--gold), var(--yellow));
      color: #180006;
      font-weight: 800;
      border-color: rgba(255,255,255,0.5);
    }

    .btn-dark {
      background: linear-gradient(135deg, #7b062a, var(--burgundy));
      color: var(--white);
    }

    .hero {
      min-height: calc(100vh - 92px);
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      align-items: center;
      gap: 50px;
      padding: 80px 0;
    }

    .eyebrow {
      display: inline-flex;
      gap: 10px;
      align-items: center;
      color: var(--light-gold);
      border: 1px solid var(--border);
      background: rgba(255,255,255,0.07);
      padding: 9px 15px;
      border-radius: 999px;
      letter-spacing: 2px;
      font-size: 0.78rem;
      text-transform: uppercase;
      margin-bottom: 22px;
    }

    .hero h1 {
      font-family: Georgia, serif;
      font-size: clamp(3.2rem, 8vw, 7.2rem);
      line-height: 0.95;
      color: var(--white);
      letter-spacing: -2px;
    }

    .hero h1 span {
      display: block;
      color: var(--gold);
      text-shadow: 0 0 45px rgba(215,170,50,0.35);
    }

    .hero p {
      color: var(--muted);
      font-size: 1.08rem;
      line-height: 1.8;
      max-width: 650px;
      margin: 24px 0 0;
    }

    .hero-actions {
      display: flex;
      gap: 14px;
      margin-top: 34px;
      flex-wrap: wrap;
    }

    .hero-stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 14px;
      margin-top: 38px;
      max-width: 650px;
    }

    .stat {
      padding: 18px;
      border: 1px solid var(--border);
      border-radius: 22px;
      background: var(--glass);
    }

    .stat strong {
      color: var(--gold);
      font-size: 1.8rem;
      display: block;
      font-family: Georgia, serif;
    }

    .stat small {
      color: var(--silver);
    }

    .visual-stage {
      position: relative;
      min-height: 560px;
    }

    .camera-3d {
      position: absolute;
      inset: 40px 0 0;
      border-radius: 42px;
      background:
        radial-gradient(circle at 52% 43%, #111 0 13%, #050505 14% 19%, var(--silver) 20% 21%, #111 22% 31%, transparent 32%),
        radial-gradient(circle at 52% 43%, rgba(215,170,50,0.35), transparent 38%),
        linear-gradient(145deg, #393939, #060606 48%, #1b1b1b);
      border: 2px solid rgba(215,170,50,0.65);
      box-shadow: var(--shadow), inset 0 0 80px rgba(255,255,255,0.06);
      transform: rotate(-2deg);
      overflow: hidden;
    }

    .camera-3d::before {
      content: "";
      position: absolute;
      width: 260px;
      height: 80px;
      top: 72px;
      left: 50%;
      transform: translateX(-50%);
      border-radius: 30px 30px 8px 8px;
      background: linear-gradient(135deg, #1c1c1c, #5a5a5a, #111);
      border: 1px solid rgba(255,255,255,0.2);
    }

    .camera-3d::after {
      content: "CINEMATIC WEDDING FILMS";
      position: absolute;
      bottom: 44px;
      left: 0;
      right: 0;
      text-align: center;
      color: var(--gold);
      letter-spacing: 5px;
      font-size: 0.9rem;
      font-weight: 800;
    }

    .floating-card {
      position: absolute;
      left: 0;
      bottom: 35px;
      width: 260px;
      padding: 22px;
      border: 1px solid var(--border);
      border-radius: 24px;
      background: rgba(20,0,8,0.78);
      backdrop-filter: blur(18px);
      box-shadow: var(--shadow);
    }

    .floating-card h3 {
      color: var(--gold);
      margin-bottom: 8px;
    }

    .floating-card p {
      color: var(--muted);
      line-height: 1.6;
      font-size: 0.92rem;
    }

    section {
      padding: 90px 0;
    }

    .section-title {
      text-align: center;
      margin-bottom: 48px;
    }

    .section-title .mini {
      color: var(--light-gold);
      text-transform: uppercase;
      letter-spacing: 4px;
      font-size: 0.78rem;
    }

    .section-title h2 {
      margin-top: 12px;
      font-family: Georgia, serif;
      font-size: clamp(2.3rem, 5vw, 4.8rem);
      color: var(--white);
    }

    .section-title h2 span {
      color: var(--gold);
    }

    .section-title p {
      max-width: 720px;
      margin: 16px auto 0;
      color: var(--muted);
      line-height: 1.8;
    }

    .grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 24px;
    }

    .card {
      border: 1px solid var(--border);
      border-radius: 30px;
      padding: 30px;
      background:
        linear-gradient(145deg, rgba(255,255,255,0.11), rgba(255,255,255,0.035)),
        radial-gradient(circle at top right, rgba(215,170,50,0.18), transparent 35%);
      box-shadow: 0 22px 65px rgba(0,0,0,0.35);
      transition: 0.35s ease;
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: "";
      position: absolute;
      top: 0;
      left: -100%;
      width: 80%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.12), transparent);
      transform: skewX(-20deg);
      transition: 0.7s ease;
    }

    .card:hover::before {
      left: 120%;
    }

    .card:hover {
      transform: translateY(-8px);
      border-color: rgba(255,226,138,0.8);
      box-shadow: 0 32px 85px rgba(215,170,50,0.18);
    }

    .card h3 {
      color: var(--gold);
      font-size: 1.5rem;
      margin-bottom: 14px;
      font-family: Georgia, serif;
    }

    .card p,
    .card li {
      color: var(--muted);
      line-height: 1.8;
    }

    .card ul {
      margin: 16px 0 0 20px;
    }

    .rating {
      color: var(--yellow);
      font-weight: 900;
      letter-spacing: 2px;
      margin-bottom: 14px;
    }

    .tag {
      display: inline-block;
      padding: 7px 11px;
      border-radius: 999px;
      border: 1px solid var(--border);
      color: var(--light-gold);
      font-size: 0.75rem;
      margin-bottom: 16px;
      background: rgba(255,255,255,0.05);
    }

    .planning-box {
      display: grid;
      grid-template-columns: 1.1fr 0.9fr;
      gap: 26px;
      align-items: stretch;
    }

    .lux-box {
      border: 1px solid var(--border);
      border-radius: 36px;
      padding: 36px;
      background:
        linear-gradient(135deg, rgba(75,0,22,0.75), rgba(255,255,255,0.07)),
        radial-gradient(circle at 20% 10%, rgba(215,170,50,0.22), transparent 32%);
      box-shadow: var(--shadow);
    }

    .lux-box h2 {
      color: var(--gold);
      font-family: Georgia, serif;
      font-size: clamp(1.8rem, 4vw, 3.3rem);
      margin-bottom: 15px;
    }

    .lux-box p {
      color: var(--muted);
      line-height: 1.8;
      margin-bottom: 20px;
    }

    form {
      display: grid;
      gap: 16px;
    }

    .form-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 16px;
    }

    input,
    select,
    textarea {
      width: 100%;
      padding: 15px 16px;
      border-radius: 16px;
      border: 1px solid rgba(215,170,50,0.38);
      background: rgba(255,255,255,0.075);
      color: var(--white);
      outline: none;
      font: inherit;
    }

    input:focus,
    select:focus,
    textarea:focus {
      border-color: var(--light-gold);
      box-shadow: 0 0 0 4px rgba(215,170,50,0.13);
    }

    input::placeholder,
    textarea::placeholder {
      color: #c8b9be;
    }

    select option {
      color: #111;
    }

    .success {
      display: none;
      margin-top: 15px;
      padding: 15px;
      border-radius: 16px;
      border: 1px solid rgba(215,170,50,0.7);
      background: rgba(215,170,50,0.13);
      color: var(--light-gold);
      font-weight: 700;
    }

    .portfolio {
      min-height: 300px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      border-radius: 32px;
      padding: 28px;
      border: 1px solid var(--border);
      background:
        linear-gradient(to top, rgba(15,0,5,0.92), rgba(15,0,5,0.15)),
        radial-gradient(circle at 50% 35%, rgba(255,255,255,0.18), transparent 12%),
        linear-gradient(135deg, rgba(215,170,50,0.38), rgba(192,192,192,0.2), rgba(75,0,22,0.9));
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
    }

    .portfolio::before {
      content: "";
      position: absolute;
      inset: 20px;
      border: 1px solid rgba(255,255,255,0.22);
      border-radius: 24px;
    }

    .portfolio h3,
    .portfolio p {
      position: relative;
      z-index: 1;
    }

    .portfolio h3 {
      color: var(--gold);
      font-family: Georgia, serif;
      font-size: 1.45rem;
      margin-bottom: 8px;
    }

    .portfolio p {
      color: var(--text);
      line-height: 1.7;
    }

    .contact-info p {
      margin: 11px 0;
      color: var(--muted);
      line-height: 1.6;
    }

    .contact-info strong {
      color: var(--gold);
    }

    footer {
      padding: 60px 0 35px;
      background: #070002;
      border-top: 1px solid var(--border);
      text-align: center;
    }

    .footer-brand {
      color: var(--gold);
      font-family: Georgia, serif;
      font-size: 2.4rem;
      margin-bottom: 10px;
    }

    .socials {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      gap: 10px;
      margin: 26px 0;
    }

    .socials a {
      padding: 10px 16px;
      border: 1px solid var(--border);
      border-radius: 999px;
      color: var(--silver);
      background: rgba(255,255,255,0.04);
      transition: 0.3s;
    }

    .socials a:hover {
      color: #160005;
      background: var(--gold);
    }

    .thank {
      margin-top: 28px;
      color: var(--light-gold);
      letter-spacing: 2px;
      text-transform: uppercase;
    }

    .floating-whatsapp {
      position: fixed;
      right: 22px;
      bottom: 22px;
      z-index: 900;
      padding: 15px 20px;
      border-radius: 999px;
      background: linear-gradient(135deg, var(--gold), var(--yellow));
      color: #150005;
      font-weight: 900;
      box-shadow: 0 18px 45px rgba(215,170,50,0.35);
    }

    @media (max-width: 980px) {
      .navbar {
        grid-template-columns: 1fr;
        text-align: center;
        padding: 16px 0;
      }

      .nav-left,
      .nav-right {
        justify-content: center;
      }

      .hero,
      .planning-box,
      .grid-2 {
        grid-template-columns: 1fr;
      }

      .visual-stage {
        min-height: 440px;
      }

      .grid {
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 640px) {
      .grid,
      .hero-stats,
      .form-grid {
        grid-template-columns: 1fr;
      }

      section {
        padding: 70px 0;
      }

      .hero {
        padding-top: 50px;
      }

      .camera-3d {
        inset: 20px 0 0;
      }

      .floating-card {
        width: calc(100% - 20px);
        left: 10px;
      }
    }
  </style>
</head>

<body>
  <div class="welcome-screen">
    <div class="welcome-inner">
      <div class="welcome-logo">SRK</div>
      <h1>S.R.K Studio</h1>
      <p>Welcome to S.R.K Studio</p>
    </div>
  </div>

  <header>
    <div class="container navbar">
      <div class="nav-left">
        <a class="nav-link" href="#profile">Profile</a>
      </div>

      <div class="brand-area">
        <div class="brand-logo">SRK</div>
        <div class="brand-name">S.R.K Studio</div>
        <div class="brand-ceo">CEO S.R.K Studio: Sharvan Yadav</div>
      </div>

      <div class="nav-right">
        <a class="nav-link" href="#home">Home</a>
        <a class="nav-link" href="#vendor">Wedding Vendor</a>
        <a class="nav-link" href="#real">Real Wedding</a>
        <a class="nav-link" href="#book">Book Now</a>
        <a class="nav-link" href="#login">Log In</a>
        <a class="btn btn-primary" href="#signup">Sign Up</a>
      </div>
    </div>
  </header>

  <main>
    <section class="container hero" id="home">
      <div>
        <div class="eyebrow">Premium Wedding Studio</div>
        <h1>World Class <span>Wedding Films</span></h1>
        <p>
          S.R.K Studio creates luxury wedding photography, cinematic videography, drone coverage,
          royal couple portraits and premium wedding memories for families who want their wedding
          to look grand, emotional and unforgettable.
        </p>

        <div class="hero-actions">
          <a href="#book" class="btn btn-primary">Book My Wedding Plan</a>
          <a href="https://wa.me/919110066743" class="btn btn-dark">WhatsApp 9110066743</a>
        </div>

        <div class="hero-stats">
          <div class="stat">
            <strong>7</strong>
            <small>Camera Categories</small>
          </div>
          <div class="stat">
            <strong>5</strong>
            <small>Star Rated Plans</small>
          </div>
          <div class="stat">
            <strong>24/7</strong>
            <small>Booking Support</small>
          </div>
        </div>
      </div>

      <div class="visual-stage">
        <div class="camera-3d"></div>
        <div class="floating-card">
          <h3>Cinematic Camera Setup</h3>
          <p>Drone shots, film-like color grading, candid moments, royal portraits and full wedding coverage.</p>
        </div>
      </div>
    </section>

    <section id="profile">
      <div class="container planning-box">
        <div class="lux-box">
          <h2>GET WEDDING PLANNING HELP FROM S.R.K Studio</h2>
          <p>
            S.R.K Studio is now offering wedding assistance on WhatsApp / Telegram number:
            <strong style="color:var(--gold)">9110066743</strong>.
            Contact us for camera selection, wedding shoot planning, booking support and package guidance.
          </p>
          <a class="btn btn-primary" href="https://wa.me/919110066743">Join Now</a>
        </div>

        <div class="lux-box">
          <h2>JOIN OUR EXCLUSIVE EMAIL LIST</h2>
          <p>The best of inspiration and ideas delivered to your inbox.</p>
          <form onsubmit="showSuccess(event, 'emailSuccess')">
            <input type="email" placeholder="Your Email Address*" required />
            <button class="btn btn-primary" type="submit">Subscribe Now</button>
          </form>
          <div class="success" id="emailSuccess">Thank you. Your email has been submitted.</div>
        </div>
      </div>
    </section>

    <section id="vendor">
      <div class="container">
        <div class="section-title">
          <div class="mini">Wedding Vendor</div>
          <h2>Select Your <span>Camera Category</span></h2>
          <p>Every camera section is designed for a different level of wedding coverage. All categories include five star rating.</p>
        </div>

        <div class="grid">
          <div class="card">
            <span class="tag">Luxury Package</span>
            <h3>Aplus Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Cinematic photography and videography with premium camera setup, drone, film-like videography and luxury editing.</p>
            <ul>
              <li>Drone wedding shots</li>
              <li>Cinematic wedding film</li>
              <li>Premium photo album</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>

          <div class="card">
            <span class="tag">Premium Package</span>
            <h3>A Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Professional DSLR/mirrorless camera, candid photography, couple shoot, full HD video and highlights.</p>
            <ul>
              <li>Candid coverage</li>
              <li>Creative highlights</li>
              <li>Premium editing</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>

          <div class="card">
            <span class="tag">Royal Package</span>
            <h3>B Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Traditional wedding photography and videography with family moments, stage coverage and clean editing.</p>
            <ul>
              <li>Stage coverage</li>
              <li>Family photography</li>
              <li>Full event video</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>

          <div class="card">
            <span class="tag">Smart Package</span>
            <h3>C Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Budget-friendly package for quality photo and video coverage for small and medium wedding events.</p>
            <ul>
              <li>Photo coverage</li>
              <li>Video recording</li>
              <li>Basic editing</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>

          <div class="card">
            <span class="tag">Event Package</span>
            <h3>D Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Compact ceremony coverage for engagement, haldi, mehndi, reception and family programs.</p>
            <ul>
              <li>Function shoot</li>
              <li>Short event video</li>
              <li>Edited photos</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>

          <div class="card">
            <span class="tag">Basic Package</span>
            <h3>E Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Basic event photography and simple video recording for birthday, local events and family functions.</p>
            <ul>
              <li>Basic camera setup</li>
              <li>Simple video</li>
              <li>Affordable service</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>

          <div class="card">
            <span class="tag">Entry Package</span>
            <h3>F Category</h3>
            <div class="rating">Five Star Rating</div>
            <p>Entry-level photo coverage with essential camera setup for simple bookings and small events.</p>
            <ul>
              <li>Essential photo shoot</li>
              <li>Simple booking</li>
              <li>Low budget plan</li>
            </ul>
            <br />
            <a class="btn btn-primary" href="#book">Select</a>
          </div>
        </div>
      </div>
    </section>

    <section id="real">
      <div class="container">
        <div class="section-title">
          <div class="mini">Real Wedding</div>
          <h2>Photo & Video <span>Experience</span></h2>
          <p>Here customers can understand the difference between camera categories and wedding coverage style.</p>
        </div>

        <div class="grid-2">
          <div class="portfolio">
            <h3>Aplus Cinematic Wedding</h3>
            <p>Drone, film color, royal couple shots and movie-style wedding video.</p>
          </div>

          <div class="portfolio">
            <h3>Premium Photography</h3>
            <p>Candid moments, bridal portraits, groom entry, stage and family photography.</p>
          </div>

          <div class="portfolio">
            <h3>Traditional Wedding Coverage</h3>
            <p>Complete rituals, family blessings, reception and event documentation.</p>
          </div>

          <div class="portfolio">
            <h3>Budget Wedding Plan</h3>
            <p>Professional basic coverage for small functions with clean photos and videos.</p>
          </div>
        </div>
      </div>
    </section>

    <section>
      <div class="container">
        <div class="section-title">
          <div class="mini">Quick Form</div>
          <h2>Book My <span>Wedding Plan</span></h2>
          <p>Fill this form before booking your wedding plan.</p>
        </div>

        <div class="lux-box">
          <form onsubmit="showSuccess(event, 'quickSuccess')">
            <div class="form-grid">
              <input type="text" placeholder="Name" required />
              <input type="tel" placeholder="Number" required />
              <input type="email" placeholder="Email Address" required />
              <input type="text" placeholder="State" required />
              <input type="text" placeholder="District" required />
              <input type="text" placeholder="Location" required />
              <select required>
                <option value="">Choose Camera Type</option>
                <option>Aplus Category</option>
                <option>A Category</option>
                <option>B Category</option>
                <option>C Category</option>
                <option>D Category</option>
                <option>E Category</option>
                <option>F Category</option>
              </select>
            </div>
            <button class="btn btn-primary" type="submit">Submit Form</button>
          </form>

          <div class="success" id="quickSuccess">
            Your form has been submitted. Booking confirmation ke liye 9110066743 par contact karein.
          </div>

          <p style="margin-top:20px;color:var(--muted)">
            Booking ke liye phone number: <strong style="color:var(--gold)">9110066743</strong> WhatsApp / Telegram no.
          </p>
        </div>
      </div>
    </section>

    <section id="book">
      <div class="container">
        <div class="section-title">
          <div class="mini">Book Now</div>
          <h2>Full Wedding <span>Booking Form</span></h2>
          <p>WhatsApp, Telegram and phone booking available. Advance booking and UPI payment details will be added later.</p>
        </div>

        <div class="grid-2">
          <div class="lux-box contact-info">
            <h2>Contact Information</h2>
            <p><strong>Phone:</strong> 9110066743</p>
            <p><strong>WhatsApp:</strong> 9110066743</p>
            <p><strong>Telegram:</strong> 9110066743</p>
            <p><strong>State:</strong> Bihar</p>
            <p><strong>District:</strong> Saharsa</p>
            <p><strong>Street:</strong> Yadav Chowk, Dumrail</p>
            <p><strong>Pincode:</strong> 852201</p>
            <br />
            <a class="btn btn-primary" href="https://wa.me/919110066743">Open WhatsApp</a>
            <a class="btn btn-dark" href="#">Telegram Link</a>
          </div>

          <div class="lux-box">
            <h2>Payment Method</h2>
            <p>
              Payment on UPI number and advance booking charge will be added later.
              For now, please call or message S.R.K Studio for final booking confirmation.
            </p>
          </div>
        </div>

        <br /><br />

        <div class="lux-box">
          <form onsubmit="showSuccess(event, 'bookingSuccess')">
            <div class="form-grid">
              <input type="text" placeholder="Name" required />
              <input type="tel" placeholder="Number" required />
              <input type="text" placeholder="State" required />
              <input type="text" placeholder="District" required />
              <input type="text" placeholder="Pincode" required />
              <input type="email" placeholder="Email Address" required />
              <input type="text" placeholder="Location" required />
              <input type="text" placeholder="Groom/Bride Name" required />
              <input type="tel" placeholder="Groom/Bride Number" required />
              <input type="number" placeholder="For How Many Days" required />
              <input type="date" required />
              <input type="date" required />

              <select required>
                <option value="">Choose Camera Section</option>
                <option>Aplus Category</option>
                <option>A Category</option>
                <option>B Category</option>
                <option>C Category</option>
                <option>D Category</option>
                <option>E Category</option>
                <option>F Category</option>
              </select>
            </div>

            <textarea rows="4" placeholder="Extra Information"></textarea>
            <button class="btn btn-primary" type="submit">Book Now</button>
          </form>

          <div class="success" id="bookingSuccess">
            Thank you. Your wedding booking request has been submitted. Please call 9110066743 for confirmation.
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div class="footer-brand">S.R.K Studio</div>
      <p style="color:var(--muted)">Premium Wedding Photography & Cinematic Videography</p>
      <p style="color:var(--muted);margin-top:10px">
        Phone: 9110066743 | Yadav Chowk, Dumrail, Saharsa, Bihar - 852201
      </p>

      <div class="socials">
        <a href="#">Instagram URL</a>
        <a href="#">Facebook URL</a>
        <a href="#">LinkedIn URL</a>
        <a href="#">X URL</a>
        <a href="#">YouTube Channel URL</a>
      </div>

      <div class="thank">Thank you for visiting site</div>
    </div>
  </footer>

  <a class="floating-whatsapp" href="https://wa.me/919110066743">WhatsApp Now</a>

  <script>
    function showSuccess(event, id) {
      event.preventDefault();
      const successBox = document.getElementById(id);
      successBox.style.display = "block";
      event.target.reset();

      setTimeout(() => {
        successBox.scrollIntoView({
          behavior: "smooth",
          block: "center"
        });
      }, 100);
    }

    const cards = document.querySelectorAll(".card, .portfolio, .lux-box");

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = "1";
          entry.target.style.transform = "translateY(0)";
        }
      });
    }, {
      threshold: 0.15
    });

    cards.forEach((card) => {
      card.style.opacity = "0";
      card.style.transform = "translateY(35px)";
      card.style.transition = "0.7s ease";
      observer.observe(card);
    });
  </script>
</body>
</html>
