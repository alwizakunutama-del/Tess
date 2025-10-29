
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>(AlwizzTeamX)</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
  }

  body {
    height: 100vh;
    background: #000;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    color: #ff002b;
    text-align: center;
    overflow: hidden;
    padding: 15px;
  }

  .container {
    background: rgba(20, 0, 0, 0.8);
    border: 1px solid #ff002b;
    backdrop-filter: blur(8px);
    border-radius: 20px;
    padding: 40px 50px;
    box-shadow: 0 0 25px rgba(255,0,43,0.4);
    animation: fadeIn 1s ease-in-out;
    width: 100%;
    max-width: 400px;
    position: relative;
    overflow: hidden;
  }

  h1 {
    margin-bottom: 20px;
    font-weight: 600;
    text-shadow: 0 0 20px #ff002b;
    font-size: 1.6rem;
  }

  input {
    width: 100%;
    padding: 12px 15px;
    font-size: 16px;
    border-radius: 10px;
    border: 1px solid #ff002b;
    outline: none;
    margin-bottom: 25px;
    text-align: center;
    background: transparent;
    color: #ff002b;
    transition: 0.3s;
  }
  input:focus {
    box-shadow: 0 0 10px #ff002b;
  }

  .btn {
    width: 48%;
    padding: 10px;
    margin: 1%;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    font-weight: bold;
    color: white;
    transition: 0.3s;
    position: relative;
    overflow: hidden;
    box-shadow: 0 0 15px rgba(255,0,43,0.6);
  }

  .btn::before {
    content: "";
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: rgba(255,255,255,0.15);
    transition: all 0.3s;
  }

  .btn:hover::before {
    left: 0;
  }

  /* 🔥 Ripple animasi */
  .btn::after {
    content: "";
    position: absolute;
    border-radius: 50%;
    transform: scale(0);
    background: rgba(255,0,43,0.6);
    animation: none;
  }

  .btn.ripple::after {
    animation: rippleEffect 0.6s linear;
  }

  @keyframes rippleEffect {
    from {
      transform: scale(0);
      opacity: 1;
    }
    to {
      transform: scale(4);
      opacity: 0;
    }
  }

  .ban {
    background: linear-gradient(45deg, #ff002b, #5c000f);
  }
  .unban {
    background: linear-gradient(45deg, #5c000f, #ff002b);
  }

  .link-btn {
    display: block;
    margin-top: 25px;
    text-decoration: none;
    background: rgba(255,0,43,0.2);
    border: 1px solid #ff002b;
    padding: 10px 20px;
    border-radius: 12px;
    color: #ff002b;
    font-weight: 600;
    transition: 0.3s;
    box-shadow: 0 0 15px rgba(255,0,43,0.4);
  }
  .link-btn:hover {
    background: rgba(255,0,43,0.4);
    box-shadow: 0 0 25px rgba(255,0,43,0.8);
  }

  .footer {
    margin-top: 15px;
    font-size: 14px;
    opacity: 0.8;
  }
  .footer a {
    color: #ff002b;
    text-decoration: none;
  }
  .footer a:hover {
    text-shadow: 0 0 10px #ff002b;
  }

  @keyframes fadeIn {
    from {opacity: 0; transform: translateY(20px);}
    to {opacity: 1; transform: translateY(0);}
  }

  /* 📱 Responsif untuk HP */
  @media (max-width: 480px) {
    .container {
      padding: 25px 20px;
      border-radius: 15px;
      box-shadow: 0 0 15px rgba(255,0,43,0.3);
    }

    h1 {
      font-size: 1.2rem;
    }

    input {
      font-size: 14px;
      padding: 10px;
    }

    .btn {
      width: 100%;
      margin-top: 10px;
    }

    .link-btn {
      font-size: 14px;
      padding: 8px 15px;
    }
  }
</style>
</head>
<body>
  <div class="container">
    <h1>BAN UNBAN VIP</h1>
    <input type="text" id="phone" placeholder="+62xxxxxxxxxx">
    <br>
    <div style="display:flex;justify-content:center;flex-wrap:wrap;">
      <button class="btn ban" onclick="sendEmail(event, 'ban')">Ban</button>
      <button class="btn unban" onclick="sendEmail(event, 'unban')">Unban</button>
    </div>
    <a class="link-btn" href="https://whatsapp.com/channel/0029VbAsKVFF6sn6f2Fvu51G" target="_blank">Join WhatsApp Channel</a>
    <p class="footer">by <a href="https://t.me/AlwizzMarket" target="_blank">t.me/AlwizzMarket</a></p>
  </div>

<script>
function sendEmail(e, type) {
  const phone = document.getElementById("phone").value.trim();
  if (!phone) {
    alert("Masukkan nomor telepon terlebih dahulu!");
    return;
  }

  let subject, body;

  if (type === "ban") {
    subject = "Request Disable WhatsApp Account";
    body = `Halo, saya kehilangan dokumen saya bersama dengan ponsel dan kartu SIM saya. Jadi saya ingin Anda segera menonaktifkan nomor saya, karena saya takut seseorang dapat masuk ke akun WhatsApp saya. Nomor saya adalah: ${phone}`;
  } else {
    subject = "Request Unban WhatsApp Account";
    body = `Mohon aktifkan kembali nomor saya karena saya tidak melanggar aturan WhatsApp. Tiba-tiba nomor saya diblokir. Mohon aktifkan kembali nomor ini: ${phone}\n\nTerima kasih atas perhatian Anda.`;
  }

  const mailtoLink = `mailto:support@support.whatsapp.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;

  // Efek ripple 🔥
  const btn = e.target;
  const ripple = document.createElement("span");
  ripple.classList.add("ripple");
  const rect = btn.getBoundingClientRect();
  ripple.style.left = `${e.clientX - rect.left}px`;
  ripple.style.top = `${e.clientY - rect.top}px`;
  btn.appendChild(ripple);

  setTimeout(() => ripple.remove(), 600);

  // Efek tekan kecil
  btn.style.transform = "scale(0.9)";
  setTimeout(() => { btn.style.transform = "scale(1)"; }, 150);

  // Buka Gmail
  window.location.href = mailtoLink;
}
</script>
</body>
