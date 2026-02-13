<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Valentine 💖</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:linear-gradient(-45deg,#ff4e50,#fc913a,#ff758c,#ff7eb3);
    background-size:400% 400%;
    animation:gradientBG 10s ease infinite;
    font-family:Arial, sans-serif;
    overflow:hidden;
}

@keyframes gradientBG{
    0%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
    100%{background-position:0% 50%;}
}

.container{
    background:white;
    padding:30px;
    border-radius:20px;
    text-align:center;
    box-shadow:0 10px 30px rgba(0,0,0,0.3);
    animation:fadeIn 1.5s ease;
}

h1{
    color:#e91e63;
}

button{
    padding:10px 20px;
    margin-top:15px;
    border:none;
    border-radius:10px;
    background:#e91e63;
    color:white;
    cursor:pointer;
    font-size:16px;
    transition:0.3s;
}

button:hover{
    background:#c2185b;
}

#letter{
    display:none;
    margin-top:15px;
    animation:fadeIn 1s ease;
    color:#e91e63;
    font-weight:bold;
}

@keyframes fadeIn{
    from{opacity:0; transform:translateY(10px);}
    to{opacity:1; transform:translateY(0);}
}

.heart{
    position:absolute;
    color:red;
    font-size:20px;
    animation:float 5s linear infinite;
}

@keyframes float{
    from{transform:translateY(100vh);}
    to{transform:translateY(-10vh);}
}
</style>
</head>

<body>

<div class="container">
    <h1>Happy Valentine's Day 💕</h1>
    <p>Click the button below 💌</p>
    <button onclick="openLetter()">Open My Heart ❤️</button>

    <div id="letter">
        You are the most beautiful part of my life 💖<br>
        I’m so lucky to have you 💕<br>
        Will you always be mine? 💍
    </div>
</div>

<!-- Background Music -->
<audio id="music" loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
</audio>

<script>
function openLetter(){
    document.getElementById("letter").style.display="block";
    document.getElementById("music").play();
    createHearts();
}

function createHearts(){
    setInterval(()=>{
        const heart=document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML="💖";
        heart.style.left=Math.random()*100+"vw";
        document.body.appendChild(heart);

        setTimeout(()=>{heart.remove();},5000);
    },300);
}
</script>

</body>
</html>
