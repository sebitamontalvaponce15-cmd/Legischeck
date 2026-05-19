# Legischeck
Trata de una plataforma digital que le permite a la ciudadanía votar simbólicamente las leyes que sale del congreso, la gente solamente va a poder informarce de todo lo que va pasando y votar
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mi Votación</title>

<style>
body{
    font-family:Arial,sans-serif;
    background:#f2f2f2;
    text-align:center;
    padding:30px;
}

.container{
    max-width:450px;
    margin:auto;
    background:white;
    padding:25px;
    border-radius:15px;
    box-shadow:0 0 15px rgba(0,0,0,.2);
}

button{
    width:100%;
    padding:15px;
    margin:10px 0;
    border:none;
    border-radius:10px;
    font-size:16px;
    cursor:pointer;
}

button:hover{
    opacity:0.9;
}

.resultados{
    margin-top:20px;
}
</style>
</head>

<body>

<div class="container">

<h1>🗳️ Votación</h1>
<p>Elige una opción:</p>

<button onclick="votar('A')">Opción A</button>
<button onclick="votar('B')">Opción B</button>
<button onclick="votar('C')">Opción C</button>

<div class="resultados">
<h3>Resultados</h3>

<p>A: <span id="a">0</span></p>
<p>B: <span id="b">0</span></p>
<p>C: <span id="c">0</span></p>

</div>

<p id="mensaje"></p>

</div>

<script>

let votosA=Number(localStorage.getItem("votosA"))||0;
let votosB=Number(localStorage.getItem("votosB"))||0;
let votosC=Number(localStorage.getItem("votosC"))||0;

actualizar();

function votar(opcion){

if(localStorage.getItem("yaVoto")){
document.getElementById("mensaje").innerText="Ya votaste";
return;
}

if(opcion=="A"){
votosA++;
localStorage.setItem("votosA",votosA);
}

if(opcion=="B"){
votosB++;
localStorage.setItem("votosB",votosB);
}

if(opcion=="C"){
votosC++;
localStorage.setItem("votosC",votosC);
}

localStorage.setItem("yaVoto","si");

document.getElementById("mensaje").innerText="Gracias por votar";

actualizar();

}

function actualizar(){

document.getElementById("a").innerText=votosA;
document.getElementById("b").innerText=votosB;
document.getElementById("c").innerText=votosC;

}

</script>

</body>
</html>
