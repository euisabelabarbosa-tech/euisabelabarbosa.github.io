<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Almoxarifado ETEC</title>

<!-- Fontes -->
<link href="https://fonts.googleapis.com/css2?family=Merriweather:wght@400;700&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">

<style>
  body { font-family: "Outfit", sans-serif; margin: 0; background: #e2d9d9; text-align: center; }
  header { position: fixed; top: 0; width: 100%; background: rgb(253, 252, 252); box-shadow: 0 2px 4px rgba(0,0,0,0.1); z-index: 1000; padding: 8px 20px; display: flex; flex-direction: column; align-items: center; }
  header h1 { font-size: 35px; font-family: "Merriweather", serif; font-weight: 700; margin: 10px 0; }
  header button { margin: 5px; padding: 5px 12px; cursor: pointer; background: none; border: none; font-size: 16px; font-family: "Merriweather", serif; font-weight: 500; color: black; transition: color 0.3s; }
  header button:hover { color: rgb(192, 40, 40); }
  header input { margin-left: 1px; padding: 3px 6px; border-radius: 15px; border: 0px solid #ffffff; }
  main { padding-top: 105px; max-width: 1200px; margin: 0 auto; }
  .carousel { position: relative; width: 90%; max-width: 800px; aspect-ratio: 16 / 9; margin: 20px auto; overflow: hidden; border-radius: 10px; box-shadow: 0 4px 10px rgba(0,0,0,0.2); }
  .carousel img { width: 100%; height: 100%; object-fit: cover; position: absolute; top: 0; left: 0; transition: opacity 1s; }
  .carousel button { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(163, 153, 153, 0.6); border: none; padding: 10px; cursor: pointer; border-radius: 50%; font-size: 18px; }
  .carousel .prev { left: 10px; } .carousel .next { right: 10px; }
  section { padding: 40px 20px; text-align: center; }
  .inicio-texto h2 { font-family: "Merriweather", serif; font-size: 36px; margin: 0; }
  .inicio-texto h4 { font-family: "Merriweather", serif; font-size: 24px; margin: 5px 0 20px 0; font-weight: 500; }
  .inicio-texto p { font-size: 16px; max-width: 900px; margin: 0 auto 20px auto; line-height: 1.6; text-align: center; }
  .cards { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap: 20px; margin-top: 20px; justify-items: center; }
  .card { background: rgb(253, 250, 250); padding: 10px 10px 20px 10px; border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.2); text-align: center; transform: rotate(-1deg); transition: transform 0.3s; width: 200px; position: relative; cursor: pointer; }
  .card:hover { transform: rotate(0deg) scale(1.05); }
  .card img { width: 100%; height: 150px; object-fit: cover; border-radius: 6px; margin-bottom: 10px; }
  .card h3 { margin: 5px 0; font-size: 16px; font-weight: 600; color: rgb(3, 0, 0); transition: color 0.3s; }
  .card:hover h3 { color: rgb(255, 245, 245); }
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
.btn-red {
  background: red;
  color: #fff;
  border: none;
  padding: 8px 15px;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
}

.card-atrasado {
  background: #ffe5e5;
  border-left: 5px solid red;
  padding: 10px;
  margin-bottom: 10px;
  border-radius: 8px;
}

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

  /* ========================================================= */
/* ESTILO GERAL (DESKTOP)                                    */
/* ========================================================= */
.tabs {
  display: flex;
  cursor: pointer;
  justify-content: space-around;
  background-color: #f1f1f1;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  gap: 10px;
}

.tab {
  padding: 10px;
  flex-grow: 1;
  text-align: center;
  background: #fafafa;
  border-radius: 5px;
}

.product {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 15px;
}

/* ========================================================= */
/* RESPONSIVIDADE PARA CELULAR (TELAS MENORES QUE 768px)     */
/* ========================================================= */
@media (max-width: 768px) {

  /* Abas ficam empilhadas */
  .tabs {
    flex-direction: column;
  }

  /* Abas maiores e mais fáceis de clicar */
  .tab {
    padding: 15px;
    font-size: 18px;
  }

  /* Produtos ficam verticais */
  .product {
    flex-direction: column;
    text-align: center;
  }

  /* Imagens maiores e centralizadas */
  .product img {
    width: 80px;
    height: 80px;
    margin: 0 auto;
  }
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
      <img src="imagens\COMPONENTES.png" alt="Slide 1">
      <img src="imagens\circuitos.png" alt="Slide 2" style="opacity:0;">
      <img src="imagens\automoção.png" alt="Slide 3" style="opacity:0;">
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
        <img src="imagens\componentes.placasite.png" alt="Componentes">
        <h3>Componentes</h3>
        <p>Confira os componentes eletrônicos disponíveis para seus projetos e aulas práticas.</p>
      </div>
      <div class="card" onclick="showPage('equipamentos')">
        <img src="imagens\equipamentos.placasite.png" alt="Equipamentos">
        <h3>Equipamentos</h3>
        <p>Veja os equipamentos disponíveis para empréstimo e uso supervisionado em laboratório.</p>
      </div>
      <div class="card" onclick="showPage('ferramentas')">
        <img src="imagens\ferramentas.placasite.png" alt="Ferramentas">
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

    <form id="cadastroForm" class="form-grid">
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

        <!-- COMPONENTES -->
        <div class="form-group full-width">
            <label>Componentes</label>
            <select id="itemEmprestadoComponentes" required>
                <option value="">Selecione</option>
                <option value="nenhum">Nenhum empréstimo</option>
                <option value="chaves-alavanca">Chaves alavanca</option>
<option value="circuito-integrado-diversos">Circuito integrado diversos</option>
<option value="conectores-bnc">Conectores BNC</option>
<option value="conectores-borne">Conectores borne</option>
<option value="conectores-alimentacao-dc">Conectores de alimentação DC</option>
<option value="conectores-cabo-rede">Conectores de cabo de rede</option>
<option value="contadores">Contadores</option>
<option value="controles-rgb">Controles RGB</option>
<option value="conversor-boost">Conversor boost</option>
<option value="conversores-voltagem">Conversores de voltagem</option>
<option value="cpus">CPUs</option>
<option value="diode-1n914">Díodo 1N914</option>
<option value="diodo-generico">Diodo (genérico)</option>
<option value="diodo-zener">Diodo Zener</option>
<option value="display-grande">Display grande</option>
<option value="display-pequeno">Display pequeno</option>
<option value="displays-7-segmentos">Displays de 7 segmentos</option>
<option value="fonte-chaveada">Fonte chaveada</option>
<option value="fonte-de-sol">Fonte de Sol</option>
<option value="fontes">Fontes</option>
<option value="interruptor-mestre-lamina">Interruptor mestre de lâmina de canivete</option>
<option value="interruptores">Interruptores</option>
<option value="lcd-botao">LCD com botão</option>
<option value="lcd-fio">LCD com fio</option>
<option value="lcd-grande-sem-fio">LCD grande sem fio</option>
<option value="lcd-pequeno-sem-fio">LCD pequeno sem fio</option>
<option value="lcd-pequeno-sem-fio-quebrado">LCD pequeno sem fio quebrado</option>

<!-- LEDs 10mm -->
<option value="led-10mm-amarelo">LED 10mm Amarelo</option>
<option value="led-10mm-branco">LED 10mm Branco</option>
<option value="led-10mm-verde">LED 10mm Verde</option>
<option value="led-10mm-vermelho">LED 10mm Vermelho</option>

<!-- LEDs 3mm -->
<option value="led-3mm-amarelo">LED 3mm Amarelo</option>
<option value="led-3mm-azul">LED 3mm Azul</option>
<option value="led-3mm-branco">LED 3mm Branco</option>
<option value="led-3mm-verde">LED 3mm Verde</option>
<option value="led-3mm-vermelho">LED 3mm Vermelho</option>

<!-- LEDs 5mm -->
<option value="led-5mm-amarelo">LED 5mm Amarelo</option>
<option value="led-5mm-azul">LED 5mm Azul</option>
<option value="led-5mm-branco">LED 5mm Branco</option>
<option value="led-5mm-verde">LED 5mm Verde</option>
<option value="led-5mm-vermelho">LED 5mm Vermelho</option>

<
<option value="led-piranha-azul">LED piranha azul</option>
<option value="led-piranha-verde">LED piranha verde</option>
<option value="led-piranha-vermelho">LED piranha vermelho</option>

<!-- Lampadas -->
<option value="lampada-incandescente-150w">Lâmpada incandescente 150W</option>
<option value="lampada-indicadora-40ma">Lâmpada indicadora 40mA</option>
<option value="lampada-lbt-36w">Lâmpada LBT 36W</option>
<option value="lampada-led-3w">Lâmpada LED 3W</option>
<option value="lampada-para-amplificador">Lâmpada para amplificador</option>
<option value="lampada-teleslide-12v">Lâmpada teleslide 12V</option>
<option value="lampada-torpedo-42mm">Lâmpada torpedo 42mm</option>
<option value="lampadas-micro">Lâmpadas micro</option>

<option value="motores">Motores</option>
<option value="multimetros">Multímetros</option>
<option value="osciladores">Osciladores</option>
<option value="placas-pcbs">Placas / PCBs</option>
<option value="porta-fusivel">Porta-fusível</option>

<!-- Potenciômetros -->
<option value="potenc-10k">Potenc. 10k</option>
<option value="potenc-10m">Potenc. 10M</option>
<option value="potenc-100k">Potenc. 100k</option>
<option value="potenc-1k">Potenc. 1k</option>
<option value="potenc-1m">Potenc. 1M</option>
<option value="potenc-20k">Potenc. 20k</option>
<option value="potenc-220k">Potenc. 220k</option>
<option value="potenc-250k">Potenc. 250k</option>
<option value="potenc-2k">Potenc. 2k</option>
<option value="potenc-2m">Potenc. 2M</option>
<option value="potenc-4-ohms">Potenc. 4 ohms</option>
<option value="potenc-4k">Potenc. 4k</option>
<option value="potenc-470k">Potenc. 470k</option>
<option value="potenc-470r">Potenc. 470R</option>
<option value="potenc-50-ohms">Potenc. 50 ohms</option>
<option value="potenc-50k">Potenc. 50k</option>
<option value="potenc-500k">Potenc. 500k</option>
<option value="potenc-5k">Potenc. 5k</option>
<option value="potenciometros-duplos">Potenciômetros duplos</option>

<option value="protoboards">Protoboards</option>

<!-- Push buttons -->
<option value="push-buttons-com-trava">Push buttons com trava</option>
<option value="push-buttons-comuns">Push buttons comuns</option>
<option value="rele-potencia-schcrack-rp510024">Relé de potência Schrack RP510024</option>

<!-- Resistores -->
<option value="resistor-100k">Resistor 100k</option>
<option value="resistor-120k">Resistor 120k</option>
<option value="resistor-15k">Resistor 15k</option>
<option value="resistor-18k">Resistor 18k</option>
<option value="resistor-1k">Resistor 1k</option>
<option value="resistor-1m2">Resistor 1M2</option>
<option value="resistor-1m5">Resistor 1M5</option>
<option value="resistor-1-ohm">Resistor 1Ω</option>
<option value="resistor-220-ohm">Resistor 220Ω</option>
<option value="resistor-22k">Resistor 22k</option>
<option value="resistor-27-ohm">Resistor 27Ω</option>
<option value="resistor-33k">Resistor 33k</option>
<option value="resistor-33-ohm">Resistor 33Ω</option>
<option value="resistor-3k3">Resistor 3k3</option>
<option value="resistor-5k6">Resistor 5k6</option>
<option value="resistor-680r">Resistor 680R</option>
<option value="resistor-71-5k">Resistor 71.5k</option>
<option value="resistor-820-ohm">Resistor 820Ω</option>
<option value="resistor-82k">Resistor 82k</option>
<option value="resistor-8k2">Resistor 8k2</option>

<option value="ressonadores">Ressonadores</option>
<option value="ressonadores-3-pinos">Ressonadores 3 pinos</option>
<option value="sistema-integrado-nao-identificado">Sistema integrado não identificado</option>
<option value="tdas">TDA’s</option>
<option value="termostatos">Termostatos</option>
<option value="transformador">Transformador</option>

<!-- Transistores -->
<option value="transistor-bd135">Transistor BD135</option>
<option value="transistor-bd139">Transistor BD139</option>
<option value="transistor-bd140">Transistor BD140</option>
<option value="transistor-bd243c">Transistor BD243C</option>
<option value="transistor-bd433">Transistor BD433</option>
<option value="transistor-bd435">Transistor BD435</option>
<option value="transistor-bd437">Transistor BD437</option>
<option value="transistor-bf494">Transistor BF494</option>
<option value="transistor-bf495">Transistor BF495</option>
<option value="transistor-bf789">Transistor BF789</option>
<option value="transistor-bf871">Transistor BF871</option>
<option value="transistor-bf873">Transistor BF873</option>
<option value="transistor-bu150">Transistor BU150</option>
<option value="transistor-bu2030">Transistor BU2030</option>
<option value="transistor-bu208a">Transistor BU208A</option>
<option value="transistor-bu326a">Transistor BU326A</option>
<option value="transistor-bu406">Transistor BU406</option>
<option value="transistor-tip110">Transistor TIP110</option>
<option value="transistor-tip112">Transistor TIP112</option>
<option value="transistor-tip122">Transistor TIP122</option>
<option value="transistor-tip147">Transistor TIP147</option>
<option value="transistor-irfz44">Transistor IRFZ44</option>
<option value="transistor-irf740">Transistor IRF740</option>
<option value="transistor-irf9530">Transistor IRF9530</option>
<option value="transistor-buz11">Transistor BUZ11</option>
<option value="transistor-2n2218">Transistor 2N2218</option>
<option value="transistor-2n2222">Transistor 2N2222</option>
<option value="transistor-2n2222a">Transistor 2N2222A</option>
<option value="transistor-2n3055">Transistor 2N3055</option>
<option value="transistor-2n3773">Transistor 2N3773</option>
<option value="transistor-2n3904">Transistor 2N3904</option>
<option value="transistor-2n3906">Transistor 2N3906</option>
<option value="transistor-2n4918">Transistor 2N4918</option>
<option value="transistor-npn">Transistor NPN</option>
<option value="transistor-pnp">Transistor PNP</option>

<!-- Válvulas -->
<option value="valvulas-8-pinos">Válvulas de 8 pinos</option>
<option value="valvulas">Válvulas</option>

<option value="voltimetros">Voltímetros</option>

<!-- Zeners -->
<option value="zener-3v">Zeners 3V</option>
<option value="zener-6-2v">Zeners 6.2V</option>
<option value="zener-9v">Zeners 9V</option>
<option value="zener-12v">Zeners 12V</option>
<option value="zener-18v">Zeners 18V</option>

<option value="conectores-genericos">Conectores genéricos</option>
<option value="resistores-variados">Resistores variados</option>
<option value="capacitores-diversos">Capacitores diversos</option>
<option value="fusiveis">Fusíveis</option>
<option value="microchaves">Microchaves</option>

            </select>
        </div>

        <!-- ==== FERRAMENTAS ==== -->

<div class="form-group full-width">
    <label>Ferramentas</label>
    <select id="itemEmprestadoFerramentas" required>
        <option value="">Selecione</option>
        <option value="nenhum">Nenhum empréstimo</option>

        <optgroup label="Ferramentas">
            <option value="alicate-amperimetro">Alicate amperímetro</option>
            <option value="alicate-corte">Alicate de corte</option>
            <option value="alicate-rebitador">Alicate rebitador</option>
            <option value="alicate-universal">Alicate universal</option>
            <option value="alicates-normais">Alicates normais</option>
            <option value="apoio-ferro-solda">Apoiador de ferro de solda</option>
            <option value="descador">Descador</option>
            <option value="ferro-solda">Ferro de solda</option>
            <option value="fita-veda-rosca">Rolo de fita veda rosca</option>
            <option value="furador">Furador</option>
            <option value="furadores-placa">Furadores de placa</option>
            <option value="kit-ferramentas">Kit de ferramentas</option>
            <option value="kit-lab-educacional">Kit de laboratório educacional</option>
            <option value="mini-molas">Mini molas</option>
            <option value="molas">Molas</option>
            <option value="pacote-fixador">Pacote de fixador</option>
            <option value="paquimetro">Paquímetro</option>
            <option value="parafusos">Parafusos</option>
            <option value="pinca">Pinça</option>
            <option value="porcas">Porcas</option>
            <option value="pregos">Pregos</option>
            <option value="terminais">Terminais</option>
            <option value="sugador-solda">Sugador de solda</option>
        </optgroup>
    </select>
</div>

<!-- ===== EQUIPAMENTOS === -->

<div class="form-group full-width">
    <label>Equipamentos</label>
    <select id="itemEmprestadoEquipamentos" required>
        <option value="">Selecione</option>
        <option value="nenhum">Nenhum empréstimo</option>

        <optgroup label="Equipamentos">
            <option value="caixa-disjuntor">Caixa de disjuntor</option>
            <option value="cooler">Cooler</option>
            <option value="fio-rede">Fio de rede</option>
            <option value="rele">Relé</option>
            <option value="rele-estado-solido">Relé de estado sólido</option>
        </optgroup>
    </select>
        </form>
        
        <div class="form-group">
            <label>Data do Empréstimo</label>
            <input type="date" id="emprestimo" required>
        </div>

        <div class="form-group">
            <label>Data de Devolução</label>
            <input type="date" id="devolucao" readonly>
        </div>

        <div class="form-group full-width">
            <button type="submit">Cadastrar</button>
        </div>
    </form>
</section>

<!-- Devoluções Pendentes (aparecerá somente quando registros tiverem devolução <= hoje) -->
<section id="registrosAtrasados" style="display:none;">
    <h2>Devoluções Pendentes</h2>
    <div id="listaAtrasados"></div>
</section>

<!-- Página de Sucesso (mantida mas não usada; mensagem temporária será usada) -->
<section id="paginaSucesso" style="display:none; padding:40px; text-align:center;">
    <img id="imgSucesso" src="IMAGEM_AQUI" style="width:200px; margin-bottom:20px;">
    <h2 id="textoSucesso"></h2>
    <button onclick="voltarCadastro()">Voltar ao início</button>
</section>

<!-- Detalhes -->
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

<!-- Mensagem de sucesso temporária (aparece no topo) -->
<div id="mensagemSucesso" style="display:none; position:fixed; top:20px; left:50%; transform:translateX(-50%); background:#e6ffea; border:1px solid #2ecc71; padding:14px 20px; border-radius:8px; box-shadow:0 6px 18px rgba(0,0,0,0.08); z-index:9999;">
  <strong id="mensagemSucessoTexto">Cadastro realizado com sucesso!</strong>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
  // Elements
  const form = document.getElementById("cadastroForm");
  const emprestimoInput = document.getElementById("emprestimo");
  const devolucaoInput = document.getElementById("devolucao");
  const cadastroSection = document.getElementById("cadastro");
  const registrosAtrasadosSection = document.getElementById("registrosAtrasados");
  const listaAtrasados = document.getElementById("listaAtrasados");
  const mensagemBox = document.getElementById("mensagemSucesso");
  const mensagemTexto = document.getElementById("mensagemSucessoTexto");

  // Safety checks
  if (!form) {
    console.error("Form #cadastroForm não encontrado.");
    return;
  }
  if (!emprestimoInput || !devolucaoInput) {
    console.error("Inputs de data não encontrados (emprestimo/devolucao).");
  }

  // Pre-calcula a devolução (+10 dias) ao escolher data de empréstimo
  emprestimoInput.addEventListener("change", function () {
    const v = this.value;
    if (!v) {
      devolucaoInput.value = "";
      return;
    }
    const emprestimo = new Date(v + "T00:00:00");
    if (!isNaN(emprestimo)) {
      emprestimo.setDate(emprestimo.getDate() + 10);
      devolucaoInput.value = emprestimo.toISOString().split("T")[0];
    }
  });

  // Submit handler
  form.addEventListener("submit", function(e) {
    e.preventDefault();
    salvarCadastroMostrarMensagem();
  });

  // Save and show temporary message
  function salvarCadastroMostrarMensagem() {
    const nome = (document.getElementById("nome") || {}).value || "";
    const tipoUsuario = (document.getElementById("tipoUsuario") || {}).value || "";
    const email = (document.getElementById("email") || {}).value || "";
    const rm = (document.getElementById("rm") || {}).value || "";
    const serie = (document.getElementById("serie") || {}).value || "";
    const curso = (document.getElementById("curso") || {}).value || "";
    const emprestimo = (document.getElementById("emprestimo") || {}).value || "";
    const devolucao = (document.getElementById("devolucao") || {}).value || "";

    if (!nome) {
      alert("Preencha o nome.");
      return;
    }

    const cadastro = {
      nome,
      tipoUsuario,
      email,
      rm,
      serie,
      curso,
      componente: (document.getElementById("itemEmprestadoComponentes") || {}).value || "",
      ferramenta: (document.getElementById("itemEmprestadoFerramentas") || {}).value || "",
      equipamento: (document.getElementById("itemEmprestadoEquipamentos") || {}).value || "",
      emprestimo,
      devolucao,
      concluido: false,
      criadoEm: new Date().toISOString()
    };

    // salvar no localStorage
    const registros = JSON.parse(localStorage.getItem("registros")) || [];
    registros.push(cadastro);
    localStorage.setItem("registros", JSON.stringify(registros));

    // Mostrar mensagem temporária (não muda de página)
    if (mensagemBox && mensagemTexto) {
      mensagemTexto.innerText = `${nome} cadastrado com sucesso. Devolução prevista: ${devolucao || "N/A"}.`;
      mensagemBox.style.display = "block";
    }

    // limpar formulário (opcional)
    form.reset();
    devolucaoInput.value = "";

    // atualizar lista (apenas itens com devolução <= hoje serão mostrados)
    atualizarListaAtrasados();

    // após 10s esconder a mensagem e voltar à tela de cadastro (início)
    setTimeout(() => {
      if (mensagemBox) mensagemBox.style.display = "none";

      // Mostrar seção de cadastro (página inicial)
      if (cadastroSection) cadastroSection.style.display = "block";

      // rolar ao topo
      window.scrollTo({ top: 0, left: 0, behavior: "smooth" });
    }, 10000);
  }

  // Atualiza a lista "registrosAtrasados" mostrando apenas registros com devolução <= hoje
  function atualizarListaAtrasados() {
    const registros = JSON.parse(localStorage.getItem("registros")) || [];
    listaAtrasados.innerHTML = "";

    const hoje = new Date();
    hoje.setHours(0,0,0,0);

    let count = 0;
    registros.forEach((r, index) => {
      if (!r.devolucao) return;
      const dataDev = new Date(r.devolucao + "T00:00:00");
      dataDev.setHours(0,0,0,0);

      if (dataDev <= hoje && r.concluido === false) {
        const div = document.createElement("div");
        div.className = "registro-atrasado";
        div.innerHTML = `
          <p><strong>${escapeHtml(r.nome)}</strong> — Devolução: <strong>${escapeHtml(r.devolucao)}</strong></p>
          <button onclick="marcarComoDevolvido(${index})" style="background:red;color:#fff;border:none;padding:6px 10px;border-radius:6px;cursor:pointer;">Devolvido</button>
        `;
        listaAtrasados.appendChild(div);
        count++;
      }
    });

    registrosAtrasadosSection.style.display = count > 0 ? "block" : "none";
  }

  // função global para marcar como devolvido
  window.marcarComoDevolvido = function(index) {
    const registros = JSON.parse(localStorage.getItem("registros")) || [];
    if (!registros[index]) return;
    registros[index].concluido = true;
    localStorage.setItem("registros", JSON.stringify(registros));
    atualizarListaAtrasados();
  };

  // função voltar (mantida)
  window.voltarCadastro = function() {
    if (mensagemBox) mensagemBox.style.display = "none";
    if (cadastroSection) cadastroSection.style.display = "block";
    // esconder outros se houver
    if (registrosAtrasadosSection) registrosAtrasadosSection.style.display = "none";
    window.scrollTo({ top: 0, left: 0, behavior: "smooth" });
  };

  // inicial
  atualizarListaAtrasados();

  // escape para evitar XSS
  function escapeHtml(str) {
    if (!str) return "";
    return String(str)
      .replace(/&/g, "&amp;")
      .replace(/</g, "&lt;")
      .replace(/>/g, "&gt;")
      .replace(/"/g, "&quot;")
      .replace(/'/g, "&#039;");
  }
});
</script>

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
"Chaves alavanca": { qtd:"44", voltagem:"110V ou 220V)", corrente:"15A a 125V AC", funcao:"Liga e desliga circuitos por meio de alavanca.", desc:"Chaves robustas usadas em painéis e equipamentos.", img:"https://tse1.mm.bing.net/th/id/OIP.ySZU1k3j7m6iPJcUsgPfBwHaHa?rs=1&pid=ImgDetMain&o=7&rm=3",},

"circuito_integrado_diversos": { "quantidade": 200, "tensao": "5–24 V", "corrente": "100 mA – 1 A", "funcao": "Realiza funções específicas conforme o tipo de CI.", "descricao": "CIs comuns em eletrônica, incluindo amplificadores, reguladores e outros componentes integrados.", "imagem": "https://cdn.shoppub.io/cdn-cgi/image/w=1000,h=1000,q=80,f=auto/eletronicacastro/media/uploads/produtos/foto/kpizmdow/circuito-integrado.jpg" },

"Conectores BNC": { qtd: "5", voltagem:"50V–500V (sinal)", corrente:"Baixa corrente", funcao:"Conecta cabos coaxiais.", desc:"Usado em osciloscópios, câmeras, RF e sinais de instrumentação.", img:"https://cdn.shoppub.io/cdn-cgi/image/w=1000,h=1000,q=80,f=auto/oficinadosbits/media/uploads/produtos/foto/zyrcqjvu/file.png" },

"Conectores borne": { qtd: "19", voltagem:"250V", corrente:"10–16A", funcao:"Fixação segura de fios.", desc:"Conectores de parafuso para ligação elétrica firme.", img:"https://cdn.awsli.com.br/600x450/969/969921/produto/42842558/f24e731402.jpg" },

"Conectores de alimentação DC": { qtd: "9", voltagem:"12–24V", corrente:"1–5A", funcao:"Conecta fontes DC a equipamentos.", desc:"Padrão utilizado em câmeras, placas e pequenos aparelhos.", img:"https://cdn.awsli.com.br/800x800/550/550177/produto/25053809/bcb278c6ab.jpg" },

"Conectores de cabo de rede": { qtd: "3", voltagem:"44–57V (PoE)", corrente:"Até 1A", funcao:"Terminação de cabos Ethernet.", desc:"Conectores RJ45 para redes de computadores.", img:"https://static.casadoeletricistasc.com.br/public/casadoeletricista/imagens/produtos/conector-rj45-para-cabo-de-rede-1174.jpg" },

"Contadores": { qtd: "3", voltagem:"5–24V", corrente:"Baixa corrente", funcao:"Conta pulsos elétricos.", desc:"Utilizados em automação, medição e sistemas digitais.", img:"https://i.ebayimg.com/images/g/vbsAAOSwGnFnbmsR/s-l1600.webp" },

"Controles RGB": { qtd: "2", voltagem:"12V", corrente:"2–5A", funcao:"Controla faixas e LEDs RGB.", desc:"Permite ajustar cor, brilho e efeitos.", img:".jpg" },

"Conversor boost": { qtd: "1", voltagem:"Entrada 3–12V / Saída até 28V", corrente:"1–2A", funcao:"Eleva a tensão de entrada.", desc:"Usado para aumentar tensão DC mantendo portabilidade.", img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQCqBBtm3fb-NUBfI2Fb2U_bAiu4WQJToOPGA&s" },

"Conversores de voltagem": { qtd: "2", voltagem:"5–24V (varia)", corrente:"1–3A", funcao:"Converte níveis de tensão.", desc:"Módulos step-up/step-down comuns em projetos eletrônicos.", img:".jpg" },

"CPUs": { qtd: "2", voltagem:"1–5V", corrente:"Baixa a média", funcao:"Processa dados digitais.", desc:"Unidades de processamento para sistemas embarcados ou computadores.", img:".jpg" },

"Diode 1N914": { qtd: "4 pacotes", voltagem:"0.7V (queda)", corrente:"300mA", funcao:"Retifica e comuta sinais.", desc:"Diodo rápido usado em lógica e alta frequência.", img:"https://mm.digikey.com/Volume0/opasdata/d220001/medias/images/649/1N5229BFS.jpg?hidebanner=true" },

"Diodo (genérico)": { qtd: "null", voltagem:"0.7V", corrente:"100–300mA", funcao:"Conduz corrente em um sentido.", desc:"Diodos comuns para retificação simples.", img:"https://http2.mlstatic.com/D_NQ_NP_744386-MLB79109161273_092024-O.webp" },

"Diodo Zener": { qtd: "20 pacotes", voltagem:"5V–24V (varia)", corrente:"20–50mA", funcao:"Regula tensão.", desc:"Usado como referência de tensão ou proteção.", img:".jpg" },

"Display grande": { qtd: "5", voltagem:"5V", corrente:"10–50mA", funcao:"Exibe números ou texto.", desc:"Displays maiores usados em painéis e instrumentos.", img:".jpg" },

"Display pequeno": { qtd: "5+", voltagem:"5V", corrente:"5–30mA", funcao:"Exibe dados visuais.", desc:"Displays compactos para instrumentos.", img:"https://image.made-in-china.com/2f0j00WskGwtNcniqT/7-Segment-LED-Display-From-0-28-.jpg" },

"Displays de 7 segmentos": { qtd: "4", voltagem:"2–3V por segmento", corrente:"10–20mA", funcao:"Exibe números de 0 a 9.", desc:"Usados em contadores, painéis e temporizadores.", img:".jpg" },

"Fonte chaveada": { qtd: "1", voltagem:"110/220V → 5–24V", corrente:"1–5A", funcao:"Converte AC em DC estabilizado.", desc:"Fonte eficiente e leve usada em eletrônica moderna.", img:".jpg" },

"Fonte de Sol": { qtd: "1", voltagem:"6–12V", corrente:"500mA–1A", funcao:"Gera energia solar.", desc:"Painel solar pequeno para experimentos ou carregamento.", img:".jpg" },

"Fontes": { qtd: "19", voltagem:"5–24V", corrente:"500mA–5A", funcao:"Fornecem energia elétrica.", desc:"Conjunto variado de fontes DC.", img:".jpg" },

"Interruptor mestre de lâmina de canivete": { qtd: "3", voltagem:"110–250V", corrente:"5–15A", funcao:"Aciona e desliga circuitos de alta robustez.", desc:"Chave antiga de lâmina, usada em demonstrações e painéis antigos.", img:".jpg" },

"Interruptores": { qtd: "31", voltagem:"125–250V", corrente:"1–5A", funcao:"Abrem e fecham circuitos.", desc:"Interruptores variados para comandos gerais.", img:".jpg" },

"LCD com botão": { qtd: "1", voltagem:"5V", corrente:"20–60mA", funcao:"Exibe texto e permite entrada via botão.", desc:"Módulo LCD integrado a interface simples de controle.", img:".jpg" },

"LCD com fio": { qtd: "5", voltagem:"5V", corrente:"20–60mA", funcao:"Exibe informações alfanuméricas.", desc:"LCDs com cabeamento já conectado.", img:".jpg" },

"LCD grande sem fio": { qtd: "6", voltagem:"5V", corrente:"20–80mA", funcao:"Exibe texto em tamanho maior.", desc:"Painéis LCD maiores para instrumentos.", img:".jpg" },

"LCD pequeno sem fio": { qtd: "1", voltagem:"3–5V", corrente:"10–30mA", funcao:"Mostra informações básicas.", desc:"LCD compacto para dispositivos pequenos.", img:".jpg" },

"LCD pequeno sem fio quebrado": { qtd: "3", voltagem:"3–5V", corrente:"10–30mA", funcao:"Display danificado sem pleno funcionamento.", desc:"Pequenos LCDs para sucata ou reaproveitamento de peças.", img:".jpg" },

"LED 10mm Amarelo": { qtd:"20", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz amarela de alto brilho.", desc:"", img:"https://http2.mlstatic.com/D_NQ_NP_653181-MLB83382658348_042025-O-kit-5-led-amarelo-difuso-10mm.webp" },

"LED 10mm Branco": { qtd:"20", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 10mm Verde": { qtd:"15", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz verde de alto brilho.", desc:"", img:"https://mvelectronica.s3.us-east-2.amazonaws.com/...webp" },

"LED 10mm Vermelho": { qtd:"20", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz vermelha de alto brilho.", desc:"", img:"https://encrypted-tbn0.gstatic.com/...jpg" },

"LED 3mm Amarelo": { qtd:"15", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Azul": { qtd:"20", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz azul.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Branco": { qtd:"15", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Verde": { qtd:"15", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 3mm Vermelho": { qtd:"15", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"", img:"imagens/led_branco10.jpg" },

"LED 5mm Amarelo": { qtd:"10", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz amarela.", desc:"Comum em indicadores luminosos.", img:"https://cdn.awsli.com.br/...jpg" },

"LED 5mm Azul": { qtd:"10", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz azul.", desc:"Usado em decoração e sinalização técnica.", img:"https://backend.ryndackcomponentes.com.br/...jpg" },

"LED 5mm Branco": { qtd:"10", voltagem:"3V", corrente:"20mA", funcao:"Emissor de luz branca.", desc:"Usado em projetos eletrônicos e iluminação.", img:"imagens/led_branco10.jpg" },

"LED 5mm Verde": { qtd:"10", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz verde.", desc:"Utilizado em projetos eletrônicos e sinalizações.", img:"https://cdn.awsli.com.br/...jpg" },

"LED 5mm Vermelho": { qtd:"10", voltagem:"2V", corrente:"20mA", funcao:"Emissor de luz.", desc:"Usado em sinalização e indicadores.", img:"https://backend.ryndackcomponentes.com.br/media/catalog/product/1/0/1090.jpg" },

"LED piranha azul": { qtd: "20", voltagem:"3.0–3.3V", corrente:"20–30mA", funcao:"Emite luz azul de alto brilho.", desc:"LED quadrado de alta intensidade para displays e painéis.", img:".jpg" },

"LED piranha verde": { qtd: "20", voltagem:"2.0–2.2V", corrente:"20–30mA", funcao:"Emite luz verde brilhante.", desc:"LED robusto usado em iluminação e sinalização.", img:".jpg" },

"LED piranha vermelho": { qtd: "20", voltagem:"1.8–2.0V", corrente:"20–30mA", funcao:"Emite luz vermelha intensa.", desc:"Componente de indicação luminosa de alto brilho.", img:".jpg" },

"Lâmpada incandescente 150W": { qtd: "1", voltagem:"110/220V", corrente:"0.7–1.4A", funcao:"Ilumina por filamento incandescente.", desc:"Lâmpada de alta potência usada em aquecimento ou iluminação forte.", img:".jpg" },

"Lâmpada indicadora 40mA": { qtd: "7", voltagem:"12–24V", corrente:"40mA", funcao:"Sinaliza estados em painéis.", desc:"Lâmpada pequena usada como indicador luminoso.", img:".jpg" },

"Lâmpada LBT 36W": { qtd: "5", voltagem:"110/220V", corrente:"0.16–0.33A", funcao:"Iluminação fluorescente tubular.", desc:"Lâmpada tubular usada em luminárias e oficinas.", img:".jpg" },

"Lâmpada LED 3W": { qtd: "3", voltagem:"110/220V", corrente:"~30mA", funcao:"Iluminação econômica.", desc:"Lâmpada LED compacta e eficiente.", img:".jpg" },

"Lâmpada para amplificador": { qtd: "12", voltagem:"6–12V", corrente:"100–300mA", funcao:"Ilumina painéis e mostradores.", desc:"Lâmpada usada em amplificadores antigos e instrumentos.", img:".jpg" },

"Lâmpada teleslide 12V": { qtd: "8", voltagem:"12V", corrente:"100–200mA", funcao:"Iluminação de instrumentos.", desc:"Pequena lâmpada utilizada em slides, painéis e retroiluminação.", img:".jpg" },

"Lâmpada torpedo 42mm": { qtd: "5", voltagem:"12V", corrente:"150–300mA", funcao:"Ilumina painéis automotivos.", desc:"Lâmpada usada em carros e painéis de instrumentos.", img:".jpg" },

"Motores": { qtd: "2", voltagem:"3–12V", corrente:"200–500mA", funcao:"Gera movimento rotacional.", desc:"Motores DC comuns para projetos mecânicos e eletrônicos.", img:".jpg" },

"Multímetros": { qtd: "13", voltagem:"Bateria 9V", corrente:"Poucos mA", funcao:"Mede grandezas elétricas.", desc:"Instrumentos para medir tensão, corrente, resistência e mais.", img:".jpg" },

"Osciladores": { qtd: "29", voltagem:"5V", corrente:"Alguns mA", funcao:"Gera sinais de clock.", desc:"Cristais osciladores usados em circuitos digitais e microcontroladores.", img:".jpg" },

"Placas / PCBs": { qtd: "13", voltagem:"-", corrente:"-", funcao:"Montagem de circuitos.", desc:"Placas de circuito impresso para soldagem de componentes.", img:".jpg" },

"Porta-fusível": { qtd: "84", voltagem:"250V", corrente:"1–10A", funcao:"Suporta e conecta fusíveis.", desc:"Base de instalação de fusíveis de proteção.", img:".jpg" },

"Potenc. 10k": { qtd: "4", voltagem:"-", corrente:"Até 0.1A", funcao:"Ajusta tensão/nível de sinal.", desc:"Potenciômetro linear comum em controles analógicos.", img:".jpg" },
"Potenc. 10M": { qtd: "3", voltagem:"-", corrente:"Baixa corrente", funcao:"Ajuste de alta impedância.", desc:"Usado em instrumentos de medição.", img:".jpg" },
"Potenc. 100k": { qtd: "3", voltagem:"-", corrente:"Até 0.1A", funcao:"Regula níveis de sinal.", desc:"Usado em áudio e controles analógicos.", img:".jpg" },
"Potenc. 1k": { qtd: "3", voltagem:"-", corrente:"Até 0.1A", funcao:"Ajuste de baixa resistência.", desc:"Potenciômetro comum em controles simples.", img:".jpg" },
"Potenc. 1M": { qtd: "7", voltagem:"-", corrente:"Baixa corrente", funcao:"Ajuste de alta impedância.", desc:"Usado em circuitos sensíveis como amplificadores.", img:".jpg" },
"Potenc. 20k": { qtd: "1", voltagem:"-", corrente:"Até 0.1A", funcao:"Regula sinais analógicos.", desc:"Valor intermediário para áudio e instrumentação.", img:".jpg" },
"Potenc. 220k": { qtd: "4", voltagem:"-", corrente:"Até 0.1A", funcao:"Ajuste de sinais.", desc:"Usado em instrumentação e filtros.", img:".jpg" },
"Potenc. 250k": { qtd: "4", voltagem:"-", corrente:"Até 0.1A", funcao:"Controle de nível.", desc:"Comum em circuitos de áudio.", img:".jpg" },
"Potenc. 2k": { qtd: "1", voltagem:"-", corrente:"Até 0.1A", funcao:"Controle fino de resistência baixa.", desc:"Usado em ajustes específicos.", img:".jpg" },
"Potenc. 2M": { qtd: "1", voltagem:"-", corrente:"Baixa corrente", funcao:"Ajuste de alta impedância.", desc:"Utilizado em equipamentos sensíveis.", img:".jpg" },
"Potenc. 4 ohms": { qtd: "1", voltagem:"-", corrente:"Maior corrente", funcao:"Ajuste resistivo pesado.", desc:"Raro, usado em aplicações específicas.", img:".jpg" },
"Potenc. 4k": { qtd: "1", voltagem:"-", corrente:"Até 0.1A", funcao:"Ajuste intermediário.", desc:"Empregado em instrumentos analógicos.", img:".jpg" },
"Potenc. 470k": { qtd: "4", voltagem:"-", corrente:"Baixa corrente", funcao:"Controle de alto valor.", desc:"Usado em equipamentos de áudio.", img:".jpg" },
"Potenc. 470R": { qtd: "2", voltagem:"-", corrente:"Até 0.1A", funcao:"Ajuste de baixa resistência.", desc:"Empregado em regulagens finas.", img:".jpg" },
"Potenc. 50 ohms": { qtd: "1", voltagem:"-", corrente:"Alta corrente", funcao:"Ajuste de baixa resistência.", desc:"Usado em RF e cargas.", img:".jpg" },
"Potenc. 50k": { qtd: "6", voltagem:"-", corrente:"Até 0.1A", funcao:"Controle de sinais.", desc:"Comum em áudio e filtros.", img:".jpg" },
"Potenc. 500k": { qtd: "1", voltagem:"-", corrente:"Baixa corrente", funcao:"Ajuste de alto valor.", desc:"Usado em pré-amplificadores.", img:".jpg" },
"Potenc. 5k": { qtd: "5", voltagem:"-", corrente:"Até 0.1A", funcao:"Ajuste de média resistência.", desc:"Utilizado em controles de painel.", img:".jpg" },
"Potenciômetros duplos": { qtd: "4", voltagem:"-", corrente:"Até 0.1A", funcao:"Controla dois canais ao mesmo tempo.", desc:"Usados em estéreo e ajustes simultâneos.", img:".jpg" },
"Protoboards": { qtd: "8", voltagem:"5–12V", corrente:"Até 1A", funcao:"Monta circuitos sem solda.", desc:"Placas de teste reutilizáveis para prototipagem.", img:".jpg" },
"Push buttons com trava": { qtd: "14", voltagem:"125–250V", corrente:"1–3A", funcao:"Liga/desliga com trava mecânica.", desc:"Interruptores momentâneos que ficam travados ao pressionar.", img:".jpg" },
"Push buttons comuns": { qtd: "144", voltagem:"5–24V", corrente:"50–200mA", funcao:"Acionamento momentâneo.", desc:"Botões simples usados em painéis e protoboards.", img:".jpg" },
"Relé de potência Schrack RP510024": { qtd: "3", voltagem:"Bobina 24VDC", corrente:"20–30A contatos", funcao:"Comuta cargas de alta corrente.", desc:"Relé industrial robusto para cargas pesadas.", img:".jpg" },
"Resistor 100k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Limita corrente e divide tensão.", desc:"Resistor padrão para circuitos analógicos.", img:".jpg" },
"Resistor 120k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Restringe corrente.", desc:"Componente comum em filtros e divisores.", img:".jpg" },
"Resistor 15k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Define níveis de sinal.", desc:"Usado em circuitos gerais.", img:".jpg" },
"Resistor 18k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Reduz corrente.", desc:"Padrão para eletrônica básica.", img:".jpg" },
"Resistor 1k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Limita corrente.", desc:"Comum em LEDs e divisores.", img:".jpg" },
"Resistor 1M2": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Alta impedância.", desc:"Usado em sensores e amplificadores.", img:".jpg" },
"Resistor 1M5": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Alta resistência.", desc:"Empregado em instrumentação.", img:".jpg" },
"Resistor 1Ω": { qtd: "200", voltagem:"-", corrente:"1/2W", funcao:"Limita pequenas quedas de tensão.", desc:"Usado em medições e shunts.", img:".jpg" },
"Resistor 220Ω": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Limita corrente.", desc:"Muito usado com LEDs.", img:".jpg" },
"Resistor 22k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Resistência intermediária.", desc:"Comum em circuitos analógicos.", img:".jpg" },
"Resistor 27Ω": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Baixa resistência.", desc:"Usado em ajustes finos.", img:".jpg" },
"Resistor 33k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Define níveis de tensão.", desc:"Utilizado em diversos circuitos.", img:".jpg" },
"Resistor 33Ω": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Resistência baixa.", desc:"Usado em limitadores de corrente.", img:".jpg" },
"Resistor 3k3": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Resistência média.", desc:"Componente comum em eletrônica.", img:".jpg" },
"Resistor 5k6": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Resistência média.", desc:"Usado em filtros e controles.", img:".jpg" },
"Resistor 680R": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Limita corrente.", desc:"Usado em LEDs e circuitos diversos.", img:".jpg" },
"Resistor 71.5k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Resistência precisa.", desc:"Usado em instrumentação e precisão.", img:".jpg" },
"Resistor 820Ω": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Limita corrente.", desc:"Utilizado em divisores e LEDs.", img:".jpg" },
"Resistor 82k": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Define tensão.", desc:"Usado em sinais analógicos.", img:".jpg" },
"Resistor 8k2": { qtd: "200", voltagem:"-", corrente:"1/4W", funcao:"Resistência intermediária.", desc:"Componente comum em diversos projetos.", img:".jpg" },
"Ressonadores": { qtd: "36", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Ressonadores 3 pinos": { qtd: "17", voltagem:"5V", corrente:"<1mA", funcao:"Gera frequência estável.", desc:"Ressonadores cerâmicos usados como clock.",img:".jpg" },

"Sistema integrado não identificado": { qtd: 600, voltagem:"-", corrente:"-", funcao:".", desc:"", img:".jpg" },

"TDA’s": { qtd: "27", voltagem:"12–24V", corrente:"Dependente do modelo", funcao:"Amplifica áudio.", desc:"CIs de potência usados em amplificadores.",img:".jpg" },

"Termostatos": { qtd: "2", voltagem:"110/220V", corrente:"5–15A", funcao:"Controla temperatura.", desc:"Chave térmica que abre e fecha conforme a temperatura.",img:".jpg" },

"Transformador": { qtd: "1", voltagem:"", corrente:"", funcao:".", desc:"", img:".jpg" },

"Transistor BD135": { qtd: "3", voltagem:"45V", corrente:"1.5A", funcao:"NPN de média potência.", desc:"Usado em drivers e reguladores.", img:".jpg" },
"Transistor BD139": { qtd: "2", voltagem:"80V", corrente:"1.5A", funcao:"NPN de potência média.", desc:"Comum em áudio e fontes.", img:".jpg" },
"Transistor BD140": { qtd: "1", voltagem:"80V", corrente:"1.5A", funcao:"PNP de potência média.", desc:"Complementar ao BD139.", img:".jpg" },
"Transistor BD243C": { qtd: "5", voltagem:"100V", corrente:"6A", funcao:"NPN de potência.", desc:"Usado em fontes e amplificadores.", img:".jpg" },
"Transistor BD433": { qtd: "5", voltagem:"45V", corrente:"1A", funcao:"NPN universal.", desc:"Usado em controles e reguladores.", img:".jpg" },
"Transistor BD435": { qtd: "10", voltagem:"45V", corrente:"4A", funcao:"NPN de potência.", desc:"Amplificadores e drivers.", img:".jpg" },
"Transistor BD437": { qtd: "9", voltagem:"60V", corrente:"4A", funcao:"NPN forte.", desc:"Comum em som automotivo.", img:".jpg" },
"Transistor BF494": { qtd: "164", voltagem:"30V", corrente:"50mA", funcao:"NPN RF.", desc:"Usado em rádio e VHF.", img:".jpg" },
"Transistor BF495": { qtd: "217", voltagem:"30V", corrente:"50mA", funcao:"NPN RF.", desc:"Similar ao BF494 para recepção.", img:".jpg" },
"Transistor BF789": { qtd:"15", voltagem:"60V", corrente:"100mA", funcao:"Transistor RF.", desc:"Usado em amplificadores de RF.", img:".jpg" },
"Transistor BF871": { qtd:"4", voltagem:"45V", corrente:"50mA", funcao:"NPN RF.", desc:"Usado em telecom.", img:".jpg" },
"Transistor BF873": { qtd:"2", voltagem:"45V", corrente:"50mA", funcao:"NPN RF.", desc:"Baixo ruído para RF.", img:".jpg" },
"Transistor BU150": { qtd: "8", voltagem:"700V", corrente:"8A", funcao:"Transistor horizontal.", desc:"Usado em TVs CRT.", img:".jpg" },
"Transistor BU2030": { qtd: "16", voltagem:"400V", corrente:"4A", funcao:"Horizontal.", desc:"Controle de deflexão.", img:".jpg" },
"Transistor BU208A": { qtd: "7", voltagem:"1500V", corrente:"8A", funcao:"Alta tensão.", desc:"Usado em TVs e fontes.", img:".jpg" },
"Transistor BU326A": { qtd: "2", voltagem:"450V", corrente:"10A", funcao:"Potência.", desc:"Etapas de alta tensão.", img:".jpg" },
"Transistor BU406": { qtd: "20", voltagem:"800V", corrente:"4A", funcao:"Horizontal.", desc:"Equipamentos de TV CRT.", img:"https://tse1.mm.bing.net/th/id/OIP.beihLh-_QR19SizolIwelwHaHa?rs=1&pid=ImgDetMain&o=7&rm=3" },
"Transistor TIP110": { qtd: "6", voltagem:"100V", corrente:"2A", funcao:"Darlington NPN.", desc:"Alto ganho para drivers.", img:".jpg" },
"Transistor TIP112": { qtd: "3", voltagem:"100V", corrente:"2A", funcao:"Darlington NPN.", desc:"Drivers de potência.", img:".jpg" },
"Transistor TIP122": { qtd: "12", voltagem:"100V", corrente:"5A", funcao:"Darlington NPN.", desc:"Amplificadores e motores.", img:".jpg" },
"Transistor TIP147": { qtd: "5", voltagem:"100V", corrente:"10A", funcao:"PNP potência.", desc:"Complementar ao TIP142.", img:".jpg" },
"Transistor IRFZ44": { qtd: "4", voltagem:"55V", corrente:"49A", funcao:"MOSFET N canal.", desc:"Usado em fontes e automotivo.", img:".jpg" },
"Transistor IRF740": { qtd: "2", voltagem:"400V", corrente:"10A", funcao:"MOSFET alta tensão.", desc:"Fontes chaveadas.", img:".jpg" },
"Transistor IRF9530": { qtd: "4", voltagem:"100V", corrente:"14A", funcao:"MOSFET P canal.", desc:"Comutação e áudio.", img:".jpg" },
"Transistor BUZ11": { qtd: "6", voltagem:"50V", corrente:"30A", funcao:"MOSFET N.", desc:"Usado em PWM e controle.", img:".jpg" },
"Transistor 2N2218": { qtd: "101", voltagem:"30V", corrente:"800mA", funcao:"NPN geral.", desc:"Drivers e controles.", img:".jpg" },
"Transistor 2N2222": { qtd: "38", voltagem:"40V", corrente:"800mA", funcao:"NPN universal.", desc:"Muito usado em projetos.", img:".jpg" },
"Transistor 2N2222A": { qtd: "5", voltagem:"40V", corrente:"800mA", funcao:"NPN.", desc:"Versão reforçada.", img:".jpg" },
"Transistor 2N3055": { qtd: "1", voltagem:"60V", corrente:"15A", funcao:"Potência.", desc:"Usado em amplificadores.", img:".jpg" },
"Transistor 2N3773": { qtd: "13", voltagem:"140V", corrente:"16A", funcao:"Alta potência.", desc:"Aplicações industriais.", img:".jpg" },
"Transistor 2N3904": { qtd: "48", voltagem:"40V", corrente:"200mA", funcao:"NPN pequeno sinal.", desc:"Comum em eletrônica geral.", img:".jpg" },
"Transistor 2N3906": { qtd: "5", voltagem:"40V", corrente:"200mA", funcao:"PNP sinal.", desc:"Complementar ao 3904.", img:".jpg" },
"Transistor 2N4918": { qtd: "5", voltagem:"80V", corrente:"1A", funcao:"Potência média.", desc:"Drivers e reguladores.", img:".jpg" },

"Transistor NPN": { qtd:"350", voltagem:"40–60V", corrente:"100–800mA", funcao:"Amplificação ou comutação de sinais.", desc:"Transistor de uso geral NPN para pequenos sinais e circuitos de baixa potência.", img:".jpg" },

"Transistor PNP": { qtd:"300", voltagem:"40–60V", corrente:"100–800mA", funcao:"Amplificação ou comutação de sinais.", desc:"Transistor de uso geral PNP para pequenos sinais e inversão de polaridade em circuitos.", img:".jpg" },

"Válvulas de 8 pinos": { qtd:"9", voltagem:"250–350V (placa)", corrente:"10–50mA", funcao:"Amplificação ou retificação.", desc:"Tubo eletrônico octal usado em áudio, RF ou retificação em equipamentos antigos.", img:".jpg" },

"Valvulas": { qtd:"9", voltagem:"250–350V", corrente:"10–50mA", funcao:"Amplificação termo-iônica.", desc:"Tubo eletrônico usado em áudio e RF antigos.", img:".jpg" },
"Voltimetros": { qtd:"17", voltagem:"5–30V", corrente:"<20mA", funcao:"Mede tensão elétrica.", desc:"Painel digital ou analógico para medição de tensão.", img:".jpg" },
"Zeners 3V": { qtd:"12", voltagem:"3V", corrente:"500mA", funcao:"Regula tensão.", desc:"Zener de baixa tensão para estabilização.", img:".jpg" },
"Zeners 6.2V": { qtd:"17", voltagem:"6.2V", corrente:"500mA", funcao:"Regulação.", desc:"Zener comum em circuitos lógicos.", img:".jpg" },
"Zeners 9V": { qtd:"18", voltagem:"9V", corrente:"500mA", funcao:"Regula tensão.", desc:"Zener usado em fontes.", img:".jpg" },
"Zeners 12V": { qtd:"71", voltagem:"12V", corrente:"500mA", funcao:"Estabiliza tensão.", desc:"Muito usado em reguladores caseiros.", img:".jpg" },
"Zeners 18V": { qtd:"46", voltagem:"18V", corrente:"500mA", funcao:"Clampeia tensão.", desc:"Proteção e regulação de circuitos.", img:".jpg" },
"Conectores genéricos": { qtd:"53", voltagem:"Até 50V", corrente:"1–5A", funcao:"Interliga cabos.", desc:"Diversos tipos de conectores elétricos.", img:".jpg" },
"Lâmpadas micro": { qtd:"19", voltagem:"6–12V", corrente:"50–200mA", funcao:"Iluminação.", desc:"Mini lâmpadas usadas em painéis.", img:".jpg" },
"Resistores variados": { qtd:"5400", voltagem:"Até 250V", corrente:"Depende da resistência", funcao:"Limita corrente.", desc:"Pacote grande com resistores diversos de 1/4W.", img:".jpg" },
"Capacitores diversos": { qtd:"620", voltagem:"16–400V", corrente:"-", funcao:"Armazenam carga elétrica.", desc:"Lote de eletróliticos, cerâmicos e poliéster.", img:".jpg" },
"Fusíveis": { qtd:"54", voltagem:"250V", corrente:"100mA–10A", funcao:"Proteção contra sobrecorrente.", desc:"Fusíveis de vidro e terminais.", img:".jpg" },
"Microchaves": { qtd:"33", voltagem:"125–250V", corrente:"1–5A", funcao:"Acionamento mecânico.", desc:"Chaves tipo clique usadas em eletrodomésticos.", img:".jpg" }

};

const equipamentos = {
 
"Caixas de disjuntor": {
  funcao:"Protege e organiza disjuntores.",
  desc:"Caixas para instalação de disjuntores residenciais ou industriais.",
  img:"https://down-br.img.susercontent.com/file/sg-11134201-7qvg0-li9l6769rh8777",
  quantidade:"3"
},

"Carretel de bobinas": { 
  qtd: "27",
  funcao:"armazenamento e a organização de materiais flexíveis e longos", 
  desc:"suporte cilíndrico projetado para enrolar e armazenar materiais flexíveis e longos", 
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSi92gieP2WWT3U1jgpi52bklXRb8R0tsbaNG9hMA9hJE2HeuyH5YTQrtyO9Fjewf78AcE&usqp=CAU" 
},


"Coolers": {
  voltagem:" 5V a 12V",
  funcao:"Resfria equipamentos eletrônicos.",
  desc:"Coolers diversos para refrigeração de circuitos.",
  img:"https://cf.shopee.com.br/file/3648a2c45c416237359af337e8aa79d1",
  quantidade:10
},

"Fio de rede": {
  voltagem:"44 V a 57 V",
  funcao:"Transmite sinais de rede.",
  desc:"Cabo de rede para conexão Ethernet.",
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQbT8V_16axNmDqBAFe5LdmuKcBneQrQ50DAQ&s",
  quantidade:"1"
},

"Protoboards": { 
  qtd: "8", 
  funcao:"Controla dois canais ao mesmo tempo.", 
  desc:"Usados em estéreo e ajustes simultâneos.",
  img:"https://cdn.awsli.com.br/800x800/853/853129/produto/32757951/f4e90ca4fa.jpg" 
},  

"Relés 2 canais": {
  voltagem:"5VDC, 12VDC, 24VDC",
  corrente:"10A, 25A, 40A",
  funcao:"Comuta circuitos usando sinais elétricos.",
  desc:"Relés eletromecânicos convencionais.",
  img:"https://cdn.awsli.com.br/300x300/468/468162/produto/19414409/106e8da5c7.jpg",
  quantidade:"6"
},

"Relés de estado sólido": {
  voltagem:"24-480 VAC",
  corrente:"Entrada: 3-32 VDC Saída: 10A-100A ",
  funcao:"Comuta circuitos eletrônicos sem partes móveis.",
  desc:"Relé eletrônico de alta velocidade e longa durabilidade.",
  img:"https://47eletrica.cdn.magazord.com.br/img/2024/02/produto/4716/01-rele-de-estado-solido-monofasico-ssr-controle-3-32vcc-tensao-30-480vca-ssr-60da-60a.png?ims=600x600",
  quantidade:"2"
},

"Teclado de silicone": { 
  qtd: "15", 
  funcao:".", 
  desc:"", 
  img:"https://p.globalsources.com/IMAGES/PDT/S1222071751/Teclado-de-silicio.jpg?ver=6018719940" 
  },

};

const ferramentas = {
"Alicate amperímetro": {
  Quant:"1",  
  funcao:"Mede corrente elétrica.",
  desc:"Ferramenta utilizada para medições rápidas.",
  img:"https://daxonart8aj4m.cloudfront.net/Custom/Content/Products/25/12/25123_48655-multmetro-digital-com-alicate-ampermetro_z1_638656597941271093.webp"
},

"Alicate de corte": {
  Quant:"1",
  funcao:"Corta fios e terminais.",
  desc:"Ferramenta de corte para eletrônica.",
  img:"https://antferramentas.vtexassets.com/arquivos/ids/161906-800-auto?v=635857862083600000&width=800&height=auto&aspect=true"
},

"Alicate rebitador": {
  Quant:"1",
  funcao:"Aplica rebites.",
  desc:"Usado para fixação mecânica.",
  img:"https://img.irroba.com.br/fit-in/600x600/filters:fill(fff):quality(80)/hidrauli/catalog/api/hidrauli_citelirr/62cdbe315fcb2.jpg"
},

"Alicate Universal": {
  Quant:"2",
  funcao:"Aperta, corta e dobra fios.",
  desc:"Ferramenta multiuso para eletricista.",
  img:"https://www.dutramaquinas.com.br/shared/img/produto/alta/144969_alicate_universal_isolado_aco_cromo_vanadio_8.webp"
},

"Apoiador de ferro de solda": {
  Quant:"1",
  funcao:"Suporta o ferro de solda aquecido.",
  desc:"Evita acidentes e queimaduras.",
  img:"https://http2.mlstatic.com/D_Q_NP_939810-MLA93087988986_092025-O.webp"
},

"Descapadores": {
  Quant:"16",
  funcao:"Remove isolamento de fios.",
  desc:"Indispensável para montagem eletrônica.",
  img:"https://http2.mlstatic.com/D_Q_NP_928816-MLU76716505754_062024-O.webp"
},

"Ferros de solda": {
  Quant:"4", 
  funcao:"Realiza soldagem eletrônica.",
  desc:"Ferramenta aquecida para soldar componentes.",
  img:"https://cdn.awsli.com.br/757/757427/produto/38811943/3caabcdaf6.jpg"
},

"Furador": {
  Quant:"1", 
  funcao:"Fura materiais diversos.",
  desc:"Ferramenta para pequenos furos em PCB.",
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTZjMkz5LeLJ0MyjvoMtcxvBvf6RckecQJux67nZhRt7ln9XuadCVPqquV0zzJyHqxwCX4&usqp=CAU"
},

"Furadores de placa": {
  Quant:"8",
  funcao:"Fura placas de circuito.",
  desc:"Serve para criar furos em placas de fenolite.",
  img:"https://images.tcdn.com.br/img/img_prod/751846/perfurador_de_placa_de_circuito_impresso_2069_2_e454488580eac336426b0e2b9148b059_20240418040229.jpg"
},


"Kit de ferramentas": {
  Quant:"1",
  funcao:"Conjunto variado de ferramentas.",
  desc:"Contém itens básicos para manutenção.",
  img:"https://cdn.awsli.com.br/600x700/1551/1551409/produto/222240738/14011-xeizfso8ea.jpg"
},

"Mini molas": {
  Quant:"15",
  funcao:"Retorno mecânico leve.",
  desc:"Aplicadas em peças pequenas.",
  img:"https://m.media-amazon.com/images/I/51JkMJUA-yL._SL1100_.jpg"
},

"Molas": {
  Quant:"21",
  funcao:"Pressão mecânica.",
  desc:"Usadas em mecanismos gerais.",
  img:"https://ae01.alicdn.com/kf/S1a048f293d8e4b77b9fb9e6dc7c9c21aG.jpg"
},

"Pacote de fixador": {
  Quant:"1",
  funcao:"Seguro de peças e componentes.",
  desc:"Conjunto de fixadores diversos.",
  img:"https://http2.mlstatic.com/D_NQ_NP_821406-MLA92549119152_092025-O.webp"
},

"Paquímetro": {
  Quant:"1",
  funcao:"Mede dimensões com precisão.",
  desc:"Ferramenta de medição milimétrica.",
  img:"https://www.paraflex.com.br/wp-content/uploads/2022/12/paquimetro-aco.webp"
},


"Pinça": {
  Quant:"1",
  funcao:"Segura pequenos componentes.",
  desc:"Usada em SMD e eletrônica fina.",
  img:"https://images.tcdn.com.br/img/img_prod/1231250/pinca_adson_reta_18cm_2621_1_6783523b959b6d46f6e2d92f97b727c9.jpg"
},

"Porcas e Parafusos": {
  Quant:"500",
  funcao:"Fixação com parafusos.",
  desc:"Porcas metálicas para montagem.",
  img:"https://www.amimetalurgica.com.br/wp-content/uploads/2018/01/parafusos.png"
},

"Pregos": {
  Quant:"300",
  funcao:"Fixação mecânica.",
  desc:"Usados para prender materiais.",
  img:"https://images.tcdn.com.br/img/img_prod/765502/prego_3x8_1kg_12373_1_058d3d0f928a54a02e07a49badb7f610.jpg"
},

"Rolo de fita veda rosca": {
  Quant:"1",
  funcao:"Veda conexões roscadas.",
  desc:"Usado em encanamento e vedação geral.",
  img:"https://img.irroba.com.br/fit-in/600x600/filters:fill(fff):quality(80)/atacadoz/catalog/api/atacadoz_integrac/67bcd0633f094.jpg" 
},

"Sugadores de solda": {
  Quant:"2",
  funcao:"Remove solda derretida.",
  desc:"Utilizado para retrabalho em placas.",
  img:"https://www.sotudo.com.br/imagens/produtos/m/16175_1.jpg"
},

"Terminais": {
  Quant:"70",
  funcao:"Conecta fios e componentes.",
  desc:"Diversos tipos de terminais elétricos.",
  img:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQYWqTQ39h1nAYup2qOD2BFCgwSkZgaoCLYCA&s"
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
