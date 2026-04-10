<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday</title>

<style>
body {
    background-image: url(gg.png);
    background-size: cover;
    background-position: center;
    margin: 0;
    overflow: hidden;
    font-family: 'Arial', sans-serif;
  
    color: rgb(8, 8, 8);
    text-align: center;
}

h1 {
    font-size: 60px;
    margin-top: 100px;
    animation: glow 2s infinite alternate;
}

@keyframes glow {
    from { text-shadow: 0 0 10px #ff4da6; }
    to { text-shadow: 0 0 30px #ffff66; }
}

p {
    font-size: 25px;
}

button {
    padding: 12px 25px;
    font-size: 20px;
    border: none;
    border-radius: 10px;
    background: #fffb02;
    color: rgb(0, 0, 0);
    cursor: pointer;
}

button:hover {
    background: #fffb02;
}

/* balloons */
.balloon {
    position: absolute;
    bottom: -100px;
    width: 50px;
    height: 70px;
    background: red;
    border-radius: 50%;
    animation: float 6s linear infinite;
}

@keyframes float {
    from { transform: translateY(0); }
    to { transform: translateY(-120vh); }
}
</style>

</head>

<body>

<h1>🎉 Happy Birthday, <span id="SUNNY">SUNNY</span>! 🎂</h1>
<p>Wishing you happiness, love, and lots of cake! 🎁</p>

<button onclick="startParty()">Start Party 🎶</button>

<audio id="myAudio" loop>
<source src="happy.mp3" type="audio/mpeg"></audio>


<script>
function startParty() {
    var audio = document.getElementById("myAudio"); audio.play();

    // create balloons
    for (let i = 0; i < 20; i++) {
        let balloon = document.createElement("div");
        balloon.classList.add("balloon");
        balloon.style.left = Math.random() * 100 + "vw";
        balloon.style.background = randomColor();
        balloon.style.animationDuration = (Math.random() * 3 + 3) + "s";
        document.body.appendChild(balloon);
    }

  
}

function randomColor() {
    return "hsl(" + Math.random() * 360 + ", 70%, 60%)";
}
</script>

</body>
</html>
