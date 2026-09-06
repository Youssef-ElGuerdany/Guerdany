from pathlib import Path

svg = r'''<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 420" role="img" aria-labelledby="title desc">
  <title id="title">Evolution of Delphi Software Development</title>
  <desc id="desc">An animated timeline showing Delphi evolving from classic desktop software into modern client server, REST, database and AI-assisted development.</desc>

  <defs>
    <linearGradient id="bg" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0%" stop-color="#080b12"/>
      <stop offset="100%" stop-color="#111827"/>
    </linearGradient>
    <linearGradient id="accent" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0%" stop-color="#ef3340"/>
      <stop offset="50%" stop-color="#ff6b6b"/>
      <stop offset="100%" stop-color="#60a5fa"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="5" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
    <pattern id="grid" width="32" height="32" patternUnits="userSpaceOnUse">
      <path d="M32 0H0V32" fill="none" stroke="#ffffff" stroke-opacity=".035"/>
    </pattern>
  </defs>

  <rect width="1200" height="420" rx="24" fill="url(#bg)"/>
  <rect x="1" y="1" width="1198" height="418" rx="23" fill="url(#grid)" stroke="#ffffff" stroke-opacity=".08"/>

  <g font-family="Segoe UI, Arial, sans-serif" text-anchor="middle">
    <text x="600" y="54" fill="#ffffff" font-size="25" font-weight="700">
      The Evolution of Software Development
    </text>
    <text x="600" y="82" fill="#94a3b8" font-size="14">
      From classic Delphi applications to modern software engineering
    </text>
  </g>

  <!-- animated timeline -->
  <path d="M120 230 C260 145 390 315 525 230 S790 145 920 230 S1060 290 1120 190"
        fill="none" stroke="#334155" stroke-width="4" stroke-linecap="round"/>
  <path d="M120 230 C260 145 390 315 525 230 S790 145 920 230 S1060 290 1120 190"
        fill="none" stroke="url(#accent)" stroke-width="4" stroke-linecap="round"
        stroke-dasharray="18 1000" filter="url(#glow)">
    <animate attributeName="stroke-dashoffset" from="0" to="-1000" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="stroke-dasharray" values="18 1000;220 800;18 1000" dur="5s" repeatCount="indefinite"/>
  </path>

  <!-- moving pulse -->
  <circle r="7" fill="#ffffff" filter="url(#glow)">
    <animateMotion dur="5s" repeatCount="indefinite"
      path="M120 230 C260 145 390 315 525 230 S790 145 920 230 S1060 290 1120 190"/>
  </circle>

  <!-- nodes -->
  <g>
    <circle cx="120" cy="230" r="31" fill="#0f172a" stroke="#ef3340" stroke-width="3"/>
    <circle cx="120" cy="230" r="8" fill="#ef3340">
      <animate attributeName="r" values="7;11;7" dur="2s" repeatCount="indefinite"/>
    </circle>

    <circle cx="360" cy="210" r="31" fill="#0f172a" stroke="#ef3340" stroke-width="3"/>
    <circle cx="360" cy="210" r="8" fill="#ef3340">
      <animate attributeName="r" values="7;11;7" dur="2s" begin=".4s" repeatCount="indefinite"/>
    </circle>

    <circle cx="600" cy="230" r="31" fill="#0f172a" stroke="#f97316" stroke-width="3"/>
    <circle cx="600" cy="230" r="8" fill="#f97316">
      <animate attributeName="r" values="7;11;7" dur="2s" begin=".8s" repeatCount="indefinite"/>
    </circle>

    <circle cx="840" cy="210" r="31" fill="#0f172a" stroke="#60a5fa" stroke-width="3"/>
    <circle cx="840" cy="210" r="8" fill="#60a5fa">
      <animate attributeName="r" values="7;11;7" dur="2s" begin="1.2s" repeatCount="indefinite"/>
    </circle>

    <circle cx="1080" cy="215" r="31" fill="#0f172a" stroke="#a78bfa" stroke-width="3"/>
    <circle cx="1080" cy="215" r="8" fill="#a78bfa">
      <animate attributeName="r" values="7;11;7" dur="2s" begin="1.6s" repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- labels -->
  <g font-family="Segoe UI, Arial, sans-serif" text-anchor="middle">
    <g fill="#ffffff" font-size="16" font-weight="700">
      <text x="120" y="292">Classic Delphi</text>
      <text x="360" y="272">Business Apps</text>
      <text x="600" y="292">Client / Server</text>
      <text x="840" y="272">REST + SQL</text>
      <text x="1080" y="292">Modern + AI</text>
    </g>
    <g fill="#94a3b8" font-size="12">
      <text x="120" y="313">Robust foundations</text>
      <text x="360" y="293">Real-world software</text>
      <text x="600" y="313">mORMot2 &amp; services</text>
      <text x="840" y="293">Connected systems</text>
      <text x="1080" y="313">Engineering today</text>
    </g>
  </g>

  <!-- Delphi code motif -->
  <g opacity=".55" font-family="Consolas, monospace" font-size="11" fill="#64748b">
    <text x="42" y="370">begin</text>
    <text x="75" y="386">  BuildReliableSoftware;</text>
    <text x="42" y="402">end.</text>
  </g>

  <g font-family="Segoe UI, Arial, sans-serif" text-anchor="middle">
    <text x="600" y="374" fill="#cbd5e1" font-size="13">
      Youssef El Guerdany • Delphi Developer • Software Engineering
    </text>
  </g>
</svg>
'''

path = Path("/mnt/data/hero-animation.svg")
path.write_text(svg, encoding="utf-8")
print(f"Created: {path}")
