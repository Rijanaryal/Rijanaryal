from pathlib import Path

svg = r'''<svg width="1600" height="430" viewBox="0 0 1600 430" fill="none" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg" x1="0" y1="0" x2="1600" y2="430" gradientUnits="userSpaceOnUse">
      <stop stop-color="#07001A"/>
      <stop offset="0.28" stop-color="#170044"/>
      <stop offset="0.55" stop-color="#071B3D"/>
      <stop offset="0.78" stop-color="#3A064A"/>
      <stop offset="1" stop-color="#090018"/>
    </linearGradient>

    <radialGradient id="cyanGlow" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse"
      gradientTransform="translate(260 80) rotate(35) scale(420 300)">
      <stop stop-color="#00F6FF" stop-opacity=".38"/>
      <stop offset="1" stop-color="#00F6FF" stop-opacity="0"/>
    </radialGradient>

    <radialGradient id="pinkGlow" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse"
      gradientTransform="translate(1320 350) rotate(-20) scale(500 300)">
      <stop stop-color="#FF2BD6" stop-opacity=".38"/>
      <stop offset="1" stop-color="#FF2BD6" stop-opacity="0"/>
    </radialGradient>

    <linearGradient id="title" x1="420" y1="120" x2="1180" y2="230" gradientUnits="userSpaceOnUse">
      <stop stop-color="#FFFFFF"/>
      <stop offset=".35" stop-color="#6FFAFF"/>
      <stop offset=".7" stop-color="#C98CFF"/>
      <stop offset="1" stop-color="#FF5EDB"/>
    </linearGradient>

    <linearGradient id="line" x1="0" y1="0" x2="1" y2="1">
      <stop stop-color="#00F6FF"/>
      <stop offset=".5" stop-color="#8C52FF"/>
      <stop offset="1" stop-color="#FF2BD6"/>
    </linearGradient>

    <filter id="glowCyan" x="-100%" y="-100%" width="300%" height="300%">
      <feGaussianBlur stdDeviation="6" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>

    <filter id="glowPink" x="-100%" y="-100%" width="300%" height="300%">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>

    <pattern id="grid" width="55" height="55" patternUnits="userSpaceOnUse">
      <path d="M55 0H0V55" stroke="#8B7BFF" stroke-opacity=".09"/>
      <circle cx="0" cy="0" r="1.7" fill="#8B7BFF" fill-opacity=".25"/>
    </pattern>
  </defs>

  <rect width="1600" height="430" rx="28" fill="url(#bg)"/>
  <rect width="1600" height="430" rx="28" fill="url(#grid)"/>
  <rect width="1600" height="430" rx="28" fill="url(#cyanGlow)"/>
  <rect width="1600" height="430" rx="28" fill="url(#pinkGlow)"/>

  <!-- futuristic network -->
  <g stroke="url(#line)" stroke-width="2" opacity=".45">
    <path d="M0 85L180 25L330 100L470 30L620 90L790 35L940 100L1110 25L1280 95L1450 35L1600 80"/>
    <path d="M0 350L160 285L310 370L470 305L640 365L800 285L970 355L1130 300L1300 375L1460 300L1600 345"/>
    <path d="M90 0L180 150L120 300L250 430"/>
    <path d="M1500 0L1410 140L1480 275L1370 430"/>
  </g>

  <!-- floating circuit nodes -->
  <g filter="url(#glowCyan)">
    <circle cx="180" cy="25" r="5" fill="#00F6FF"/>
    <circle cx="330" cy="100" r="4" fill="#00F6FF"/>
    <circle cx="620" cy="90" r="4" fill="#00F6FF"/>
    <circle cx="1110" cy="25" r="5" fill="#00F6FF"/>
    <circle cx="1280" cy="95" r="4" fill="#00F6FF"/>
    <circle cx="160" cy="285" r="4" fill="#00F6FF"/>
    <circle cx="640" cy="365" r="5" fill="#00F6FF"/>
  </g>

  <g filter="url(#glowPink)">
    <circle cx="470" cy="30" r="4" fill="#FF2BD6"/>
    <circle cx="940" cy="100" r="5" fill="#FF2BD6"/>
    <circle cx="1450" cy="35" r="4" fill="#FF2BD6"/>
    <circle cx="1130" cy="300" r="5" fill="#FF2BD6"/>
    <circle cx="1460" cy="300" r="4" fill="#FF2BD6"/>
  </g>

  <!-- left code badge -->
  <g transform="translate(100 105)">
    <polygon points="0,35 58,0 116,35 116,105 58,140 0,105"
             fill="#0A0720" stroke="#00F6FF" stroke-width="3"/>
    <polygon points="13,42 58,15 103,42 103,98 58,125 13,98"
             fill="#111038" stroke="#8C52FF" stroke-width="2"/>
    <text x="58" y="84" text-anchor="middle"
          font-family="monospace" font-size="38" font-weight="bold"
          fill="#00F6FF">&lt;/&gt;</text>
  </g>

  <!-- right security badge -->
  <g transform="translate(1384 95)">
    <path d="M58 0L112 20V65C112 103 88 129 58 142C28 129 4 103 4 65V20L58 0Z"
          fill="#100624" stroke="#FF2BD6" stroke-width="3"/>
    <path d="M58 25L88 37V64C88 85 76 101 58 110C40 101 28 85 28 64V37L58 25Z"
          fill="#24104B" stroke="#C98CFF" stroke-width="2"/>
    <rect x="45" y="59" width="26" height="24" rx="4" fill="#00F6FF"/>
    <path d="M50 59V51C50 40 66 40 66 51V59" stroke="#00F6FF" stroke-width="5" fill="none"/>
  </g>

  <!-- central decorative bars -->
  <g opacity=".8">
    <rect x="550" y="73" width="500" height="2" fill="url(#line)"/>
    <rect x="635" y="330" width="330" height="2" fill="url(#line)"/>
    <circle cx="550" cy="74" r="4" fill="#00F6FF"/>
    <circle cx="1050" cy="74" r="4" fill="#FF2BD6"/>
  </g>

  <!-- title -->
  <text x="800" y="170" text-anchor="middle"
        font-family="Arial, Helvetica, sans-serif"
        font-size="58" font-weight="800"
        fill="url(#title)"
        filter="url(#glowCyan)">
    Hey! I'm Reejan Aryal
  </text>

  <text x="800" y="215" text-anchor="middle"
        font-family="monospace"
        font-size="21" letter-spacing="4"
        fill="#B7F9FF">
    &lt; CODE • CREATE • SECURE • INNOVATE /&gt;
  </text>

  <!-- role chips -->
  <g font-family="Arial, Helvetica, sans-serif" font-size="18" font-weight="700">
    <rect x="445" y="252" width="205" height="42" rx="21" fill="#00F6FF" fill-opacity=".10" stroke="#00F6FF"/>
    <text x="547" y="279" text-anchor="middle" fill="#6FFAFF">CYBERSECURITY</text>

    <rect x="665" y="252" width="175" height="42" rx="21" fill="#8C52FF" fill-opacity=".13" stroke="#9D72FF"/>
    <text x="752" y="279" text-anchor="middle" fill="#D7C4FF">WEB DEVELOPER</text>

    <rect x="855" y="252" width="185" height="42" rx="21" fill="#FF2BD6" fill-opacity=".11" stroke="#FF2BD6"/>
    <text x="947" y="279" text-anchor="middle" fill="#FF8BE8">TECH ENTHUSIAST</text>

    <rect x="585" y="307" width="205" height="42" rx="21" fill="#FF8A00" fill-opacity=".10" stroke="#FF9D32"/>
    <text x="687" y="334" text-anchor="middle" fill="#FFC078">SOFTWARE DEV</text>

    <rect x="805" y="307" width="210" height="42" rx="21" fill="#00C2FF" fill-opacity=".10" stroke="#00C2FF"/>
    <text x="910" y="334" text-anchor="middle" fill="#75DDFF">UI/UX EXPLORER</text>
  </g>

  <!-- bottom cyber line -->
  <path d="M350 390H1250" stroke="url(#line)" stroke-width="3" opacity=".8"/>
  <circle cx="350" cy="390" r="5" fill="#00F6FF" filter="url(#glowCyan)"/>
  <circle cx="1250" cy="390" r="5" fill="#FF2BD6" filter="url(#glowPink)"/>

  <text x="800" y="405" text-anchor="middle"
        font-family="monospace" font-size="13"
        fill="#7E8AAE" letter-spacing="3">
    NEPAL 🇳🇵  •  BUILDING THE FUTURE ONE PROJECT AT A TIME
  </text>
</svg>
'''

path = Path("/mnt/data/header.svg")
path.write_text(svg, encoding="utf-8")
print(f"Created: {path}")
