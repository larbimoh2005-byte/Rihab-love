<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Rihab ❤️</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #ff9eb5, #ffc0cb);
    text-align: center;
    color: white;
    overflow: hidden;
}

h1 {
    margin-top: 60px;
    font-size: 2.5em;
}

img {
    width: 250px;
    border-radius: 20px;
    margin-top: 20px;
    box-shadow: 0 0 20px rgba(255,255,255,0.6);
}

.buttons {
    margin-top: 40px;
}

button {
    border: none;
    border-radius: 30px;
    padding: 15px 30px;
    font-size: 18px;
    cursor: pointer;
    margin: 10px;
    transition: 0.3s;
}

#yesBtn {
    background: #ff4d6d;
    color: white;
    font-size: 22px;
}

#noBtn {
    background: white;
    color: #ff4d6d;
}

/* Celebration screen */
#celebration {
    position: fixed;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background: radial-gradient(circle, #ff4d6d, #ff99aa);
    display: none;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

/* Hearts animation */
.heart {
    position: absolute;
    font-size: 24px;
    animation: floatUp 4s linear infinite;
}

@keyframes floatUp {
    0% { transform: translateY(100vh); opacity: 1; }
    100% { transform: translateY(-10vh); opacity: 0; }
}
</style>
</head>

<body>

<h1>Rihab 💖<br>Will you be my Valentine?</h1>

<!-- Replace this with your real image -->
<img src="your-photo.jpg" alt="Rihab">

<div class="buttons">
    <button id="yesBtn">Yes 😍</button>
    <button id="noBtn">No 😢</button>
</div>

<div id="celebration">
    <h1>Rihab ❤️</h1>
    <h2>You said YES 😭💖</h2>
    <p style="font-size:24px;">I promise to always make you smile 💕</p>
</div>

<script>
let yesSize = 22;

const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const celebration = document.getElementById("celebration");

noBtn.addEventListener("click", () => {
    yesSize += 10;
    yesBtn.style.fontSize = yesSize + "px";
    yesBtn.style.padding = (yesSize/2) + "px " + (yesSize) + "px";

    // Move NO button randomly
    noBtn.style.position = "absolute";
    noBtn.style.top = Math.random() * 80 + "%";
    noBtn.style.left = Math.random() * 80 + "%";
});

yesBtn.addEventListener("click", () => {
    document.body.innerHTML = `
        <div id="celebration" style="
            display:flex;
            position:fixed;
            width:100%;
            height:100%;
            top:0;
            left:0;
            background: radial-gradient(circle, #ff4d6d, #ff99aa);
            justify-content:center;
            align-items:center;
            flex-direction:column;
            color:white;
            text-align:center;
        ">
            <h1>Rihab ❤️</h1>
            <h2>You said YES 😭💖</h2>
            <p style="font-size:24px;">I promise to always make you smile 💕</p>
        </div>
    `;
    startHearts();
});

function startHearts() {
    setInterval(() => {
        const heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "❤️";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.fontSize = (Math.random() * 20 + 20) + "px";
        document.body.appendChild(heart);

        setTimeout(() => heart.remove(), 4000);
    }, 200);
}
</script>

</body>
</html>
