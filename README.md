<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Almoxarifado ETEC</title>

<!-- Fontes -->
<link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@400;700&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
  body { font-family: "Outfit", sans-serif; margin: 0; background: #f7f7f7; text-align: center; }
  header { position: fixed; top: 0; width: 100%; background: white; box-shadow: 0 2px 4px rgba(0,0,0,0.1); z-index: 1000; padding: 8px 20px; display: flex; flex-direction: column; align-items: center; }
  header h1 { font-size: 32px; font-family: "Merriweather", serif; font-weight: 700; margin: 10px 0; }
  header button { margin: 5px; padding: 5px 12px; cursor: pointer; background: none; border: none; font-size: 16px; font-family: "Merriweather", serif; font-weight: 500; color: black; transition: color 0.3s; }
  header button:hover { color: red; }
  header input { margin-left: 1px; padding: 3px 6px; border-radius: 15px; border: 0px solid #ccc; }
  main { padding-top: 105px; max-width: 1200px; margin: 0 auto; }
  .carousel { position: relative; width: 90%; max-width: 800px; aspect-ratio: 16 / 9; margin: 20px auto; overflow: hidden; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.2); }
  .carousel img { width: 100%; height: 100%; object-fit: cover; position: absolute; top: 0; left: 0; transition: opacity 1s; }
  .carousel button { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(255,255,255,0.6); border: none; padding: 10px; cursor: pointer; border-radius: 50%; font-size: 18px; }
  .carousel .prev { left: 10px; } .carousel .next { right: 10px; }
  section { padding: 40px 20px; text-align: center; }
  .inicio-texto h2 { font-family: "Merriweather", serif; font-size: 36px; margin: 0; }
  .inicio-texto h4 { font-family: "Merriweather", serif; font-size: 24px; margin: 5px 0 20px 0; font-weight: 500; }
  .inicio-texto p { font-size: 16px; max-width: 900px; margin: 0 auto 20px auto; line-height: 1.6; text-align: center; }
  .cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap: 20px; margin-top: 20px; justify-items: center; }
  .card { background: white; padding: 10px 10px 20px 10px; border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); text-align: center; transform: rotate(-1deg); transition: transform 0.3s; width: 200px; position: relative; cursor: pointer; }
  .card:hover { transform: rotate(0deg) scale(1.05); }
  .card img { width: 100%; height: 150px; object-fit: cover; border-radius: 6px; margin-bottom: 10px; }
  .card h3 { margin: 5px 0; font-size: 16px; font-weight: 600; color: black; transition: color 0.3s; }
  .card:hover h3 { color: red; }
  .tooltip { position: absolute; bottom: 120%; left: 50%; transform: translateX(-50%); background: rgba(0,0,0,0.8); color: white; padding: 6px 10px; border-radius: 6px; font-size: 13px; opacity: 0; pointer-events: none; transition: opacity 0.3s; white-space: nowrap; }
  .card:hover .tooltip { opacity: 1; }
  
  /* Formulário de cadastro */
  .form-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 15px; max-width: 800px; margin: 0 auto; background: white; padding: 20px; border-radius: 10px; box-shadow:0 4px 10px rgba(0,0,0,0.1); }
  .form-group { display: flex; flex-direction: column; }
  .form-group label { font-weight: 500; margin-bottom: 5px; text-align: left; }
  .form-group input, .form-group select { padding: 8px; border-radius: 5px; border: 1px solid #ccc; }
  .form-group.full-width { grid-column: 1 / -1; }
  .conditional { display: none; }
  button[type="submit"] { background:#0066cc; color:white; border:none; border-radius:5px; padding:10px; cursor:pointer; font-size:16px; transition:0.3s; }
  button[type="submit"]:hover { background:#005bb5; }

  /* Estilo da seção de detalhes */
  .detalhes-container { display:flex; flex-direction:column; align-items:center; max-width:800px; margin:0 auto; padding:20px; background:white; border-radius:10px; box-shadow:0 4px 10px rgba(0,0,0,0.2); }
  .detalhes-flex { display:flex; gap:20px; align-items:flex-start; width:100%; flex-wrap: wrap; }
  .detalhes-flex img { width:350px; height:420px; object-fit:cover; border-radius:8px; flex-shrink:0; }
  .detalhes-info { text-align:left; display:flex; flex-direction:column; gap:10px; font-size:16px; }
  .detalhes-container button { margin-top:20px; padding:10px 20px; background:#0066cc; color:white; border:none; border-radius:5px; cursor:pointer; }

  /* Sobre */
 .sobre-texto {
    background-color: #fff;
    padding: 40px;
    border-radius: 15px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    max-width: 900px;
    text-align: justify;
    line-height: 1.8;
    color: #333;
    font-family: 'Merriweather', serif;
}

.sobre-texto h2 {
    text-align:center;
    font-size:32px;
    margin-bottom:20px;
}
</style>
</head>
<body>

<header>
  <div style="display:flex; align-items:center; justify-content:center; gap:20px;">
    <img src="https://leonardo-energy.org.br/wp-content/uploads/2017/07/LOGO-ETEC.jpg" height="80" alt="Logo ETEC">
    <img src="https://bkpsitecpsnew.blob.core.windows.net/uploadsitecps/sites/101/2021/02/Logo.png" height="90" alt="Logo CPS">
    <h1>ALMOXARIFADO ETEC</h1>
  </div>
  <div style="display:flex; align-items:center; justify-content:center; flex-wrap: wrap; gap:10px;">
    <button onclick="showPage('inicio')">Início</button>
    <button onclick="showPage('sobre')">Sobre</button>
    <button onclick="showPage('componentes')">Componentes</button>
    <button onclick="showPage('equipamentos')">Equipamentos</button>
    <button onclick="showPage('ferramentas')">Ferramentas</button>
    <button onclick="showPage('cadastro')">Cadastro</button>
    🔍 <input type="text" id="search" placeholder="Pesquisar..." oninput="filterItems()">
  </div>
</header>

<main>
  <!-- Início -->
  <section id="inicio">
    <div class="carousel">
      <img src="imagens/COMPONENTES.png" alt="Slide 1">
      <img src="imagens/circuitos.png" alt="Slide 2" style="opacity:0;">
      <img src="imagens/automoção.png" alt="Slide 3" style="opacity:0;">
      <img src="https://blog.win-source.net/wp-content/uploads/2023/12/%E8%A7%A3%E5%86%B3%E7%94%B5%E5%AD%90%E5%85%83%E4%BB%B6%E5%B0%8F%E6%89%B9%E9%87%8F%E9%87%87%E8%B4%AD%E9%9A%BE%E9%A2%98-1_proc.jpg" alt="Slide 4" style="opacity:0;">
      <button class="prev" onclick="prevImage()">◀</button>
      <button class="next" onclick="nextImage()">▶</button>
    </div>

    <div class="inicio-texto">
      <h2>BEM VINDO AO ALMOXARIFADO DIGITAL</h2>
      <h4>DA ETEC CAROLINA CARINHATO SAMPAIO</h4>
       <p>Este site apresenta e fornece acesso rápido aos componentes, ferramentas e equipamentos disponíveis no almoxarifado da ETEC, permitindo que alunos e professores consultem, conheçam e solicitem empréstimos de forma organizada e digital.</p>
    </div>

    <div class="cards">
      <div class="card" onclick="showPage('componentes')">
        <img src="imagens/componentes.placasite.png" alt="Componentes">
        <h3>Componentes</h3>
        <p>Confira os componentes eletrônicos disponíveis para seus projetos e aulas práticas.</p>
      </div>
      <div class="card" onclick="showPage('equipamentos')">
        <img src="imagens/equipamentos.placasite.png" alt="Equipamentos">
        <h3>Equipamentos</h3>
        <p>Veja os equipamentos disponíveis para empréstimo e uso supervisionado em laboratório.</p>
      </div>
      <div class="card" onclick="showPage('ferramentas')">
        <img src="imagens/ferramentas.placasite.png" alt="Ferramentas">
        <h3>Ferramentas</h3>
        <p>Explore as ferramentas disponíveis para uso em atividades práticas e projetos.</p>
      </div>
    </div>
  </section>

  <!-- Sobre -->
  <section id="sobre" style="display:none;">
    <div class="sobre-texto">
      <h2>Sobre o Projeto</h2>
      <p>
      Esse site foi desenvolvido como parte de um Projeto de Conclusão de Curso (TCC) pelos alunos do curso técnico em Eletrônica da ETEC Carolina Carinhato Sampaio. Seu principal objetivo é oferecer uma plataforma moderna, organizada e acessível para todos que frequentam a instituição, com foco especial em alunos, professores e coordenadores do curso.
      <br><br>
      Um almoxarifado é um setor responsável pelo armazenamento, controle, organização e distribuição de materiais, componentes e equipamentos utilizados em atividades educacionais e práticas laboratoriais. No contexto do curso de Eletrônica, esse espaço é essencial para garantir que os recursos estejam sempre disponíveis e em bom estado para os projetos desenvolvidos na escola.
      <br><br>
      Pensando nisso, este site foi criado para facilitar o acesso às informações sobre os componentes eletrônicos, ferramentas e equipamentos disponíveis no almoxarifado da instituição. A plataforma permite que os usuários conheçam cada item com mais detalhes, compreendendo sua função, aplicação e disponibilidade.
      <br><br>
      Além disso, o sistema possibilita o registro de empréstimos, permitindo que alunos e professores retirem temporariamente componentes ou equipamentos para utilização em aulas práticas, projetos escolares ou atividades extracurriculares, de forma organizada e com controle eficiente de devoluções.
      <br><br>
      Com isso, o Almoxarifado Digital contribui para tornar os processos mais transparentes, estimular o uso responsável dos recursos disponíveis, apoiar projetos e atividades práticas com maior agilidade e fortalecer a interação entre alunos, professores e a coordenação do curso.
    </p>
    </div>
  </section>

  <!-- Componentes -->
  <section id="componentes" style="display:none;">
    <h2>Componentes</h2>
    <div class="cards" id="componentes-list"></div>
  </section>

  <!-- Equipamentos -->
  <section id="equipamentos" style="display:none;">
    <h2>Equipamentos</h2>
    <div class="cards" id="equipamentos-list"></div>
  </section>

  <!-- Ferramentas -->
  <section id="ferramentas" style="display:none;">
    <h2>Ferramentas</h2>
    <div class="cards" id="ferramentas-list"></div>
  </section>

  <!-- Cadastro -->
  <section id="cadastro" style="display:none;">
    <h2>Cadastro de Empréstimo</h2>
    <form id="cadastroForm" onsubmit="saveCadastro(event)" class="form-grid">
      <div class="form-group full-width">
        <label>Nome Completo</label>
        <input type="text" id="nome" required>
      </div>
      <div class="form-group">
        <label>Tipo de Usuário</label>
        <select id="tipoUsuario" onchange="toggleCamposUsuario()" required>
          <option value="">Selecione</option>
          <option value="aluno">Aluno</option>
          <option value="professor">Professor</option>
          <option value="coordenador">Coordenador</option>
          <option value="modular">Modular</option>
        </select>
      </div>
      <div class="form-group">
        <label>Email Institucional</label>
        <input type="email" id="email" required>
      </div>
      <div class="form-group conditional" id="rmDiv">
        <label>RM</label>
        <input type="text" id="rm">
      </div>
      <div class="form-group conditional" id="serieDiv">
        <label>Série</label>
        <input type="text" id="serie">
      </div>
      <div class="form-group conditional" id="cursoDiv">
        <label>Curso</label>
        <input type="text" id="curso">
      </div>
      <div class="form-group full-width">
        <label>Itens emprestados</label>
        <select id="itemEmprestado" required>
          <option value="">Selecione</option>
          <optgroup label="Componentes">
            <option value="diodo">Diodo 1N4007</option>
            <option value="led">LED 5mm Vermelho</option>
          </optgroup>
          <optgroup label="Equipamentos">
            <option value="fonte">Fonte de Alimentação</option>
            <option value="osciloscopio">Osciloscópio</option>
          </optgroup>
          <optgroup label="Ferramentas">
            <option value="ferro_solda">Ferro de Solda</option>
            <option value="chave_fenda">Chave de Fenda</option>
          </optgroup>
        </select>
      </div>
      <div class="form-group">
        <label>Data do Empréstimo</label>
        <input type="date" id="emprestimo" required>
      </div>
      <div class="form-group full-width">
        <button type="submit">Cadastrar</button>
      </div>
    </form>
  </section>

  <!-- Detalhes do Produto -->
  <section id="detalhes" style="display:none;">
    <div class="detalhes-container">
      <h2 id="detalhes-nome"></h2>
      <div class="detalhes-flex">
        <img id="detalhes-img" src="" alt="">
        <div id="detalhes-info" class="detalhes-info"></div>
      </div>
      <button onclick="showPage(lastPage)">⬅ Voltar</button>
    </div>
  </section>
</main>

<footer>© 2025 Almoxarifado ETEC - Projeto TCC</footer>

<script>
const images = document.querySelectorAll('.carousel img');
let current = 0;
setInterval(nextImage, 5000);

function showPage(pageId) {
  document.querySelectorAll('main section').forEach(s => s.style.display = 'none');
  document.getElementById(pageId).style.display = 'block';
}

function nextImage() {
  images[current].style.opacity = 0;
  current = (current + 1) % images.length;
  images[current].style.opacity = 1;
}
function prevImage() {
  images[current].style.opacity = 0;
  current = (current - 1 + images.length) % images.length;
  images[current].style.opacity = 1;
}

let lastPage = "inicio";

// Produtos
const componentes = {

  // ============================
  // COMPONENTES ELETRÔNICOS DIVERSOS
  // ============================
  "Voltímetros": { qtd: 17, voltagem:".", corrente:".", funcao:".", desc:".", img:".jpg" },
  "Multímetros": { qtd: 13, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Contadores": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Conectores BNC": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Conectores de cabo de rede": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Conectores borne": { qtd: 19, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" }, // soma dos dois relatados
  "Conectores de alimentação DC": { qtd: 9, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Conversor boost": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Conversores de voltagem": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Transformador": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Protoboards": { qtd: 8, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Fontes": { qtd: 19, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Fonte de Sol": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Fonte chaveada": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Osciladores": { qtd: 29, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Ressonadores": { qtd: 36, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Válvulas": { qtd: 27, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Válvulas de 8 pinos": { qtd: 9, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Cabeças magnéticas": { qtd: 18, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "CPUs": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Teclado de silicone": { qtd: 15, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Placas / PCBs": { qtd: 13, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Termostatos": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Cabeçote magnético": { qtd: 18, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Sistema integrado não identificado": { qtd: 600, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Motores": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Porta-fusível": { qtd: 84, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Relé de potência Schrack RP510024": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "TDA": { qtd: 100, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  

  // ============================
  // DISPLAYS E LCDs
  // ============================
  "Displays de 7 segmentos": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Display grande": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Display pequeno": { qtd: "5+", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LCD com fio": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LCD grande sem fio": { qtd: 6, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LCD pequeno sem fio": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LCD pequeno sem fio quebrado": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LCD com botão": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

  // ============================
  // BOTÕES, INTERRUPTORES E CONTROLES
  // ============================
  "Botões": { qtd: 70, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Interruptores": { qtd: 31, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Push buttons com trava": { qtd: 14, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Push buttons comuns": { qtd: 144, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Chaves alavanca": { qtd: 44, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Interruptor mestre de lâmina de canivete": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Controles RGB": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

  // ============================
  // LEDs E LÂMPADAS
  // ============================
  "LED 5mm Vermelho": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"Usado em sinalização e indicadores.", img:"https://backend.ryndackcomponentes.com.br/media/catalog/product/1/0/1090.jpg" },
  "LED 5mm Branco": { qtd: "", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"Usado em projetos eletrônicos e iluminação.", img:"imagens/led_branco10.jpg" },
  "LED 5mm Verde": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz verde.", desc:"Utilizado em projetos eletrônicos e sinalizações.", img:"https://cdn.awsli.com.br/...jpg" },
  "LED 5mm Amarelo": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz amarela.", desc:"Comum em indicadores luminosos.", img:"https://cdn.awsli.com.br/...jpg" },
  "LED 5mm Azul": { qtd: "", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz azul.", desc:"Usado em decoração e sinalização técnica.", img:"https://backend.ryndackcomponentes.com.br/...jpg" },
  "LED 10mm Verde": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz verde de alto brilho.", desc:"", img:"https://mvelectronica.s3.us-east-2.amazonaws.com/...webp" },
  "LED 10mm Amarelo": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz amarela de alto brilho.", desc:"", img:"https://http2.mlstatic.com/...webp" },
  "LED 10mm Vermelho": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz vermelha de alto brilho.", desc:"", img:"https://encrypted-tbn0.gstatic.com/...jpg" },
  "LED 10mm Branco": { qtd: "", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"", img:"imagens/led_branco10.jpg" },
  "LED 3mm Vermelho": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },
  "LED 3mm Amarelo": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },
  "LED 3mm Verde": { qtd: "", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },
  "LED 3mm Branco": { qtd: "", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"", img:"imagens/led_branco10.jpg" },
  "LED 3mm Azul": { qtd: "", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz azul.", desc:"", img:"imagens/led_branco10.jpg" },
  "LED piranha azul": { qtd: 20, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LED piranha verde": { qtd: 20, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "LED piranha vermelho": { qtd: 20, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada torpedo 42mm": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada incandescente 150W": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada LED 3W": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Ampola reed switch": { qtd: 42, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada para amplificador": { qtd: 12, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada teleslide 12V": { qtd: 8, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada LBT 36W": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Lâmpada indicadora 40mA": { qtd: 7, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },


  // ============================
  // POTENCIÔMETROS
  // ============================
  "Potenc. 250k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 220k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 470R": { qtd: 2, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 10k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 2k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 1k": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 4 ohms": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 50k": { qtd: 6, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 5k": { qtd: 5, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 10M": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 470k": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 4k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 2M": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 50 ohms": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 1M": { qtd: 7, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 100k": { qtd: 3, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 500k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 4M": { qtd: 9, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenc. 20k": { qtd: 1, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Potenciômetros duplos": { qtd: 4, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

  // ============================
  // RESISTORES
  // ============================
  "Resistor 1Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 33k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 820Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 15k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 1M2": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 5k6": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 3k3": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 1M5": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 22k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 120k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 220Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 100k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 680R": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 8k2": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 1k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 71.5k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 82k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 27Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 33Ω": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Resistor 18k": { qtd: 200, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

  // ============================
  // DIODOS
  // ============================
  "Diodo (genérico)": { qtd: null, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Diodo Zener": { qtd: "20 pacotes", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Diodo 1N914": { qtd: "4 pacotes", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

  // ============================
  // TRANSISTORES
  // ============================
  "Transistor (genérico)": { qtd: null, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Transistor NPN": { qtd: 350, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Transistor PNP": { qtd: 300, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Transistores genéricos": { qtd: 150, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Transistor de potência": { qtd: null, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

  // ============================
  // CAPACITORES, BOBINAS E COMPONENTES PASSIVOS
  // ============================
  "Carretel de bobinas": { qtd: 27, voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },
  "Bobina de indução": { qtd: "50+", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

};

const equipamentos = {
 
  "Coolers": {
    voltagem:"",
    corrente:"",
    funcao:"Resfria equipamentos eletrônicos.",
    desc:"Coolers diversos para refrigeração de circuitos.",
    img:"imagens/cooler.jpg",
    quantidade:10
  },

  "Caixas de disjuntor": {
    voltagem:"",
    corrente:"",
    funcao:"Protege e organiza disjuntores.",
    desc:"Caixas para instalação de disjuntores residenciais ou industriais.",
    img:"imagens/caixa_disjuntor.jpg",
    quantidade:3
  },

  "Fio de rede": {
    voltagem:"",
    corrente:"",
    funcao:"Transmite sinais de rede.",
    desc:"Cabo de rede para conexão Ethernet.",
    img:"imagens/fio_rede.jpg",
    quantidade:1
  },

  "Relés de estado sólido": {
    voltagem:"",
    corrente:"",
    funcao:"Comuta circuitos eletrônicos sem partes móveis.",
    desc:"Relé eletrônico de alta velocidade e longa durabilidade.",
    img:"imagens/relé_estado_solido.jpg",
    quantidade:2
  },

  "Relés": {
    voltagem:"",
    corrente:"",
    funcao:"Comuta circuitos usando sinais elétricos.",
    desc:"Relés eletromecânicos convencionais.",
    img:"imagens/relé.jpg",
    quantidade:6
  },

  "Chaves alavanca": {
    voltagem:"",
    corrente:"",
    funcao:"Liga e desliga circuitos por meio de alavanca.",
    desc:"Chaves robustas usadas em painéis e equipamentos.",
    img:"imagens/chave_alavanca.jpg",
    quantidade:44
  }
};

const ferramentas = {

  "Alicate de corte": {
    voltagem:"", corrente:"",
    funcao:"Corta fios e terminais.",
    desc:"Ferramenta de corte para eletrônica.",
    img:"imagens/alicate_corte.jpg"
  },

  "Alicate amperímetro": {
    voltagem:"", corrente:"",
    funcao:"Mede corrente elétrica.",
    desc:"Ferramenta utilizada para medições rápidas.",
    img:"imagens/alicate_amperimetro.jpg"
  },

  "Alicate rebitador": {
    voltagem:"", corrente:"",
    funcao:"Aplica rebites.",
    desc:"Usado para fixação mecânica.",
    img:"imagens/rebitador.jpg"
  },

  "Alicate Universal": {
    voltagem:"", corrente:"",
    funcao:"Aperta, corta e dobra fios.",
    desc:"Ferramenta multiuso para eletricista.",
    img:"imagens/alicate_universal.jpg"
  },

  "Alicates normais": {
    voltagem:"", corrente:"",
    funcao:"Manipula componentes e fios.",
    desc:"Alicate comum para diversas tarefas.",
    img:"imagens/alicate.jpg"
  },

  "Descapadores": {
    voltagem:"", corrente:"",
    funcao:"Remove isolamento de fios.",
    desc:"Indispensável para montagem eletrônica.",
    img:"imagens/descapador.jpg"
  },

  "Furador": {
    voltagem:"", corrente:"",
    funcao:"Fura materiais diversos.",
    desc:"Ferramenta para pequenos furos em PCB.",
    img:"imagens/furador.jpg"
  },

  "Furadores de placa": {
    voltagem:"", corrente:"",
    funcao:"Fura placas de circuito.",
    desc:"Serve para criar furos em placas de fenolite.",
    img:"imagens/furador_placa.jpg"
  },

  "Rolo de fita veda rosca": {
    voltagem:"", corrente:"",
    funcao:"Veda conexões roscadas.",
    desc:"Usado em encanamento e vedação geral.",
    img:"imagens/fita_vedarosca.jpg"
  },

  "Pinça": {
    voltagem:"", corrente:"",
    funcao:"Segura pequenos componentes.",
    desc:"Usada em SMD e eletrônica fina.",
    img:"imagens/pinca.jpg"
  },

  "Paquímetro": {
    voltagem:"", corrente:"",
    funcao:"Mede dimensões com precisão.",
    desc:"Ferramenta de medição milimétrica.",
    img:"imagens/paquimetro.jpg"
  },

  "Interruptor mestre de lâmina de canivete": {
    voltagem:"", corrente:"",
    funcao:"Liga e desliga circuitos.",
    desc:"Interruptor estilo chave de lâmina.",
    img:"imagens/interruptor_lamina.jpg"
  },

  "Ferros de solda": {
    voltagem:"", corrente:"",
    funcao:"Realiza soldagem eletrônica.",
    desc:"Ferramenta aquecida para soldar componentes.",
    img:"imagens/ferro_solda.jpg"
  },

  "Sugadores de solda": {
    voltagem:"", corrente:"",
    funcao:"Remove solda derretida.",
    desc:"Utilizado para retrabalho em placas.",
    img:"imagens/sugador.jpg"
  },

  "Apoiador de ferro de solda": {
    voltagem:"", corrente:"",
    funcao:"Suporta o ferro de solda aquecido.",
    desc:"Evita acidentes e queimaduras.",
    img:"imagens/suporte_ferro.jpg"
  },

  "Kit de ferramentas": {
    voltagem:"", corrente:"",
    funcao:"Conjunto variado de ferramentas.",
    desc:"Contém itens básicos para manutenção.",
    img:"imagens/kit_ferramentas.jpg"
  },

  "Pacote de fixador": {
    voltagem:"", corrente:"",
    funcao:"Seguro de peças e componentes.",
    desc:"Conjunto de fixadores diversos.",
    img:"imagens/fixadores.jpg"
  },

  "Kit de laboratório educacional": {
    voltagem:"", corrente:"",
    funcao:"Suporte para estudos em eletrônica.",
    desc:"Inclui ferramentas e componentes diversos.",
    img:"imagens/kit_laboratorio.jpg"
  },

  "Molas": {
    voltagem:"", corrente:"",
    funcao:"Pressão mecânica.",
    desc:"Usadas em mecanismos gerais.",
    img:"imagens/molas.jpg"
  },

  "Mini molas": {
    voltagem:"", corrente:"",
    funcao:"Retorno mecânico leve.",
    desc:"Aplicadas em peças pequenas.",
    img:"imagens/mini_molas.jpg"
  },

  "Pregos": {
    voltagem:"", corrente:"",
    funcao:"Fixação mecânica.",
    desc:"Usados para prender materiais.",
    img:"imagens/pregos.jpg"
  },

  "Terminais": {
    voltagem:"", corrente:"",
    funcao:"Conecta fios e componentes.",
    desc:"Diversos tipos de terminais elétricos.",
    img:"imagens/terminais.jpg"
  },

  "Porcas": {
    voltagem:"", corrente:"",
    funcao:"Fixação com parafusos.",
    desc:"Porcas metálicas para montagem.",
    img:"imagens/porcas.jpg"
  },

  "Parafusos": {
    voltagem:"", corrente:"",
    funcao:"Fixação e montagem.",
    desc:"Parafusos variados para uso geral.",
    img:"imagens/parafusos.jpg"
  }

};

function fillList(id, items) {
  const container = document.getElementById(id);
  container.innerHTML = '';
  Object.entries(items).forEach(([nome, info]) => {
    const div = document.createElement('div');
    div.className = 'card';
    div.innerHTML = `<h3>${nome}</h3><div class="tooltip">${info.desc}</div>`;
    div.onclick = () => showDetalhes(nome, info, id);
    container.appendChild(div);
  });
}

fillList('componentes-list', componentes);
fillList('equipamentos-list', equipamentos);
fillList('ferramentas-list', ferramentas);

function showDetalhes(nome, info, origem) {
  lastPage = origem.replace('-list', '');
  document.getElementById('detalhes-nome').textContent = nome;
  document.getElementById('detalhes-img').src = info.img;
  const infoDiv = document.getElementById('detalhes-info');
  infoDiv.innerHTML = '';
  if(info.voltagem) infoDiv.innerHTML += `<div><strong>Voltagem:</strong> ${info.voltagem}</div>`;
  if(info.corrente) infoDiv.innerHTML += `<div><strong>Corrente:</strong> ${info.corrente}</div>`;
  if(info.funcao) infoDiv.innerHTML += `<div><strong>Função:</strong> ${info.funcao}</div>`;
  if(info.desc) infoDiv.innerHTML += `<div><strong>Descrição:</strong> ${info.desc}</div>`;
  showPage('detalhes');
}

// Cadastro
function saveCadastro(event) {
  event.preventDefault();
  const nome = document.getElementById('nome').value;
  const tipo = document.getElementById('tipoUsuario').value;
  const email = document.getElementById('email').value;
  const rm = document.getElementById('rm').value;
  const serie = document.getElementById('serie').value;
  const curso = document.getElementById('curso').value;
  const item = document.getElementById('itemEmprestado').value;
  const emprestimo = document.getElementById('emprestimo').value;
  const cadastro = { nome, tipo, email, rm, serie, curso, item, emprestimo };
  let cadastros = JSON.parse(localStorage.getItem('cadastros') || '[]');
  cadastros.push(cadastro);
  localStorage.setItem('cadastros', JSON.stringify(cadastros));
  alert('Cadastro salvo com sucesso!');
  document.getElementById('cadastroForm').reset();
}

function toggleCamposUsuario() {
  const tipo = document.getElementById('tipoUsuario').value;
  const mostrar = tipo === 'aluno' || tipo === 'modular';
  document.getElementById('rmDiv').style.display = mostrar ? 'block' : 'none';
  document.getElementById('serieDiv').style.display = mostrar ? 'block' : 'none';
  document.getElementById('cursoDiv').style.display = mostrar ? 'block' : 'none';
}

// Pesquisa
function filterItems() {
  const search = document.getElementById('search').value.toLowerCase();
  ['componentes','equipamentos','ferramentas'].forEach(id => {
    const container = document.getElementById(id + '-list');
    container.querySelectorAll('.card').forEach(card => {
      card.style.display = card.textContent.toLowerCase().includes(search) ? 'block' : 'none';
    });
  });
}
</script>
</body>
</html>
