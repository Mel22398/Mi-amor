<html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Love</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #ffe6f0;
            overflow: hidden;
        }
        #container {
            margin-top: 20vh;
        }
        .hidden {
            display: none;
        }
        .button {
            background-color: #ff4081;
            color: white;
            border: none;
            padding: 10px 20px;
            margin: 10px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 5px;
        }
        #letter {
            width: 150px;
            cursor: pointer;
            margin-top: 20px;
        }
        @keyframes floatHearts {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 30px;
            animation: floatHearts 4s linear infinite;
        }
    </style>
</head>
<body>
    <div id="container">
        <h2>Do you know how much I love you?</h2>
        <button class="button" onclick="stepOne()">Poquito</button>
        <button class="button" onclick="stepOne()">Muchísimo</button>
    </div>

    <div id="step2" class="hidden">
        <h2>Are you sure?</h2>
        <button class="button" onclick="stepTwo()">Sí</button>
        <button class="button">No</button>
    </div>

    <div id="step3" class="hidden">
        <h2>Cupid brings gifts today to the best boyfriends, are you ready to see what he brought to you?</h2>
        <button class="button" onclick="stepThree()">Sí</button>
        <button class="button">No</button>
    </div>

    <div id="finalStep" class="hidden">
        <img id="letter" src="https://i.pinimg.com/736x/f8/b4/58/f8b458956c267822cd844c773d72f581.jpg" onclick="showGift()" alt="Letter">
        <p>Click here to see</p>
    </div>

    <div id="gift" class="hidden">
        <img src="https://i.pinimg.com/736x/86/c0/5e/86c05e4c3291790a5565d3bcd96dd1c2.jpg" width="500px">
        <h2>♡ Hola, amoooor here is our pretty little family, we love you sooo much, thank you for be my Valentine, papi ♡ </h2>
    </div>

    <script>
        function stepOne() {
            document.getElementById("container").classList.add("hidden");
            document.getElementById("step2").classList.remove("hidden");
        }
        function stepTwo() {
            document.getElementById("step2").classList.add("hidden");
            document.getElementById("step3").classList.remove("hidden");
        }
        function stepThree() {
            document.getElementById("step3").classList.add("hidden");
            document.getElementById("finalStep").classList.remove("hidden");
        }
        function showGift() {
            document.getElementById("finalStep").classList.add("hidden");
            document.getElementById("gift").classList.remove("hidden");
            createHearts();
        }
        function createHearts() {
            for (let i = 0; i < 30; i++) {
                let heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "❤️";
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.top = Math.random() * 100 + "vh";
                heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
                document.body.appendChild(heart);
                setTimeout(() => { heart.remove(); }, 4000);
            }
        }
    </script>
</body>
</html>
