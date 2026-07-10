# -v1.0.0-git-push-origin-v.0.7
Character Model for the World Wide Web: String Matching and Searching
TEALsim – Falling Coil <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TEALsim – Falling Coil</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,Helvetica,sans-serif;
}

body{
background:#08111d;
color:white;
}

.hero{
padding:90px 20px;
text-align:center;
background:linear-gradient(135deg,#0f172a,#1e3a8a,#2563eb);
}

.hero h1{
font-size:58px;
margin-bottom:15px;
}

.hero p{
font-size:22px;
opacity:.9;
max-width:850px;
margin:auto;
}

.btn{
display:inline-block;
margin-top:35px;
padding:16px 36px;
background:#3b82f6;
color:white;
text-decoration:none;
border-radius:10px;
font-weight:bold;
transition:.3s;
}

.btn:hover{
background:#2563eb;
}

section{
max-width:1200px;
margin:auto;
padding:70px 20px;
}

.cards{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
gap:25px;
}

.card{
background:#111827;
padding:30px;
border-radius:18px;
}

.card h2{
margin-bottom:15px;
}

footer{
padding:40px;
text-align:center;
background:#111827;
color:#9ca3af;
}

code{
background:#1f2937;
padding:4px 8px;
border-radius:6px;
}
</style>

</head>

<body>

<div class="hero">

<h1>⚡ TEALsim</h1>

<p>
Interactive Electromagnetic Physics Simulations hosted securely over HTTPS using GitHub Pages and OpenWebStart.
</p>

<a class="btn" href="fallingcoil.jnlp">
Launch Falling Coil
</a>

</div>

<section>

<h2 style="margin-bottom:30px;">
Features
</h2>

<div class="cards">

<div class="card">
<h2>HTTPS Ready</h2>
<p>
Hosted entirely through GitHub Pages with secure HTTPS delivery.
</p>
</div>

<div class="card">
<h2>OpenWebStart</h2>
<p>
Compatible with modern Java Web Start replacements.
</p>
</div>

<div class="card">
<h2>Electromagnetics</h2>
<p>
Visualize magnetic induction using the Falling Coil simulation.
</p>
</div>

<div class="card">
<h2>Open Source</h2>
<p>
Organized for easy maintenance, documentation, and deployment.
</p>
</div>

</div>

</section>

<section>

<h2>
Repository Layout
</h2>

<br>

<pre><code>
fallingcoil.jnlp
lib/
java3d/
README.md
LICENSE
</code></pre>

</section>

<section>

<h2>
Launch
</h2>

<br>

<p>

Download and install OpenWebStart, then click

<b>Launch Falling Coil</b>

to start the simulation.

</p>

</section>

<footer>

© 2026 TEALsim Deployment Project

<br><br>

GitHub:
<strong>akhilsmokie3-ops</strong>

</footer>

</body>
</html>

A modern HTTPS-hosted version of the TEALsim Falling Coil Java Web Start application.

Overview

This repository hosts the resources required to launch the Falling Coil electromagnetic simulation using OpenWebStart over HTTPS.<jnlp spec="1.0+"
      codebase="https://<your-github-username>.github.io/tealsim-web"
      href="fallingcoil.jnlp">

The simulation is part of the TEAL (Technology Enabled Active Learning) physics project and demonstrates electromagnetic induction using a falling conducting coil.

Features

- HTTPS hosting via GitHub "
- OpenWebStart compatible
- Offline-capable JNLP
- Java 3D support
- Easy deployment and maintenance

Repository Structure

tealsim-web/
├── fallingcoil.jnlp
├── lib/
│   ├── TEALsim-core.jar
│   └── TEALsim-simulations.jar
├── java3d/
│   └── java3d.jnlp
├── LICENSE
└── README.md

Requirements

- Java 8 or later (recommended)
- OpenWebStart
- Java3D runtime (if required by your TEALsim version)

Installation

1. Clone the repository.

git clone https://github.com/akhilsmokie3-ops/tealsim-web.git<resources>
    <j2se version="1.4+" initial-heap-size="64m" max-heap-size="512m"/>
    <jar href="lib/TEALsim-core.jar" main="true"/>
    <jar href="lib/TEALsim-simulations.jar"/>
    <extension href="java3d/java3d.jnlp"/>
</resources>

2. Copy all required TEALsim libraries into the "lib" folder.

3. Verify the Java3D files are present.

4. Update the "codebase" attribute inside "fallingcoil.jnlp" to your GitHub Pages <?xml version="1.0" encoding="UTF-8"?>
<jnlp spec="1.0+"
      codebase="https://sim.example.com/tealsim"
      href="fallingcoil.jnlp">


codebase="https://akhilsmokie3-ops.github.io/tealsim-web"

5. Commit and push your changes.

GitHub Pages

Enable GitHub Pages:

- Repository → Settings
- Pages
- Source → Deploy from branch
- Branch → main
- Folder → / (root)

After deployment your application will be available from:

https://akhilsmokie3-ops.github.io/tealsim-web/

Launch

Open

fallingcoil.jnlp

using OpenWebStart.

The launcher starts:

teal.app.SimPlayerApp

and loads

tealsim.physics.em.FallingCoil

Updating

Replace the JAR files inside "lib/" whenever a newer TEALsim version is available.

Commit and push:

git add .
git commit -m "Update TEALsim libraries"
git push origin main

Troubleshooting

Missing JAR

Verify every file referenced by the JNLP exists.

Java3D Errors

Install the correct Java3D runtime.

Security Warnings

Ensure all JAR files are properly signed if required by your Java/OpenWebStart configuration.

License
MIT License

Copyright (c) 2026 Manu P

Permission is hereby granted, free of charge, to any person obtaining a copy
of this repository and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
TEALsim and related components are subject to their respective licenses. This repository contains only deployment configuration. Include third-party software only if its license permits redistribution.

Author

GitHub: akhilsmokie3-ops
