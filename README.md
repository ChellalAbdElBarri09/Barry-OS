<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Abd El Barry Chellal | Barry OS</title>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;700;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
:root{
    --primary:#0062ff;
    --primary-glow:rgba(0,98,255,.35);
    --bg:#030303;
    --card:rgba(255,255,255,.04);
    --border:rgba(255,255,255,.08);
    --white:#ffffff;
    --text:#dbe4ee;
    --muted:#94a3b8;
    --success:#10b981;
}
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    -webkit-tap-highlight-color:transparent;
}
body{
    background:var(--bg);
    color:var(--white);
    font-family:'Plus Jakarta Sans',sans-serif;
    overflow:hidden;
    height:100vh;
}

/* BACKGROUND */
.background{
    position:fixed;
    inset:0;
    z-index:-1;
    overflow:hidden;
}
.grid{
    position:absolute;
    inset:0;
    background-image:
        linear-gradient(rgba(255,255,255,.05) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.05) 1px, transparent 1px);
    background-size:42px 42px;
    opacity:.4;
}
.nebula{
    position:absolute;
    width:500px;
    height:500px;
    right:-200px;
    top:-180px;
    border-radius:50%;
    background:radial-gradient(circle, rgba(0,98,255,.25) 0%, transparent 70%);
    filter:blur(80px);
    animation:floatGlow 8s infinite alternate;
}
@keyframes floatGlow{
    from{ transform:scale(1); opacity:.4; }
    to{ transform:scale(1.2); opacity:.7; }
}

/* APP */
.app{
    max-width:480px;
    height:100vh;
    margin:auto;
    padding:34px 22px 130px;
    display:flex;
    flex-direction:column;
}

/* HEADER */
.header{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:28px;
    font-size:10px;
    font-family:'JetBrains Mono', monospace;
    color:var(--muted);
    letter-spacing:2px;
}
.status{
    display:flex;
    align-items:center;
    gap:8px;
}
.dot{
    width:6px;
    height:6px;
    border-radius:50%;
    background:var(--success);
    box-shadow:0 0 12px var(--success);
}

/* HERO */
.label{
    display:block;
    margin-bottom:8px;
    font-size:10px;
    font-weight:700;
    color:var(--primary);
    font-family:'JetBrains Mono', monospace;
    letter-spacing:4px;
}
.hero{
    margin-bottom:30px;
}
.hero h1{
    font-size:3rem;
    line-height:.95;
    font-weight:800;
    letter-spacing:-3px;
    background:linear-gradient(180deg, #fff 40%, #7b7b7b 100%);
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
}

/* CONTENT */
.pages{
    flex:1;
    overflow:auto;
    scrollbar-width:none;
}
.pages::-webkit-scrollbar{ display:none; }
.page{
    display:none;
    animation:slide .4s ease;
}
.page.active{ display:block; }
@keyframes slide{
    from{ opacity:0; transform:translateY(20px); }
    to{ opacity:1; transform:translateY(0); }
}

/* CARDS */
.card{
    background:var(--card);
    border:1px solid var(--border);
    border-radius:26px;
    padding:22px;
    margin-bottom:16px;
    backdrop-filter:blur(24px);
    cursor:pointer;
    transition:.3s;
}
.card:hover{ border-color:var(--primary); }
.card:active{ transform:scale(.98); }
.card-id{
    font-size:9px;
    color:var(--muted);
    font-family:'JetBrains Mono', monospace;
    margin-bottom:10px;
    letter-spacing:1.5px;
}
.card-title{
    font-size:20px;
    font-weight:700;
    margin-bottom:8px;
}
.card-text{
    color:var(--muted);
    font-size:13px;
    line-height:1.6;
}
.tags{
    display:flex;
    flex-wrap:wrap;
    gap:6px;
    margin-top:14px;
}
.tag{
    font-size:9px;
    color:var(--primary);
    font-family:'JetBrains Mono', monospace;
    border:1px solid rgba(0,98,255,.2);
    background:rgba(255,255,255,.03);
    border-radius:8px;
    padding:5px 10px;
}

/* NAV */
.nav{
    position:fixed;
    left:50%;
    bottom:24px;
    transform:translateX(-50%);
    width:calc(100% - 40px);
    max-width:440px;
    background:rgba(15,15,15,.9);
    border:1px solid var(--border);
    border-radius:28px;
    padding:6px;
    display:flex;
    backdrop-filter:blur(30px);
}
.indicator{
    position:absolute;
    top:6px;
    left:4px;
    width:calc(20% - 8px);
    height:calc(100% - 12px);
    background:var(--primary);
    border-radius:22px;
    box-shadow:0 0 20px var(--primary-glow);
    transition:.35s ease;
}
.nav button{
    flex:1;
    border:none;
    background:none;
    color:#4b5563;
    font-size:9px;
    font-weight:800;
    letter-spacing:1px;
    padding:16px 0;
    z-index:2;
    cursor:pointer;
}
.nav button.active{ color:#fff; }

/* MODAL */
.overlay{
    position:fixed;
    inset:0;
    background:rgba(0,0,0,.9);
    display:none;
    justify-content:center;
    align-items:center;
    padding:24px;
    backdrop-filter:blur(20px);
    z-index:100;
}
.modal{
    width:100%;
    max-width:400px;
    background:#090909;
    border:1px solid var(--border);
    border-radius:30px;
    padding:30px;
    max-height:80vh;
    overflow-y:auto;
    scrollbar-width:none;
}
.modal::-webkit-scrollbar{ display:none; }
.modal-code{
    font-size:9px;
    color:var(--primary);
    margin-bottom:12px;
    font-family:'JetBrains Mono', monospace;
}
.modal h2{ margin-bottom:14px; }
.modal p{
    color:var(--muted);
    line-height:1.7;
    font-size:14px;
}
.modal-list{
    color:var(--muted);
    font-size:13px;
    line-height:1.8;
    list-style:none;
    padding:0;
}
.modal-list li{
    padding:6px 0;
    border-bottom:1px solid var(--border);
    display:flex;
    gap:10px;
}
.modal-list li::before{
    content:"//";
    color:var(--primary);
    font-family:'JetBrains Mono', monospace;
    font-size:10px;
    flex-shrink:0;
    margin-top:2px;
}
.modal-section-title{
    font-size:10px;
    font-weight:700;
    color:var(--primary);
    font-family:'JetBrains Mono', monospace;
    letter-spacing:2px;
    margin:16px 0 8px;
}
.close{
    margin-top:24px;
    width:100%;
    border:none;
    border-radius:16px;
    background:var(--primary);
    color:#fff;
    font-weight:700;
    padding:16px;
    cursor:pointer;
}
</style>
</head>
<body>

<div class="background">
    <div class="grid"></div>
    <div class="nebula"></div>
</div>

<div class="app">

    <div class="header">
        <div class="status">
            <div class="dot"></div>
            <span>CORE_STABLE_V2.5</span>
        </div>
        <div id="clock">00:00:00</div>
    </div>

    <div class="hero">
        <span class="label">AI ENGINEER / YA FINALIST · DZ</span>
        <h1>Abd El Barry<br>Chellal.</h1>
    </div>

    <div class="pages">

        <div class="page active" id="p1">

            <div class="card" onclick="openModal('identity')">
                <div class="card-id">IDENTITY_MATRIX</div>
                <div class="card-title">Core Identity</div>
                <div class="card-text">17 y.o. · Dellys, Boumerdès, Algeria · Student. Builder. Future AI Engineer.</div>
            </div>

            <div class="card" onclick="openModal('academic')">
                <div class="card-id">EXP_ACADEMIC</div>
                <div class="card-title">Academic Matrix</div>
                <div class="card-text">Ranked 2nd in high school. Perfect 20/20 in Electrical Engineering. Mission: ENSIA.</div>
            </div>

            <div class="card" onclick="openModal('discipline')">
                <div class="card-id">SYS_DISCIPLINE</div>
                <div class="card-title">Operational Discipline</div>
                <div class="card-text">07:00 – 23:00 daily routine. Full-time studies + 40h/week part-time job.</div>
            </div>

        </div>

        <div class="page" id="p2">

            <div class="card" onclick="openModal('techstack')">
                <div class="card-id">TECH_STACK</div>
                <div class="card-title">AI & Neural Assets</div>
                <div class="card-text">43+ certifications. HarvardX, IBM, Google, MIT. Advanced AI & ML profile.</div>
                <div class="tags">
                    <div class="tag">Python</div>
                    <div class="tag">TensorFlow</div>
                    <div class="tag">PyTorch</div>
                    <div class="tag">SQL</div>
                    <div class="tag">React.js</div>
                    <div class="tag">Flask</div>
                    <div class="tag">n8n</div>
                    <div class="tag">Pandas</div>
                </div>
            </div>

            <div class="card" onclick="openModal('projects')">
                <div class="card-id">PROJECT_LOGS</div>
                <div class="card-title">Active Deployments</div>
                <div class="card-text">4 live projects built entirely on mobile. From OS ecosystems to AI chatbots.</div>
            </div>

        </div>

        <div class="page" id="p3">

            <div class="card" onclick="openModal('creative')">
                <div class="card-id">LAB_CREATIVE</div>
                <div class="card-title">Creative Lab</div>
                <div class="card-text">Author of ORACLETE (bilingual Sci-Fi). Fashion, pottery, drawing, cinema & Tarab.</div>
            </div>

            <div class="card" onclick="openModal('roadmap')">
                <div class="card-id">GLOBAL_EXPANSION</div>
                <div class="card-title">Silicon Valley Roadmap</div>
                <div class="card-text">YA Finalist. USA Exchange – Raleigh, NC · July 2026. Vision: San Jose, Silicon Valley.</div>
            </div>

        </div>

        <div class="page" id="p4">

            <div class="card" onclick="openModal('certs')">
                <div class="card-id">CERT_REGISTRY</div>
                <div class="card-title">Certification Vault</div>
                <div class="card-text">43+ international certificates from the world's top institutions.</div>
                <div class="tags">
                    <div class="tag">HarvardX</div>
                    <div class="tag">IBM</div>
                    <div class="tag">Google</div>
                    <div class="tag">MIT</div>
                </div>
            </div>

            <div class="card" onclick="openModal('skills')">
                <div class="card-id">SKILL_MATRIX</div>
                <div class="card-title">Domain Expertise</div>
                <div class="card-text">AI · ML · Deep Learning · Data Analysis · Web Dev · Automation.</div>
                <div class="tags">
                    <div class="tag">Machine Learning</div>
                    <div class="tag">Deep Learning</div>
                    <div class="tag">Data Viz</div>
                    <div class="tag">Web Scraping</div>
                    <div class="tag">Automation</div>
                </div>
            </div>

        </div>

        <div class="page" id="p5">

            <div class="card" onclick="openModal('contact')">
                <div class="card-id">CONTACT_NODE</div>
                <div class="card-title">Open Channel</div>
                <div class="card-text">Dellys, Boumerdès, Algeria · DOB 05/04/2009 · Available for global opportunities.</div>
            </div>

            <div class="card" onclick="openModal('vision')">
                <div class="card-id">LONG_TERM_VISION</div>
                <div class="card-title">10-Year Vision</div>
                <div class="card-text">AI Engineer & Entrepreneur. PhD in the USA via scholarship. Global software solutions.</div>
            </div>

        </div>

    </div>
</div>

<nav class="nav">
    <div class="indicator" id="indicator"></div>
    <button class="active" onclick="switchPage(0,'p1')">ID</button>
    <button onclick="switchPage(1,'p2')">DATA</button>
    <button onclick="switchPage(2,'p3')">LAB</button>
    <button onclick="switchPage(3,'p4')">CERTS</button>
    <button onclick="switchPage(4,'p5')">REACH</button>
</nav>

<div class="overlay" id="overlay" onclick="closeModal()">
    <div class="modal" onclick="event.stopPropagation()">
        <div class="modal-code">FILE_ACCESS // GRANTED</div>
        <h2 id="modalTitle"></h2>
        <div id="modalBody"></div>
        <button class="close" onclick="closeModal()">Return To Core</button>
    </div>
</div>

<script>

/* ── MODAL DATA ── */
const modals = {

    identity: {
        title: "Core Identity",
        html: `
            <p>Barry — a 17-year-old builder from Dellys, Boumerdès, Algeria (DOB: 05/04/2009). Currently a 2nd Year High School student in the Electrical Engineering stream.</p>
            <div class="modal-section-title">PERSONA_FLAGS</div>
            <ul class="modal-list">
                <li>Highly disciplined with a structured daily system</li>
                <li>AI enthusiast and self-taught engineer</li>
                <li>Balances seriousness with humor</li>
                <li>Driven by a rebellious spirit toward building the impossible</li>
                <li>Inspired by ACE as a role model for discipline & emotional stability</li>
            </ul>
        `
    },

    academic: {
        title: "Academic Matrix",
        html: `
            <div class="modal-section-title">CURRENT_STATUS</div>
            <ul class="modal-list">
                <li>2nd Year High School — Electrical Engineering Stream</li>
                <li>Ranked 2nd in class with high overall average</li>
                <li>Perfect score: 20/20 in Electrical Engineering</li>
            </ul>
            <div class="modal-section-title">FAVORITE_SUBJECTS</div>
            <ul class="modal-list">
                <li>English Language</li>
                <li>Physics</li>
                <li>Informatics / Computer Science</li>
                <li>Electrical Engineering</li>
            </ul>
            <div class="modal-section-title">TARGET_INSTITUTION</div>
            <ul class="modal-list">
                <li>ENSIA — National Higher School of Artificial Intelligence, Algeria</li>
            </ul>
        `
    },

    discipline: {
        title: "Operational Discipline",
        html: `
            <p>Barry operates on a strict daily structure that maximizes output across education, work, and personal development.</p>
            <div class="modal-section-title">DAILY_SCHEDULE</div>
            <ul class="modal-list">
                <li>Active hours: 07:00 AM – 11:00 PM daily</li>
                <li>Full-time high school attendance</li>
                <li>Part-time job at a supermarket — ~40 hours/week</li>
            </ul>
            <div class="modal-section-title">FITNESS_PROTOCOL</div>
            <ul class="modal-list">
                <li>Structured fitness regimen targeting a healthy weight goal</li>
                <li>Deep Recharge routine for recovery and focus reset</li>
            </ul>
        `
    },

    techstack: {
        title: "AI & Neural Assets",
        html: `
            <div class="modal-section-title">LANGUAGES</div>
            <ul class="modal-list">
                <li>Python — Advanced</li>
                <li>SQL</li>
                <li>JavaScript</li>
                <li>HTML / CSS (Tailwind)</li>
            </ul>
            <div class="modal-section-title">FRAMEWORKS_&_TOOLS</div>
            <ul class="modal-list">
                <li>TensorFlow · PyTorch — Deep Learning</li>
                <li>Pandas · Matplotlib · Seaborn — Data Analysis</li>
                <li>Flask · React.js — Web Development</li>
                <li>n8n · Web Scraping — Automation</li>
                <li>OpenAI API — AI Integration</li>
                <li>Pygame — Interactive Applications</li>
            </ul>
            <div class="modal-section-title">CERTIFICATIONS</div>
            <ul class="modal-list">
                <li>43+ international IT certificates</li>
                <li>Issuing bodies: HarvardX, IBM, Google, MIT</li>
            </ul>
        `
    },

    projects: {
        title: "Active Deployments",
        html: `
            <div class="modal-section-title">PROJECT_LOG</div>
            <ul class="modal-list">
                <li><strong style="color:#fff">BARRY OS 2.1</strong> — Comprehensive task management ecosystem built entirely on mobile</li>
                <li><strong style="color:#fff">AI Smart Calculator</strong> — Python & Pygame-based intelligent solver for visual math problems</li>
                <li><strong style="color:#fff">Data Vault</strong> — Data analytics tool for monitoring & optimizing student academic performance</li>
                <li><strong style="color:#fff">Personal AI Chatbot</strong> — Intelligent conversational agent integrated with OpenAI API</li>
            </ul>
            <div class="modal-section-title">ENVIRONMENT</div>
            <ul class="modal-list">
                <li>All projects developed on a mobile-based environment</li>
                <li>Focus on scalable, real-world utility</li>
            </ul>
        `
    },

    creative: {
        title: "Creative Lab",
        html: `
            <div class="modal-section-title">LITERARY_PROJECT</div>
            <ul class="modal-list">
                <li>Author of "ORACLETE" — a bilingual (English/Arabic) Sci-Fi Mystery novel</li>
                <li>Genre blend: speculative fiction, mystery, world-building</li>
            </ul>
            <div class="modal-section-title">HOBBIES_&_INTERESTS</div>
            <ul class="modal-list">
                <li>Fashion design & sewing</li>
                <li>Pottery / clay art</li>
                <li>Pencil drawing</li>
                <li>Analytical cinema — deep film study</li>
                <li>Vocal performance analysis — Arabic Tarab & Modern Pop</li>
            </ul>
        `
    },

    roadmap: {
        title: "Silicon Valley Roadmap",
        html: `
            <div class="modal-section-title">CURRENT_MILESTONE</div>
            <ul class="modal-list">
                <li>Youth Ambassadors Program (YA Algeria) — Finalist</li>
                <li>Exchange trip to USA scheduled — Raleigh, NC · July 2026</li>
            </ul>
            <div class="modal-section-title">CAREER_VISION</div>
            <ul class="modal-list">
                <li>AI Engineer & Entrepreneur</li>
                <li>Long-term base: San Jose, Silicon Valley</li>
                <li>Building global software solutions</li>
                <li>Pursuing a PhD in the USA via scholarship</li>
            </ul>
        `
    },

    certs: {
        title: "Certification Vault",
        html: `
            <p>43+ international IT certifications earned from the world's most prestigious academic and tech institutions.</p>
            <div class="modal-section-title">ISSUING_BODIES</div>
            <ul class="modal-list">
                <li>HarvardX — Online courses via Harvard University</li>
                <li>IBM — Professional tech & AI certifications</li>
                <li>Google — Data, cloud & technical programs</li>
                <li>MIT — Engineering & computer science courses</li>
            </ul>
            <div class="modal-section-title">COVERAGE_DOMAINS</div>
            <ul class="modal-list">
                <li>Artificial Intelligence & Machine Learning</li>
                <li>Data Engineering & Analysis</li>
                <li>Web Development</li>
                <li>Automation & Systems</li>
            </ul>
        `
    },

    skills: {
        title: "Domain Expertise",
        html: `
            <div class="modal-section-title">AI_&_DATA</div>
            <ul class="modal-list">
                <li>AI & Data Engineering</li>
                <li>Machine Learning & Deep Learning</li>
                <li>Data Analysis & Visualization (Pandas, Matplotlib, Seaborn)</li>
            </ul>
            <div class="modal-section-title">DEVELOPMENT</div>
            <ul class="modal-list">
                <li>Web Development — Flask, React.js, HTML/CSS</li>
                <li>Mobile-based Environment Development</li>
                <li>Interactive App Development (Pygame)</li>
            </ul>
            <div class="modal-section-title">AUTOMATION</div>
            <ul class="modal-list">
                <li>Workflow Automation — n8n</li>
                <li>Web Scraping & Data Extraction</li>
                <li>OpenAI API Integration</li>
            </ul>
        `
    },

    contact: {
        title: "Open Channel",
        html: `
            <div class="modal-section-title">PERSONAL_DATA</div>
            <ul class="modal-list">
                <li>Full Name: Abd El Barry Chellal</li>
                <li>Preferred Name: Barry</li>
                <li>Date of Birth: 05 / 04 / 2009</li>
                <li>Age: 17 years old</li>
                <li>Location: Dellys, Boumerdès, Algeria 🇩🇿</li>
            </ul>
            <div class="modal-section-title">STATUS</div>
            <ul class="modal-list">
                <li>Open to global internships, collaborations & opportunities</li>
                <li>Available for remote AI/ML or development projects</li>
                <li>Seeking mentors in the Silicon Valley ecosystem</li>
            </ul>
        `
    },

    vision: {
        title: "Next Chapter",
        html: `
            <div class="modal-section-title">NOW</div>
            <ul class="modal-list">
                <li>Focus on finishing high school with strong results</li>
                <li>Preparing for ENSIA admission path</li>
                <li>Taking part in opportunities like YA exchange programs</li>
            </ul>

            <div class="modal-section-title">GROWTH DIRECTION</div>
            <ul class="modal-list">
                <li>Developing skills in AI, software engineering, and systems thinking</li>
                <li>Building real projects to gain experience and depth</li>
                <li>Exploring global tech environments and communities</li>
            </ul>

            <div class="modal-section-title">LONG TERM OUTLOOK</div>
            <ul class="modal-list">
                <li>Aiming toward advanced studies in Artificial Intelligence</li>
                <li>Exploring opportunities in international tech ecosystems</li>
                <li>Building impactful software solutions over time</li>
            </ul>
        `
    }

};

/* ── CLOCK ── */
function updateClock(){
    document.getElementById("clock").innerText =
        new Date().toTimeString().split(" ")[0];
}
setInterval(updateClock, 1000);
updateClock();

/* ── NAV ── */
function switchPage(index, id){
    document.querySelectorAll(".page").forEach(p => p.classList.remove("active"));
    document.querySelectorAll(".nav button").forEach(b => b.classList.remove("active"));
    document.getElementById(id).classList.add("active");
    document.querySelectorAll(".nav button")[index].classList.add("active");
    document.getElementById("indicator").style.left = `calc(${index * 20}% + 4px)`;
    if(navigator.vibrate) navigator.vibrate(12);
}

/* ── MODAL ── */
function openModal(key){
    const data = modals[key];
    document.getElementById("modalTitle").innerText = data.title;
    document.getElementById("modalBody").innerHTML = data.html;
    document.getElementById("overlay").style.display = "flex";
}
function closeModal(){
    document.getElementById("overlay").style.display = "none";
}

</script>
</body>
</html>
