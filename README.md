<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>SUMIT.EDITING — Video Editor & Thumbnail Designer</title>

<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  scroll-behavior:smooth;
}

:root{
  --bg:#0b0b0d;
  --card:#131316;
  --border:#2c2c31;
  --text:#f5f5f5;
  --muted:#a5a5ad;
  --accent:#f4c928;
  --accent2:#ff8a3d;
}

body{
  font-family:Arial,Helvetica,sans-serif;
  background:
    radial-gradient(circle at 80% 10%,rgba(244,201,40,.10),transparent 25%),
    radial-gradient(circle at 10% 60%,rgba(255,138,61,.07),transparent 25%),
    var(--bg);
  color:var(--text);
  line-height:1.6;
}

a{
  color:inherit;
  text-decoration:none;
}

.container{
  width:min(1100px,92%);
  margin:auto;
}

/* NAVBAR */

nav{
  position:sticky;
  top:0;
  z-index:100;
  backdrop-filter:blur(15px);
  background:rgba(11,11,13,.82);
  border-bottom:1px solid var(--border);
}

.nav-inner{
  height:72px;
  display:flex;
  align-items:center;
  justify-content:space-between;
}

.logo{
  font-size:22px;
  font-weight:900;
  letter-spacing:1px;
}

.logo span{
  color:var(--accent);
}

.nav-links{
  display:flex;
  gap:25px;
  color:#bbb;
  font-size:14px;
}

.nav-links a:hover{
  color:var(--accent);
}

.nav-btn{
  border:1px solid var(--accent);
  padding:10px 18px;
  border-radius:14px;
  color:var(--accent);
  transition:.2s;
}

.nav-btn:hover{
  background:var(--accent);
  color:#111;
}

/* HERO */

.hero{
  min-height:calc(100vh - 72px);
  display:flex;
  align-items:center;
  padding:80px 0;
}

.badge{
  display:inline-flex;
  padding:9px 15px;
  border:1px solid #5c501f;
  background:rgba(244,201,40,.07);
  color:#ead45f;
  border-radius:30px;
  font-size:14px;
  margin-bottom:25px;
}

.hero h1{
  font-size:clamp(48px,8vw,88px);
  line-height:.98;
  max-width:800px;
  letter-spacing:-4px;
}

.hero h1 span{
  color:var(--accent2);
}

.hero p{
  max-width:650px;
  color:var(--muted);
  font-size:18px;
  margin:25px 0 30px;
}

.buttons{
  display:flex;
  gap:14px;
  flex-wrap:wrap;
}

.btn{
  display:inline-block;
  border:1px solid var(--border);
  padding:14px 22px;
  border-radius:16px;
  font-weight:700;
  transition:.2s;
}

.btn:hover{
  transform:translateY(-3px);
  border-color:var(--accent);
}

.btn:active{
  transform:scale(.94);
}

.primary{
  background:var(--accent);
  color:#111;
  border-color:var(--accent);
}

.primary:hover{
  background:#ffe064;
}

/* STATS */

.stats{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:15px;
  margin-top:55px;
}

.stat{
  padding:22px;
  border:1px solid var(--border);
  border-radius:20px;
  background:rgba(255,255,255,.025);
}

.stat strong{
  display:block;
  font-size:28px;
  color:white;
}

.stat span{
  color:var(--muted);
  font-size:14px;
}

/* SECTIONS */

section{
  padding:90px 0;
}

.section-title{
  margin-bottom:35px;
}

.section-title small{
  color:var(--accent);
  font-weight:bold;
}

.section-title h2{
  font-size:42px;
  margin-top:5px;
}

/* SERVICES */

.services{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:18px;
}

.service{
  border:1px solid var(--border);
  background:var(--card);
  border-radius:24px;
  padding:28px;
  transition:.25s;
}

.service:hover{
  transform:translateY(-7px);
  border-color:#635725;
}

.icon{
  font-size:35px;
  margin-bottom:15px;
}

.service h3{
  margin-bottom:10px;
}

.service p{
  color:var(--muted);
  font-size:14px;
}

/* PORTFOLIO */

.portfolio{
  display:grid;
  grid-template-columns:repeat(2,1fr);
  gap:20px;
}

.work{
  overflow:hidden;
  border:1px solid var(--border);
  border-radius:24px;
  background:var(--card);
}

.work-img{
  height:270px;
  display:flex;
  align-items:center;
  justify-content:center;
  text-align:center;
  padding:25px;
  background:
    radial-gradient(circle at 50% 50%,#442000,transparent 45%),
    linear-gradient(135deg,#050505,#1d1208);
}

.work-img h3{
  font-size:34px;
}

.work-img span{
  color:var(--accent);
}

.work-info{
  padding:20px;
}

.work-info p{
  color:var(--muted);
  font-size:14px;
}

/* ABOUT */

.about{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:30px;
}

.about-card{
  border:1px solid var(--border);
  background:var(--card);
  border-radius:25px;
  padding:30px;
}

.about-card p{
  color:var(--muted);
  margin-top:15px;
}

.skills{
  display:flex;
  flex-wrap:wrap;
  gap:10px;
  margin-top:20px;
}

.skill{
  border:1px solid #393939;
  border-radius:30px;
  padding:8px 13px;
  color:#ddd;
  font-size:13px;
}

/* CONTACT */

.contact{
  text-align:center;
  border:1px solid var(--border);
  background:
    radial-gradient(circle,#332707,transparent 55%),
    var(--card);
  border-radius:30px;
  padding:55px 25px;
}

.contact h2{
  font-size:45px;
  margin-bottom:12px;
}

.contact p{
  color:var(--muted);
  max-width:600px;
  margin:0 auto 25px;
}

/* FOOTER */

footer{
  border-top:1px solid var(--border);
  padding:30px 0;
  text-align:center;
  color:#777;
  font-size:13px;
}

/* MOBILE */

@media(max-width:750px){

  .nav-links{
    display:none;
  }

  .hero{
    padding:65px 0;
  }

  .hero h1{
    font-size:52px;
    letter-spacing:-2px;
  }

  .hero p{
    font-size:16px;
  }

  .stats{
    grid-template-columns:1fr;
  }

  .services{
    grid-template-columns:1fr;
  }

  .portfolio{
    grid-template-columns:1fr;
  }

  .about{
    grid-template-columns:1fr;
  }

  .section-title h2{
    font-size:34px;
  }

  .contact h2{
    font-size:34px;
  }

  .work-img{
    height:220px;
  }

  .nav-btn{
    padding:8px 13px;
  }
}
</style>
</head>

<body>

<!-- NAVBAR -->

<nav>
  <div class="container nav-inner">

    <a href="#" class="logo">
      SUMIT<span>.EDITING</span>
    </a>

    <div class="nav-links">
      <a href="#services">Services</a>
      <a href="#portfolio">Portfolio</a>
      <a href="#about">About</a>
    </div>

    <a href="#contact" class="nav-btn">
      Hire Me
    </a>

  </div>
</nav>


<!-- HERO -->

<header class="hero">
<div class="container">

  <div class="badge">
    🎬 Video Editor &nbsp;•&nbsp; 🖼️ Thumbnail Designer
  </div>

  <h1>
    Make your content
    <span>stand out.</span>
  </h1>

  <p>
    I create engaging short-form video edits, YouTube thumbnails,
    colour grading and clean creative designs for creators and businesses.
  </p>

  <div class="buttons">
    <a href="#contact" class="btn primary">
      ⚡ Start a Project
    </a>

    <a href="#portfolio" class="btn">
      View My Work
    </a>
  </div>

  <div class="stats">

    <div class="stat">
      <strong>3+</strong>
      <span>Video Samples</span>
    </div>

    <div class="stat">
      <strong>2+</strong>
      <span>Thumbnail Samples</span>
    </div>

    <div class="stat">
      <strong>100%</strong>
      <span>Mobile Friendly</span>
    </div>

  </div>

</div>
</header>


<!-- SERVICES -->

<section id="services">
<div class="container">

  <div class="section-title">
    <small>WHAT I DO</small>
    <h2>My Services</h2>
  </div>

  <div class="services">

    <div class="service">
      <div class="icon">🎬</div>
      <h3>Video Editing</h3>
      <p>
        Reels, Shorts and other short-form videos with
        smooth cuts, transitions, captions and effects.
      </p>
    </div>

    <div class="service">
      <div class="icon">🖼️</div>
      <h3>Thumbnail Design</h3>
      <p>
        Eye-catching thumbnails designed to make your
        videos look more professional.
      </p>
    </div>

    <div class="service">
      <div class="icon">🎨</div>
      <h3>Colour Grading</h3>
      <p>
        Cinematic colour correction and grading to give
        your footage a better visual style.
      </p>
    </div>

  </div>

</div>
</section>


<!-- PORTFOLIO -->

<section id="portfolio">
<div class="container">

  <div class="section-title">
    <small>MY WORK</small>
    <h2>Selected Projects</h2>
  </div>

  <div class="portfolio">

    <div class="work">
      <div class="work-img">
        <div>
          <h3>Dance <span>Cover</span></h3>
          <p>Thumbnail Design</p>
        </div>
      </div>

      <div class="work-info">
        <h3>Dance Cover Thumbnail</h3>
        <p>
          Creative YouTube-style thumbnail with cinematic
          background and strong typography.
        </p>
      </div>
    </div>


    <div class="work">
      <div class="work-img">
        <div>
          <h3>FACE <span>CARE</span></h3>
          <p>Advertisement Design</p>
        </div>
      </div>

      <div class="work-info">
        <h3>Business Advertisement</h3>
        <p>
          Promotional creative designed for a local
          beauty and grooming service.
        </p>
      </div>
    </div>


    <div class="work">
      <div class="work-img">
        <div>
          <h3>REELS <span>EDIT</span></h3>
          <p>Short-form Video</p>
        </div>
      </div>

      <div class="work-info">
        <h3>Instagram Reel Editing</h3>
        <p>
          Fast-paced edits, captions, transitions and
          social-media friendly composition.
        </p>
      </div>
    </div>


    <div class="work">
      <div class="work-img">
        <div>
          <h3>CINEMATIC <span>LOOK</span></h3>
          <p>Colour Grading</p>
        </div>
      </div>

      <div class="work-info">
        <h3>Cinematic Colour Grade</h3>
        <p>
          Moody and cinematic colour treatment for
          short-form content.
        </p>
      </div>
    </div>

  </div>

</div>
</section>


<!-- ABOUT -->

<section id="about">
<div class="container">

  <div class="section-title">
    <small>ABOUT ME</small>
    <h2>Creative. Simple. Effective.</h2>
  </div>

  <div class="about">

    <div class="about-card">
      <h3>Why work with me?</h3>

      <p>
        I focus on clean, modern and engaging designs that
        help creators present their content professionally.
      </p>

      <p>
        Whether you need a Reel edit, YouTube thumbnail
        or colour grading, I can help turn your idea into
        polished content.
      </p>
    </div>

    <div class="about-card">

      <h3>Skills</h3>

      <div class="skills">
        <span class="skill">Video Editing</span>
        <span class="skill">Reels</span>
        <span class="skill">YouTube Shorts</span>
        <span class="skill">Thumbnail Design</span>
        <span class="skill">Colour Grading</span>
        <span class="skill">Creative Design</span>
        <span class="skill">Mobile Editing</span>
      </div>

    </div>

  </div>

</div>
</section>


<!-- CONTACT -->

<section id="contact">
<div class="container">

  <div class="contact">

    <h2>Have a project?</h2>

    <p>
      Tell me what you need and let's create something
      that makes your content stand out.
    </p>

    <div class="buttons" style="justify-content:center">

      <!-- Replace these links with your own contact links -->

      <a
        href="mailto:your-email@example.com"
        class="btn primary"
      >
        📩 Email Me
      </a>

      <a
        href="https://instagram.com/"
        target="_blank"
        class="btn"
      >
        📸 Instagram
      </a>

    </div>

  </div>

</div>
</section>


<footer>
  © 2026 SUMIT.EDITING • Video Editor & Thumbnail Designer
</footer>


<script>
/* Smooth button click feedback */

document.querySelectorAll(".btn,.nav-btn").forEach(function(button){

  button.addEventListener("click",function(){

    button.style.transform="scale(.92)";

    setTimeout(function(){
      button.style.transform="";
    },150);

  });

});
</script>

</body>
</html>
