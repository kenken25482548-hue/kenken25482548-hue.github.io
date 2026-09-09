```html
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>KEN // GAME DEVELOPER</title>

    <meta name="description"
        content="Korawit Phangchalee — Game & Animation Student Portfolio">

    <!-- ==============================
         GOOGLE FONT
    =============================== -->

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600;700&family=Orbitron:wght@400;500;600;700;800&display=swap"
        rel="stylesheet">


    <style>

        /* =========================================
           GLOBAL
        ========================================= */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: #020308;
            color: #ffffff;

            font-family: "Kanit", sans-serif;

            overflow-x: hidden;
        }

        ::selection {
            background: #00f6ff;
            color: #000;
        }


        /* =========================================
           THREE.JS
        ========================================= */

        #webgl {
            position: fixed;

            top: 0;
            left: 0;

            width: 100%;
            height: 100%;

            z-index: 0;
        }


        /* =========================================
           FUTURE BACKGROUND
        ========================================= */

        .scanlines {

            position: fixed;

            inset: 0;

            pointer-events: none;

            z-index: 5;

            opacity: 0.08;

            background:
                repeating-linear-gradient(
                    0deg,
                    transparent 0px,
                    transparent 3px,
                    #00f6ff 4px
                );
        }


        .vignette {

            position: fixed;

            inset: 0;

            pointer-events: none;

            z-index: 4;

            background:
                radial-gradient(
                    circle at center,
                    transparent 30%,
                    rgba(0,0,0,0.75) 100%
                );
        }


        /* =========================================
           NAVIGATION
        ========================================= */

        nav {

            position: fixed;

            top: 0;
            left: 0;

            width: 100%;
            height: 75px;

            display: flex;

            align-items: center;

            justify-content: space-between;

            padding: 0 7%;

            z-index: 20;

            background:
                linear-gradient(
                    90deg,
                    rgba(2,3,8,0.85),
                    rgba(2,3,8,0.35)
                );

            backdrop-filter: blur(15px);

            border-bottom:
                1px solid rgba(0,246,255,0.15);
        }


        .logo {

            font-family: "Orbitron";

            font-weight: 800;

            font-size: 22px;

            letter-spacing: 4px;

            color: #ffffff;
        }


        .logo span {
            color: #00f6ff;

            text-shadow:
                0 0 15px #00f6ff;
        }


        .nav-status {

            display: flex;

            align-items: center;

            gap: 8px;

            font-family: "Orbitron";

            font-size: 9px;

            color: #00f6ff;

            letter-spacing: 1px;
        }


        .status-dot {

            width: 7px;
            height: 7px;

            border-radius: 50%;

            background: #00ff88;

            box-shadow:
                0 0 12px #00ff88;
        }


        .nav-links {

            display: flex;

            gap: 30px;

            list-style: none;
        }


        .nav-links a {

            font-family: "Orbitron";

            font-size: 10px;

            letter-spacing: 1px;

            color: #ffffff;

            text-decoration: none;

            opacity: 0.55;

            transition: 0.3s;
        }


        .nav-links a:hover {

            color: #00f6ff;

            opacity: 1;

            text-shadow:
                0 0 15px #00f6ff;
        }


        /* =========================================
           HERO
        ========================================= */

        .hero {

            position: relative;

            z-index: 2;

            min-height: 100vh;

            display: flex;

            align-items: center;

            padding:
                120px 10%
                80px;
        }


        .hero-content {

            max-width: 850px;
        }


        .system-label {

            display: flex;

            align-items: center;

            gap: 12px;

            margin-bottom: 25px;

            font-family: "Orbitron";

            font-size: 11px;

            letter-spacing: 3px;

            color: #00f6ff;
        }


        .system-line {

            width: 45px;

            height: 1px;

            background: #00f6ff;

            box-shadow:
                0 0 10px #00f6ff;
        }


        .hero h1 {

            font-family: "Orbitron";

            font-size:
                clamp(45px, 8vw, 105px);

            line-height: 0.95;

            letter-spacing: -3px;

            margin-bottom: 30px;
        }


        .hero h1 span {

            color: #00f6ff;

            text-shadow:

                0 0 10px rgba(0,246,255,0.8),

                0 0 40px rgba(0,246,255,0.5),

                0 0 100px rgba(0,246,255,0.2);
        }


        .hero-description {

            max-width: 700px;

            font-size: 18px;

            line-height: 2;

            color:
                rgba(255,255,255,0.65);
        }


        .hero-description strong {

            color: #ffffff;
        }


        /* =========================================
           FUTURE BUTTONS
        ========================================= */

        .buttons {

            display: flex;

            gap: 15px;

            margin-top: 35px;
        }


        .btn {

            position: relative;

            padding:
                14px 25px;

            text-decoration: none;

            font-family: "Orbitron";

            font-size: 10px;

            letter-spacing: 1px;

            transition: 0.3s;

            overflow: hidden;
        }


        .btn-primary {

            background: #00f6ff;

            color: #000;

            box-shadow:
                0 0 25px
                rgba(0,246,255,0.25);
        }


        .btn-primary:hover {

            box-shadow:
                0 0 45px
                rgba(0,246,255,0.65);

            transform:
                translateY(-3px);
        }


        .btn-outline {

            color: #00f6ff;

            border:
                1px solid
                rgba(0,246,255,0.4);

            background:
                rgba(0,246,255,0.03);
        }


        .btn-outline:hover {

            background:
                rgba(0,246,255,0.1);

            border-color:
                #00f6ff;

            transform:
                translateY(-3px);
        }


        /* =========================================
           SECTION
        ========================================= */

        section {

            position: relative;

            z-index: 2;

            min-height: 100vh;

            padding:
                130px 10%;
        }


        .section-code {

            font-family: "Orbitron";

            color: #00f6ff;

            font-size: 9px;

            letter-spacing: 3px;

            margin-bottom: 10px;
        }


        .section-title {

            font-family: "Orbitron";

            font-size:
                clamp(35px, 5vw, 65px);

            margin-bottom: 15px;

            letter-spacing: -2px;
        }


        .section-title span {

            color: #00f6ff;

            text-shadow:
                0 0 25px
                rgba(0,246,255,0.4);
        }


        .section-description {

            color:
                rgba(255,255,255,0.45);

            margin-bottom: 50px;
        }


        /* =========================================
           CARDS
        ========================================= */

        .grid {

            display: grid;

            grid-template-columns:
                repeat(2, 1fr);

            gap: 20px;
        }


        .card {

            position: relative;

            padding: 35px;

            min-height: 250px;

            background:
                linear-gradient(
                    135deg,
                    rgba(0,246,255,0.06),
                    rgba(255,255,255,0.015)
                );

            border:
                1px solid
                rgba(0,246,255,0.15);

            backdrop-filter: blur(15px);

            transition:
                0.4s;
        }


        .card::before {

            content: "";

            position: absolute;

            top: -1px;
            left: 20px;

            width: 50px;

            height: 2px;

            background: #00f6ff;

            box-shadow:
                0 0 15px #00f6ff;
        }


        .card:hover {

            transform:
                translateY(-8px);

            border-color:
                rgba(0,246,255,0.55);

            box-shadow:
                0 20px 70px
                rgba(0,0,0,0.5);
        }


        .card-number {

            font-family: "Orbitron";

            font-size: 10px;

            color: #00f6ff;

            margin-bottom: 25px;
        }


        .card h3 {

            font-size: 26px;

            margin-bottom: 15px;
        }


        .card p {

            color:
                rgba(255,255,255,0.55);

            line-height: 1.9;
        }


        /* =========================================
           SKILLS
        ========================================= */

        .skills {

            display: grid;

            grid-template-columns:
                repeat(3, 1fr);

            gap: 15px;
        }


        .skill {

            padding: 30px;

            background:
                rgba(255,255,255,0.025);

            border:
                1px solid
                rgba(255,255,255,0.08);

            transition: 0.3s;
        }


        .skill:hover {

            border-color:
                #00f6ff;

            background:
                rgba(0,246,255,0.05);

            transform:
                translateY(-5px);
        }


        .skill-icon {

            font-family: "Orbitron";

            color: #00f6ff;

            font-size: 20px;

            margin-bottom: 20px;
        }


        .skill h3 {

            margin-bottom: 8px;
        }


        .skill p {

            font-size: 13px;

            color:
                rgba(255,255,255,0.4);
        }


        /* =========================================
           PROJECT
        ========================================= */

        .project {

            position: relative;

            max-width: 1000px;

            min-height: 350px;

            padding: 50px;

            display: flex;

            align-items: center;

            overflow: hidden;

            background:

                linear-gradient(
                    120deg,
                    rgba(0,246,255,0.09),
                    rgba(5,5,15,0.6)
                );

            border:
                1px solid
                rgba(0,246,255,0.25);
        }


        .project::after {

            content: "UNITY";

            position: absolute;

            right: -20px;
            bottom: -55px;

            font-family: "Orbitron";

            font-size: 150px;

            font-weight: 800;

            color:
                rgba(0,246,255,0.025);

            pointer-events: none;
        }


        .project-info {

            max-width: 650px;

            z-index: 2;
        }


        .project-tag {

            font-family: "Orbitron";

            font-size: 9px;

            color: #00f6ff;

            letter-spacing: 2px;

            margin-bottom: 15px;
        }


        .project h3 {

            font-family: "Orbitron";

            font-size: 35px;

            margin-bottom: 20px;
        }


        .project p {

            color:
                rgba(255,255,255,0.55);

            line-height: 1.9;
        }


        /* =========================================
           FOOTER
        ========================================= */

        footer {

            position: relative;

            z-index: 2;

            padding: 40px 10%;

            border-top:
                1px solid
                rgba(0,246,255,0.1);

            display: flex;

            justify-content: space-between;

            font-family: "Orbitron";

            font-size: 9px;

            color:
                rgba(255,255,255,0.3);

            letter-spacing: 1px;
        }


        footer span {

            color: #00f6ff;
        }


        /* =========================================
           RESPONSIVE
        ========================================= */

        @media(max-width: 800px) {

            .nav-status {
                display: none;
            }

            .nav-links {
                display: none;
            }

            .hero {
                padding-left: 7%;
                padding-right: 7%;
            }

            section {
                padding-left: 7%;
                padding-right: 7%;
            }

            .grid {
                grid-template-columns: 1fr;
            }

            .skills {
                grid-template-columns: 1fr;
            }

            .project {
                padding: 30px;
            }

            footer {
                padding: 30px 7%;
            }
        }

    </style>

</head>


<body>


<!-- =========================================
     THREE.JS CANVAS
========================================= -->

<canvas id="webgl"></canvas>


<!-- =========================================
     FUTURE OVERLAY
========================================= -->

<div class="scanlines"></div>

<div class="vignette"></div>


<!-- =========================================
     NAVIGATION
========================================= -->

<nav>

    <div class="logo">
        KEN<span>//</span>
    </div>


    <div class="nav-status">

        <div class="status-dot"></div>

        SYSTEM ONLINE

    </div>


    <ul class="nav-links">

        <li>
            <a href="#home">HOME</a>
        </li>

        <li>
            <a href="#about">ABOUT</a>
        </li>

        <li>
            <a href="#skills">SKILLS</a>
        </li>

        <li>
            <a href="#projects">PROJECTS</a>
        </li>

    </ul>

</nav>


<!-- =========================================
     HERO
========================================= -->

<section class="hero" id="home">

    <div class="hero-content">


        <div class="system-label">

            <div class="system-line"></div>

            PORTFOLIO SYSTEM // 2026

        </div>


        <h1>

            I'M<br>

            <span>KEN.</span>

        </h1>


        <p class="hero-description">

            ผมชื่อ <strong>นายกรวิช แพงชาลี</strong>
            หรือเรียกว่า <strong>“เก้น”</strong>

            <br>

            นักศึกษาชั้นปีที่ 4
            สาขาเกมและแอนิเมชัน
            มหาวิทยาลัยเทคโนโลยีราชมงคลรัตนโกสินทร์

            <br><br>

            ผมสนใจด้าน
            <strong>Game Design</strong>
            และ
            <strong>Game Development</strong>
            โดยใช้
            <strong>Unity Engine</strong>
            เป็นหนึ่งในเครื่องมือหลักในการพัฒนาเกม

        </p>


        <div class="buttons">

            <a
                href="#about"
                class="btn btn-primary">

                INITIALIZE PROFILE

            </a>


            <a
                href="#projects"
                class="btn btn-outline">

                VIEW PROJECTS

            </a>

        </div>

    </div>

</section>


<!-- =========================================
     ABOUT
========================================= -->

<section id="about">

    <div class="section-code">
        // 01 — IDENTITY
    </div>


    <h2 class="section-title">

        About <span>Me</span>

    </h2>


    <p class="section-description">

        USER PROFILE // PERSONAL INFORMATION

    </p>


    <div class="grid">


        <div class="card">

            <div class="card-number">
                PROFILE_001
            </div>

            <h3>
                👤 Korawit Phangchalee
            </h3>

            <p>

                ผมชื่อ นายกรวิช แพงชาลี
                ชื่อเล่น เก้น

                <br><br>

                ปัจจุบันกำลังศึกษาอยู่ชั้นปีที่ 4
                สาขาเกมและแอนิเมชัน
                มหาวิทยาลัยเทคโนโลยีราชมงคลรัตนโกสินทร์

            </p>

        </div>


        <div class="card">

            <div class="card-number">
                PROFILE_002
            </div>

            <h3>
                🎮 Game Developer
            </h3>

            <p>

                มีความสนใจในการออกแบบเกม
                และการพัฒนาเกม 3D

                <br><br>

                สนใจการสร้าง Gameplay,
                Game Mechanics,
                ระบบภายในเกม และประสบการณ์
                ที่ผู้เล่นจะได้รับจากเกม

            </p>

        </div>


    </div>

</section>


<!-- =========================================
     SKILLS
========================================= -->

<section id="skills">

    <div class="section-code">
        // 02 — CAPABILITIES
    </div>


    <h2 class="section-title">

        My <span>Skills</span>

    </h2>


    <p class="section-description">

        DEVELOPMENT MODULES // CURRENTLY LEARNING

    </p>


    <div class="skills">


        <div class="skill">

            <div class="skill-icon">
                01
            </div>

            <h3>
                Unity
            </h3>

            <p>
                Game Engine สำหรับพัฒนาเกม
                และสร้าง Interactive Experience
            </p>

        </div>


        <div class="skill">

            <div class="skill-icon">
                02
            </div>

            <h3>
                Game Design
            </h3>

            <p>
                การออกแบบ Gameplay,
                Mechanics และประสบการณ์ผู้เล่น
            </p>

        </div>


        <div class="skill">

            <div class="skill-icon">
                03
            </div>

            <h3>
                3D Game Development
            </h3>

            <p>
                การพัฒนาเกมในสภาพแวดล้อม 3D
            </p>

        </div>


        <div class="skill">

            <div class="skill-icon">
                04
            </div>

            <h3>
                Gameplay
            </h3>

            <p>
                การออกแบบระบบและ Interaction
                ภายในเกม
            </p>

        </div>


        <div class="skill">

            <div class="skill-icon">
                05
            </div>

            <h3>
                UI / UX
            </h3>

            <p>
                การออกแบบ Interface
                และประสบการณ์การใช้งาน
            </p>

        </div>


        <div class="skill">

            <div class="skill-icon">
                06
            </div>

            <h3>
                VR Development
            </h3>

            <p>
                สนใจการพัฒนา Interactive Experience
                สำหรับ Virtual Reality
            </p>

        </div>


    </div>

</section>


<!-- =========================================
     PROJECT
========================================= -->

<section id="projects">

    <div class="section-code">
        // 03 — PROJECT DATABASE
    </div>


    <h2 class="section-title">

        Selected <span>Project</span>

    </h2>


    <p class="section-description">

        PROJECT DATABASE // GAME DEVELOPMENT

    </p>


    <div class="project">

        <div class="project-info">

            <div class="project-tag">
                PROJECT // GAME DEVELOPMENT
            </div>


            <h3>
                UNITY GAME PROJECT
            </h3>


            <p>

                โปรเจกต์สำหรับการออกแบบและพัฒนาเกม
                โดยใช้ Unity Engine

                <br><br>

                มุ่งเน้นการออกแบบ Gameplay
                ระบบภายในเกม สภาพแวดล้อม 3D
                และการสร้างประสบการณ์ที่น่าสนใจ
                สำหรับผู้เล่น

                <br><br>

                <strong>
                    STATUS // IN DEVELOPMENT
                </strong>

            </p>

        </div>

    </div>

</section>


<!-- =========================================
     FOOTER
========================================= -->

<footer>

    <div>
        KEN // GAME & ANIMATION
    </div>

    <div>
        SYSTEM STATUS :
        <span>ONLINE</span>
    </div>

</footer>


<!-- =========================================
     THREE.JS
========================================= -->

<script type="module">

import * as THREE from
"https://cdn.jsdelivr.net/npm/three@0.180.0/build/three.module.js";


/* =========================================
   SCENE
========================================= */

const scene =
    new THREE.Scene();


scene.background =
    new THREE.Color(0x020308);


scene.fog =
    new THREE.FogExp2(
        0x020308,
        0.035
    );


/* =========================================
   CAMERA
========================================= */

const camera =
    new THREE.PerspectiveCamera(
        60,
        window.innerWidth /
        window.innerHeight,
        0.1,
        100
    );


camera.position.set(
    0,
    1,
    7
);


/* =========================================
   RENDERER
========================================= */

const canvas =
    document.getElementById("webgl");


const renderer =
    new THREE.WebGLRenderer({

        canvas,

        antialias: true,

        alpha: true

    });


renderer.setPixelRatio(
    Math.min(
        window.devicePixelRatio,
        2
    )
);


renderer.setSize(
    window.innerWidth,
    window.innerHeight
);


/* =========================================
   LIGHTING
========================================= */

const ambient =
    new THREE.AmbientLight(
        0xffffff,
        0.25
    );


scene.add(ambient);


const cyanLight =
    new THREE.PointLight(
        0x00f6ff,
        35,
        20
    );


cyanLight.position.set(
    0,
    2,
    3
);


scene.add(cyanLight);


/* =========================================
   MAIN HOLOGRAM
========================================= */

const coreGeometry =
    new THREE.IcosahedronGeometry(
        1.6,
        2
    );


const coreMaterial =
    new THREE.MeshBasicMaterial({

        color: 0x00f6ff,

        wireframe: true,

        transparent: true,

        opacity: 0.5

    });


const core =
    new THREE.Mesh(
        coreGeometry,
        coreMaterial
    );


scene.add(core);


/* =========================================
   INNER OBJECT
========================================= */

const innerGeometry =
    new THREE.IcosahedronGeometry(
        0.8,
        1
    );


const innerMaterial =
    new THREE.MeshBasicMaterial({

        color: 0xffffff,

        wireframe: true,

        transparent: true,

        opacity: 0.9

    });


const inner =
    new THREE.Mesh(
        innerGeometry,
        innerMaterial
    );


scene.add(inner);


/* =========================================
   ORBIT RINGS
========================================= */

const ringMaterial =
    new THREE.MeshBasicMaterial({

        color: 0x00f6ff,

        transparent: true,

        opacity: 0.5

    });


const ringGeometry =
    new THREE.TorusGeometry(
        2.2,
        0.008,
        8,
        120
    );


const ring1 =
    new THREE.Mesh(
        ringGeometry,
        ringMaterial
    );


ring1.rotation.x =
    Math.PI / 2.5;


scene.add(ring1);


const ring2 =
    new THREE.Mesh(
        ringGeometry,
        ringMaterial
    );


ring2.rotation.y =
    Math.PI / 2;


ring2.rotation.x =
    0.4;


scene.add(ring2);


/* =========================================
   PARTICLES
========================================= */

const particleCount =
    1800;


const particlePositions =
    new Float32Array(
        particleCount * 3
    );


for (
    let i = 0;
    i < particleCount;
    i++
) {

    particlePositions[
        i * 3
    ] =
        (Math.random() - 0.5)
        * 35;


    particlePositions[
        i * 3 + 1
    ] =
        (Math.random() - 0.5)
        * 25;


    particlePositions[
        i * 3 + 2
    ] =
        (Math.random() - 0.5)
        * 30;

}


const particleGeometry =
    new THREE.BufferGeometry();


particleGeometry.setAttribute(

    "position",

    new THREE.BufferAttribute(
        particlePositions,
        3
    )

);


const particleMaterial =
    new THREE.PointsMaterial({

        color: 0x00f6ff,

        size: 0.025,

        transparent: true,

        opacity: 0.65

    });


const particles =
    new THREE.Points(
        particleGeometry,
        particleMaterial
    );


scene.add(particles);


/* =========================================
   FUTURE GRID
========================================= */

const grid =
    new THREE.GridHelper(
        30,
        40,
        0x00f6ff,
        0x00333a
    );


grid.position.y =
    -3;


grid.material.transparent =
    true;


grid.material.opacity =
    0.15;


scene.add(grid);


/* =========================================
   MOUSE
========================================= */

let mouseX = 0;

let mouseY = 0;


window.addEventListener(
    "mousemove",
    (event) => {

        mouseX =
            event.clientX /
            window.innerWidth -
            0.5;


        mouseY =
            event.clientY /
            window.innerHeight -
            0.5;

    }
);


/* =========================================
   ANIMATION
========================================= */

const clock =
    new THREE.Clock();


function animate() {

    requestAnimationFrame(
        animate
    );


    const time =
        clock.getElapsedTime();


    /* Core */

    core.rotation.x =
        time * 0.18;


    core.rotation.y =
        time * 0.25;


    core.position.y =
        Math.sin(
            time * 1.2
        ) * 0.25;


    /* Inner */

    inner.rotation.x =
        -time * 0.35;


    inner.rotation.y =
        -time * 0.5;


    inner.position.y =
        Math.sin(
            time * 1.2
        ) * 0.25;


    /* Rings */

    ring1.rotation.z =
        time * 0.35;


    ring2.rotation.z =
        -time * 0.25;


    /* Particles */

    particles.rotation.y =
        time * 0.008;


    /* Grid */

    grid.position.z =
        (time * 0.15) % 1;


    /* Camera */

    camera.position.x +=
        (
            mouseX * 1.2 -
            camera.position.x
        ) * 0.025;


    camera.position.y +=
        (
            1 -
            mouseY * 0.8 -
            camera.position.y
        ) * 0.025;


    camera.lookAt(
        0,
        0,
        0
    );


    renderer.render(
        scene,
        camera
    );

}


animate();


/* =========================================
   RESIZE
========================================= */

window.addEventListener(
    "resize",
    () => {

        camera.aspect =
            window.innerWidth /
            window.innerHeight;


        camera.updateProjectionMatrix();


        renderer.setSize(
            window.innerWidth,
            window.innerHeight
        );

    }
);

</script>

</body>
</html>
```