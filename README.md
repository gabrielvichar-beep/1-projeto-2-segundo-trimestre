---# 1-projeto-2-segundo-trimestre
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Universo Incrível</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#0f172a;
    color:white;
    transition:0.4s;
}

header{
    background:linear-gradient(135deg,#2563eb,#7c3aed);
    padding:30px;
    text-align:center;
}

header h1{
    font-size:2.5rem;
}

header p{
    margin-top:10px;
}

.container{
    max-width:1000px;
    margin:auto;
    padding:20px;
}

.card{
    background:rgba(255,255,255,0.08);
    padding:25px;
    border-radius:15px;
    margin:20px 0;
}

button{
    background:#3b82f6;
    color:white;
    border:none;
    padding:12px 20px;
    border-radius:8px;
    cursor:pointer;
    font-size:1rem;
}

button:hover{
    background:#2563eb;
}

#curiosidade{
    margin-top:15px;
    font-size:1.1rem;
}

.stats{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
    gap:15px;
}

.stat{
    background:rgba(255,255,255,0.08);
    padding:20px;
    border-radius:12px;
    text-align:center;
}

.numero{
    font-size:2rem;
    font-weight:bold;
    color:#60a5fa;
}

.light{
    background:#f5f5f5;
    color:#111;
}

.light .card,
.light .stat{
    background:white;
    box-shadow:0 2px 10px rgba(0,0,0,0.1);
}

footer{
    text-align:center;
    padding:20px;
    margin-top:30px;
}
</style>
</head>
<body>

<header>
    <h1>🚀 Universo Incrível</h1>
    <p>Descubra curiosidades fascinantes sobre o espaço.</p>
</header>

<div class="container">

    <div class="card">
        <h2>Curiosidade Espacial</h2>
        <p id="curiosidade">
            Clique no botão para descobrir algo interessante.
        </p>
        <br>
        <button onclick="novaCuriosidade()">
            Mostrar Curiosidade
        </button>
    </div>

    <div class="card">
        <h2>Estatísticas do Site</h2>

        <div class="stats">
            <div class="stat">
                <div class="numero" id="visitas">0</div>
                <p>Visitas na sessão</p>
            </div>

            <div class="stat">
                <div class="numero">8</div>
                <p>Planetas do Sistema Solar</p>
            </div>

            <div class="stat">
                <div class="numero">13,8B</div>
                <p>Anos do Universo</p>
            </div>
        </div>
    </div>

    <div class="card">
        <h2>Personalização</h2>
        <button onclick="alternarTema()">
            🌙 Alternar Tema
        </button>
    </div>

</div>

<footer>
    <p>Universo Incrível © 2026</p>
</footer>

<script>
const curiosidades = [
    "O Sol representa cerca de 99,8% da massa do Sistema Solar.",
    "Um dia em Vênus dura mais que um ano em Vênus.",
    "Existem bilhões de galáxias no universo observável.",
    "A Lua se afasta da Terra cerca de 3,8 cm por ano.",
    "Júpiter é tão grande que caberiam mais de 1.300 Terras dentro dele.",
    "Saturno poderia flutuar na água devido à sua baixa densidade.",
    "A luz do Sol leva cerca de 8 minutos para chegar à Terra."
];

function novaCuriosidade(){
    const aleatoria =
        curiosidades[Math.floor(Math.random()*curiosidades.length)];

    document.getElementById("curiosidade").textContent = aleatoria;
}

function alternarTema(){
    document.body.classList.toggle("light");
}

let visitas = sessionStorage.getItem("visitas") || 0;
visitas++;
sessionStorage.setItem("visitas", visitas);
document.getElementById("visitas").textContent = visitas;
</script>

</body>
</html>