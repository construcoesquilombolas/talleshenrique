

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Talles Henrique Freitas de Castro - 8ºB</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
<link href="https://cdn.jsdelivr.net/npm/remixicon/fonts/remixicon.css" rel="stylesheet">
<style>
/* BASE */
*{margin:0;padding:0;box-sizing:border-box;font-family:'Montserrat',sans-serif;scroll-behavior:smooth;}
html,body{height:100%;}
body{background:#000;color:#fff;overflow-x:hidden;}
#particles-js{position:fixed;width:100%;height:100%;z-index:-1;}

/* HEADER */
header{background:linear-gradient(90deg,#d99a00,#ffdd4d);padding:15px 20px;position:fixed;width:100%;top:0;z-index:1000;display:flex;justify-content:space-between;align-items:center;box-shadow:0 4px 20px #000;}
header h1{font-size:1.6rem;font-weight:800;color:#fff;letter-spacing:2px;animation:floatTitle 4s ease-in-out infinite alternate;margin-right:8px}
@keyframes floatTitle{0%{transform:translateY(0);}100%{transform:translateY(-6px);}}
nav{display:flex;align-items:center;gap:10px}
nav a{color:#fff;margin:0 6px;text-decoration:none;font-weight:700;position:relative;font-size:0.95rem}
nav a::after{content:"";position:absolute;bottom:-4px;left:0;height:3px;width:0;background:#fff;transition:.3s;}
nav a:hover::after{width:100%;}
#guestBtn{border:2px solid #fff;background:none;color:#fff;padding:6px 12px;border-radius:10px;cursor:pointer;transition:.3s;font-weight:700;font-size:0.95rem}
#guestBtn:hover{background:#fff;color:#000;}

/* SEÇÕES */
main{padding-top:78px}
section{padding:60px 20px 80px;text-align:center;opacity:0;transform:translateY(30px);transition:.45s;}
section.visible{opacity:1;transform:translateY(0);}
section h2{color:#ffdd4d;font-size:2rem;margin-bottom:18px;animation:titleWave 3s ease-in-out infinite alternate;}
@keyframes titleWave{0%{letter-spacing:2px;}100%{letter-spacing:6px;}}
section p{max-width:1000px;margin:auto;color:#ddd;font-size:1.05rem;line-height:1.6;}

/* BOXES */
.box-container{display:flex;flex-wrap:wrap;gap:20px;justify-content:center;margin-top:30px;padding:0 10px}
.box{background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.06);width:300px;padding:22px;border-radius:14px;backdrop-filter:blur(8px);transition:.18s;cursor:pointer;display:flex;flex-direction:column;align-items:flex-start;gap:10px}
.box:hover{transform:translateY(-6px);border-color:#ffdd4d;box-shadow:0 10px 30px #ffdd4d33;}
.box i{font-size:36px;color:#ffdd4d;margin-bottom:4px}
.box h3{color:#ffdd4d;margin-bottom:6px}
.box p{text-align:justify;color:#ccc;font-size:0.95rem}

/* FULLSCREEN PAGINATION */
#fullscreenBox{position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.96);backdrop-filter:blur(8px);z-index:6000;display:none;justify-content:center;align-items:center;padding:40px}
#fullscreenBox.active{display:flex;}
#fullWrapper{position:relative;width:94%;max-width:980px;height:82%;overflow:hidden;border-radius:12px;border:1px solid rgba(255,221,77,0.08);background:linear-gradient(180deg, rgba(0,0,0,0.35), rgba(0,0,0,0.45));padding:28px}
.page{position:absolute;width:100%;height:100%;top:0;left:100%;opacity:0;display:flex;flex-direction:column;justify-content:center;gap:18px;transition:all .18s cubic-bezier(.2,.9,.2,1);color:#fff;font-size:1.15rem;line-height:1.65;text-align:justify;padding:18px}
.page.active{left:0;opacity:1}
.page.prev{left:-100%;opacity:0}
.page.next{left:100%;opacity:0}

.page h3{color:#ffdd4d;margin-bottom:6px;font-size:1.4rem}
.page .big{font-size:1.05rem;max-height:70%;overflow:auto;padding-right:8px}

.arrow{position:absolute;bottom:22px;font-size:2.6rem;color:#ffdd4d;cursor:pointer;user-select:none;padding:10px;border-radius:8px;background:linear-gradient(180deg, rgba(255,221,77,0.08), rgba(255,221,77,0.03))}
#leftArrow{left:22px}
#rightArrow{right:22px}

/* PAGE INDICATOR */
#pager{position:absolute;bottom:28px;left:50%;transform:translateX(-50%);display:flex;gap:8px}
.pdot{width:10px;height:10px;border-radius:50%;background:rgba(255,255,255,0.12)}
.pdot.active{background:#ffdd4d}

/* VER MAIS */
#verMaisBtn{margin-top:18px;padding:10px 26px;border:none;background:linear-gradient(90deg,#d99a00,#ffdd4d);color:#000;font-weight:700;border-radius:20px;cursor:pointer;transition:.18s}
#verMaisBtn:hover{transform:scale(1.04)}
#extra{display:none;margin-top:12px;text-align:left;color:#ddd;max-width:900px;margin-left:auto;margin-right:auto}

/* QUIZ */
#quiz{margin-top:24px;padding:18px;background:#0c0c0c;border:1px solid #ffdd4d;border-radius:12px;max-width:920px;margin-left:auto;margin-right:auto}
#scoreBox{text-align:right;font-weight:800;color:#ffdd4d;margin-bottom:10px;font-size:1.05rem}
.question{margin:12px 0;font-size:1.05rem}
.options button{display:block;width:100%;margin:8px 0;padding:10px;border:none;border-radius:10px;background:#151515;color:#fff;cursor:pointer;transition:.12s;font-weight:700}
.correct{background:#1fa31f!important}
.wrong{background:#c30000!important}
#resultMsg{text-align:center;font-size:1.05rem;margin-top:12px;color:#ffdd4d}
#resetBtn{margin-top:12px;padding:8px 16px;background:#ffdd4d;color:#000;border:none;border-radius:10px;font-weight:700;cursor:pointer}

/* CONVIDADO */
#guestScreen{position:fixed;top:0;left:0;width:100%;height:100%;background:rgba(0,0,0,0.88);display:none;align-items:center;justify-content:center;flex-direction:column;z-index:7000}
#guestScreen.active{display:flex}
#guestInput{padding:10px 16px;font-size:1.05rem;border-radius:10px;border:none}
#backBtn{margin-top:12px;padding:8px 18px;border:2px solid #ffdd4d;background:none;color:#ffdd4d;border-radius:10px;cursor:pointer}

footer{margin-top:40px;padding:18px;text-align:center;background:transparent;border-top:2px solid #ffdd4d;color:#ffdd4d}

/* RESPONSIVO */
@media (max-width:720px){header h1{font-size:1.05rem} .box{width:100%} #fullWrapper{height:86%;padding:16px} .arrow{font-size:2.2rem}}
</style>
</head>
<body>
<div id="particles-js"></div>
<header>
  <h1>Talles Henrique Freitas de Castro - 8ºB</h1>
  <nav>
    <a href="#intro">INTRODUÇÃO</a>
    <a href="#conteudo">CONTEÚDO</a>
    <a href="#quiz">QUIZ</a>
  </nav>
  <button id="guestBtn">Convidado</button>
</header>

<main>
<section id="intro">
  <h2>Construções Quilombolas</h2>
  <p>Este site foi criado para ensinar com profundidade sobre as construções quilombolas — suas técnicas, significado social, organização comunitária e o legado que se mantém vivo. O objetivo é valorizar saberes ancestrais e facilitar o estudo.</p>
</section>

<section id="conteudo">
  <h2>Conteúdo Completo</h2>
  <p>As construções quilombolas representam símbolos de resistência e autonomia. Eram espaços pensados para a vida em comunidade, defesa e manutenção de tradições — tudo feito com conhecimento prático transmitido entre gerações.</p>

  <div class="box-container">
    <div class="box" data-topic="arquitetura"><i class="ri-community-line"></i><h3>Arquitetura</h3><p>Tradições de construção, plantações de casas e organização do espaço.</p></div>
    <div class="box" data-topic="sustentabilidade"><i class="ri-leaf-line"></i><h3>Sustentabilidade</h3><p>Uso de materiais locais, técnicas de conservação e integração com o ambiente.</p></div>
    <div class="box" data-topic="modernizacao"><i class="ri-magic-line"></i><h3>Modernização</h3><p>Como saberes tradicionais se encontram com técnicas modernas hoje.</p></div>
  </div>
</section>

<!-- FULLSCREEN PAGINATION -->
<div id="fullscreenBox" aria-hidden="true">
  <div id="fullWrapper" role="dialog" aria-modal="true"></div>
  <div id="leftArrow" class="arrow ri-arrow-left-s-line" title="Página anterior"></div>
  <div id="rightArrow" class="arrow ri-arrow-right-s-line" title="Próxima página"></div>
  <div id="pager"></div>
</div>

<section>
  <div style="max-width:1000px;margin:0 auto;padding:0 12px">
    <button id="verMaisBtn">Ver Mais</button>
    <div id="extra">
      <p><strong>Curiosidades sobre Construções Quilombolas</strong></p>
      <ul style="text-align:left;color:#ddd;line-height:1.7">
        <li>Muitos métodos de construção não usavam pregos — tudo era encaixado e amarrado.</li>
        <li>O posicionamento das casas e trilhas servia tanto para rotina quanto para defesa.</li>
        <li>Barro batido e taipa eram usados por durabilidade e isolamento térmico.</li>
        <li>Tetos de palha bem construídos podiam durar muitos anos quando bem mantidos.</li>
        <li>As habilidades de construção eram ensinadas desde a infância dentro das comunidades.</li>
      </ul>
    </div>
  </div>
</section>

<section id="quiz">
  <h2>Quiz - Construções Quilombolas</h2>
  <div id="scoreBox">Pontos: 0</div>
  <div id="quizContainer"></div>
  <div id="resultMsg"></div>
  <button id="resetBtn">Resetar Quiz</button>
</section>

</main>

<!-- GUEST SCREEN -->
<div id="guestScreen">
  <h2 style="color:#ffdd4d;margin-bottom:8px">Digite seu nome</h2>
  <input id="guestInput" placeholder="Seu nome">
  <button id="backBtn">Voltar</button>
</div>

<footer>© Talles Henrique Freitas de Castro - 2025</footer>

<!-- SCRIPTS -->
<script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
<script>
/* PARTICLES */
if(window.particlesJS)particlesJS("particles-js",{particles:{number:{value:70},size:{value:3},move:{speed:2},line_linked:{enable:true,distance:120,color:"#ffdd4d"}}});

/* REVEAL */
const sections=document.querySelectorAll("section");
const obs=new IntersectionObserver(e=>{e.forEach(x=>{if(x.isIntersecting)x.target.classList.add('visible');});},{threshold:.18});
sections.forEach(s=>obs.observe(s));

/* FULLSCREEN + PAGINATION LOGIC */
const boxes=document.querySelectorAll('.box');
const fullscreen=document.getElementById('fullscreenBox');
const fullWrapper=document.getElementById('fullWrapper');
const leftArrow=document.getElementById('leftArrow');
const rightArrow=document.getElementById('rightArrow');
const pager=document.getElementById('pager');

// Conteúdos para cada tópico: cada tópico tem 3 páginas (array de strings - HTML safe)
const CONTENT = {
  arquitetura:[
    {title:'Arquitetura — Página 1', text:`<div class="big">As construções quilombolas eram projetadas para atender às necessidades de vida comunitária e defesa. As plantas das moradias variavam, mas havia um raciocínio prático: espaços para dormir, cozinhar e guardar materiais, muitas vezes agrupados ao redor de áreas comuns onde a vida social acontecia. Os materiais eram locais, e a construção refletia conhecimento ambiental.</div>`},
    {title:'Arquitetura — Página 2', text:`<div class="big">Os elementos estruturais — como pilares de madeira e paredes de taipa ou barro batido — eram escolhidos por sua disponibilidade e resistência. O uso de varas e amarrações permitia construir rapidamente e reparar com facilidade. Em regiões alagadiças, algumas construções elevavam o piso para evitar problemas com água.</div>`},
    {title:'Arquitetura — Página 3', text:`<div class="big">A organização do espaço nas comunidades considerava vigilância e comunicação: trilhas, pontos de observação e o posicionamento das casas ajudavam a proteger o grupo. Hoje, estudos arquitetônicos valorizam essas soluções como práticas sustentáveis e inteligentes.</div>`}
  ],
  sustentabilidade:[
    {title:'Sustentabilidade — Página 1', text:`<div class="big">Os quilombos aproveitavam recursos locais: barro, pedra, madeira, fibras e palha. Essa economia de materiais reduzia impacto ambiental e facilitava a manutenção. Plantas medicinais e sistemas agroflorestais integravam moradia e produção de alimento.</div>`},
    {title:'Sustentabilidade — Página 2', text:`<div class="big">Técnicas como a taipa e o adobe garantiam bom isolamento térmico — calor no dia e conforto à noite. Telhados de palha, quando bem construídos, são excelentes isolantes e permitem ventilação natural, mantendo os ambientes frescos.</div>`},
    {title:'Sustentabilidade — Página 3', text:`<div class="big">A gestão comunitária dos recursos incluía saberes sobre conservação do solo, captação de água e plantio consorciado. Esses métodos mostram que a sustentabilidade não é apenas uma prática moderna, mas um conhecimento ancestral aplicado no cotidiano.</div>`}
  ],
  modernizacao:[
    {title:'Modernização — Página 1', text:`<div class="big">Hoje, muitos quilombos combinam saberes tradicionais com técnicas modernas: uso de argamassas mais resistentes, estruturas de proteção e sistemas de energia alternativa — sempre respeitando o patrimônio e a identidade cultural.</div>`},
    {title:'Modernização — Página 2', text:`<div class="big">Projetos de arquitetura social buscam adaptar moradias para melhorar conforto sem apagar a técnica tradicional. Educação e apoio técnico ajudam a conservar e melhorar as construções mantendo a memória viva.</div>`},
    {title:'Modernização — Página 3', text:`<div class="big">A modernização também abre espaço para turismo comunitário responsável, residência sustentável e iniciativas econômicas que valorizam o patrimônio cultural sem descaracterizar a comunidade.</div>`}
  ]
};

let currentTopic = null;
let currentIndex = 0;
let pages = [];

function buildPages(topic){
  fullWrapper.innerHTML = '';
  pages = CONTENT[topic] || [];
  pages.forEach((p,idx)=>{
    const el = document.createElement('div');
    el.className = 'page';
    el.setAttribute('data-idx', idx);
    el.innerHTML = `<h3>${p.title}</h3><div class="big">${p.text}</div>`;
    fullWrapper.appendChild(el);
  });
  // pager dots
  pager.innerHTML = '';
  pages.forEach((_,i)=>{const d=document.createElement('div');d.className='pdot';if(i===0)d.classList.add('active');pager.appendChild(d)});
}

function openFullscreen(topic, start=0){
  currentTopic = topic;
  buildPages(topic);
  currentIndex = start % pages.length;
  if(currentIndex<0) currentIndex = (currentIndex + pages.length)%pages.length;
  updatePages();
  fullscreen.classList.add('active');
  fullscreen.setAttribute('aria-hidden','false');
}

function closeFullscreen(){
  fullscreen.classList.remove('active');
  fullscreen.setAttribute('aria-hidden','true');
  // small cleanup
  fullWrapper.innerHTML = '';
  pager.innerHTML = '';
}

function updatePages(){
  const elems = fullWrapper.querySelectorAll('.page');
  elems.forEach(el=>{
    const idx = Number(el.dataset.idx);
    el.classList.remove('active','prev','next');
    if(idx===currentIndex) el.classList.add('active');
    else if(idx === ((currentIndex-1+pages.length)%pages.length)) el.classList.add('prev');
    else if(idx === ((currentIndex+1)%pages.length)) el.classList.add('next');
    else { /* keep off-screen */ }
  });
  // update pager
  const dots = pager.querySelectorAll('.pdot');
  dots.forEach((d,i)=> d.classList.toggle('active', i===currentIndex));
}

function nextPage(){ currentIndex = (currentIndex+1) % pages.length; updatePages(); }
function prevPage(){ currentIndex = (currentIndex-1+pages.length) % pages.length; updatePages(); }

// Box click opens fullscreen on topic
boxes.forEach(b=>{
  b.addEventListener('click', (e)=>{
    const topic = b.dataset.topic;
    openFullscreen(topic,0);
  });
});

// Arrow controls (fast transition)
rightArrow.addEventListener('click', (e)=>{ e.stopPropagation(); nextPage(); });
leftArrow.addEventListener('click', (e)=>{ e.stopPropagation(); prevPage(); });

// Close when clicking anywhere outside content (click on fullscreen closes)
fullscreen.addEventListener('click', ()=> closeFullscreen());
// But prevent clicks inside content from closing
fullWrapper.addEventListener('click', (e)=> e.stopPropagation());

// Keyboard support
document.addEventListener('keydown', (e)=>{
  if(!fullscreen.classList.contains('active')) return;
  if(e.key==='ArrowRight') nextPage();
  if(e.key==='ArrowLeft') prevPage();
  if(e.key==='Escape') closeFullscreen();
});

/* VER MAIS */
const btnVer = document.getElementById('verMaisBtn');
const extra = document.getElementById('extra');
btnVer.addEventListener('click', ()=>{
  const show = extra.style.display === 'block';
  extra.style.display = show ? 'none' : 'block';
  btnVer.textContent = show ? 'Ver Mais' : 'Ver Menos';
});

/* QUIZ */
const questions=[
  {q:"O que é uma construção quilombola?",o:["Casa ancestral de comunidades negras.","Castelo europeu.","Templo grego."],c:0},
  {q:"Quais materiais eram comuns?",o:["Barro, madeira e palha.","Aço e vidro.","Concreto armado."],c:0},
  {q:"O objetivo dos quilombos era...",o:["Resistir e viver em liberdade.","Construir cidades romanas.","Criar indústrias."],c:0}
];
let score=0,index=0;
const quizC=document.getElementById('quizContainer');
const scoreBox=document.getElementById('scoreBox');
const resultMsg=document.getElementById('resultMsg');
function loadQ(){ if(index>=questions.length){ finishQ(); return; }
  const q=questions[index];
  quizC.innerHTML = `<div class='question'>${q.q}</div><div class='options'></div>`;
  const optBox = quizC.querySelector('.options');
  q.o.forEach((opt,i)=>{
    const b = document.createElement('button'); b.textContent = opt;
    b.addEventListener('click', ()=> selectAns(i,b,q.c));
    optBox.appendChild(b);
  });
}
function selectAns(i,btn,c){ btn.classList.add(i===c? 'correct':'wrong'); score += i===c? 20 : -20; scoreBox.textContent = 'Pontos: '+score; setTimeout(()=>{ index++; loadQ(); },200); }
function finishQ(){ if(score>=500) resultMsg.textContent='INCRÍVEL! Você dominou o conteúdo!'; else if(score>=150) resultMsg.textContent='Ótimo trabalho! Continue assim!'; else if(score>=50) resultMsg.textContent='Você está no caminho! Continue estudando.'; else resultMsg.textContent='Que pena! Tente novamente.'; }
document.getElementById('resetBtn').addEventListener('click', ()=>{ score=0; index=0; scoreBox.textContent='Pontos: 0'; resultMsg.textContent=''; loadQ(); });
loadQ();

/* CONVIDADO */
const guestBtn=document.getElementById('guestBtn');
const gScreen=document.getElementById('guestScreen');
const gInput=document.getElementById('guestInput');
const gBack=document.getElementById('backBtn');
guestBtn.addEventListener('click', ()=> gScreen.classList.add('active'));
gBack.addEventListener('click', ()=>{ if(gInput.value.trim() !== '') guestBtn.textContent = gInput.value.trim(); gScreen.classList.remove('active'); gInput.value=''; });

</script>
</body>
</html>
