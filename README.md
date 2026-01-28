(function () {
  const PASSWORD = ruhi123";
  const input = prompt("Şifre:");

  if (input !== PASSWORD) {
    alert("Yanlış şifre.");
    return;
  }


  const img = "https://i.hizliresim.com/luext8z.jpg";

  let s = document.getElementById("eba-clean-bg");
  if (s) s.remove();

  s = document.createElement("style");
  s.id = "eba-clean-bg";
  s.innerHTML = `
    body::before {
      content: "";
      position: fixed;
      inset: 0;
      z-index: -1;
      background:
        linear-gradient(
          rgba(0,0,0,0.55),
          rgba(0,0,0,0.75)
        ),
        url("${img}") center / cover no-repeat;
    }

    html, body {
      background: transparent !important;
      color: #eaeaea !important;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, sans-serif !important;
    }

    header, nav {
      background: rgba(10,10,10,0.85) !important;
      backdrop-filter: blur(8px);
      border-bottom: 1px solid rgba(255,255,255,0.08);
    }

    aside {
      background: rgba(8,8,8,0.9) !important;
      backdrop-filter: blur(10px);
    }

    main, section, div {
      background: transparent !important;
    }

    [class*="card"],
    [class*="panel"],
    [class*="content"],
    [class*="box"] {
      background: rgba(18,18,18,0.7) !important;
      backdrop-filter: blur(6px);
      border-radius: 12px !important;
      border: 1px solid rgba(255,255,255,0.06) !important;
      box-shadow: 0 8px 24px rgba(0,0,0,0.6) !important;
    }

    h1, h2, h3 {
      color: #ffffff !important;
    }

    p, span {
      color: #d0d0d0 !important;
    }

    a {
      color: #ff5a5a !important;
    }

    a:hover {
      color: #ff8080 !important;
    }

    button, .btn {
      background: #b11212 !important;
      color: #fff !important;
      border-radius: 6px !important;
      border: none !important;
    }

    input, textarea, select {
      background: rgba(25,25,25,0.8) !important;
      color: #fff !important;
      border: 1px solid rgba(255,255,255,0.1) !important;
      border-radius: 6px;
    }

    
    .leftMenuProfileSchoolName {
      color: #ff2b2b !important;
      font-weight: 800 !important;
      text-shadow: 0 0 12px rgba(255,43,43,0.6);
    }


    [class*="calendar"],
    [class*="takvim"],
    [class*="schedule"],
    .vc-calendar,
    .vc-event-calendar {
      display: none !important;
    }
  `;
  document.head.appendChild(s);


  const targetText = "TURKISH AIRLİNESSS ---- GAYIŞŞ EDİTİON";

  function fixName() {
    document
      .querySelectorAll(
        ".leftMenuProfileSchoolName.vc-font-size-large.p-w-xs.ng-binding"
      )
      .forEach(el => {
        if (el.textContent !== targetText) {
          el.textContent = targetText;
        }
      });
  }

  fixName();

  const observer = new MutationObserver(fixName);
  observer.observe(document.body, {
    childList: true,
    subtree: true
  });


  const welcome = document.createElement("div");
  welcome.id = "welcome-screen";
  welcome.innerText = "HOŞGELDİNİZ";
  document.body.appendChild(welcome);

  const welcomeStyle = document.createElement("style");
  welcomeStyle.innerHTML = `
    #welcome-screen {
      position: fixed;
      top: 50%;
      left: 110%;
      transform: translateY(-50%);
      font-size: 96px;
      font-weight: 800;
      letter-spacing: 4px;
      color: #ffffff;
      z-index: 999999;
      pointer-events: none;
      white-space: nowrap;
      text-shadow: 0 10px 40px rgba(0,0,0,0.8);
      animation: welcomeStraight 4.5s ease-in-out forwards;
    }

    @keyframes welcomeStraight {
      0% {
        left: 110%;
        opacity: 0;
      }
      20% {
        opacity: 1;
      }
      45% {
        left: 50%;
        transform: translate(-50%, -50%);
        opacity: 1;
      }
      65% {
        left: 50%;
        transform: translate(-50%, -50%);
        opacity: 1;
      }
      100% {
        left: -30%;
        transform: translateY(-50%);
        opacity: 0;
      }
    }
  `;
  document.head.appendChild(welcomeStyle);

  setTimeout(() => {
    welcome.remove();
    welcomeStyle.remove();
  }, 5000);

  console.log("OK.");
})();
