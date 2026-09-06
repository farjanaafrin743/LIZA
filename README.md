# liza birthday
<Liza's Birthday 🎂>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>For Liza ♡</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: Georgia, serif;
            background:
                radial-gradient(circle at top, #7d243e, #3b0918 70%);
            color: #fff7f3;
            overflow: hidden;
        }

        .card {
            width: 90%;
            max-width: 520px;
            min-height: 500px;
            padding: 45px 30px;
            text-align: center;

            background: rgba(255, 240, 235, 0.08);
            border: 1px solid rgba(255,255,255,0.25);
            border-radius: 28px;

            box-shadow:
                0 25px 60px rgba(0,0,0,0.35),
                inset 0 0 30px rgba(255,255,255,0.03);

            backdrop-filter: blur(10px);

            animation: appear 1s ease;
        }

        .small {
            letter-spacing: 4px;
            font-size: 12px;
            text-transform: uppercase;
            opacity: 0.7;
        }

        h1 {
            font-size: 45px;
            margin: 20px 0 10px;
        }

        h2 {
            font-size: 30px;
            margin: 20px 0;
        }

        p {
            font-size: 18px;
            line-height: 1.8;
        }

        .symbol {
            font-size: 42px;
            margin: 10px;
            animation: float 2s infinite ease-in-out;
        }

        button {
            margin-top: 25px;
            padding: 14px 30px;

            border: none;
            border-radius: 30px;

            background: #f8dfe3;
            color: #5b1026;

            font-size: 16px;
            font-family: Georgia, serif;

            cursor: pointer;
            transition: 0.3s;
        }

        button:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 8px 20px rgba(0,0,0,0.25);
        }

        .hidden {
            display: none;
        }

        .line {
            width: 60px;
            height: 1px;
            background: #e7b8c1;
            margin: 20px auto;
        }

        .final {
            font-size: 20px;
            font-style: italic;
        }

        .heart {
            position: absolute;
            font-size: 20px;
            animation: rise 6s linear infinite;
            opacity: 0.5;
        }

        @keyframes appear {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-8px);
            }
        }

        @keyframes rise {
            from {
                transform: translateY(100vh);
                opacity: 0;
            }

            20% {
                opacity: 0.6;
            }

            to {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }
    </style>
</head>

<body>

    <div class="card">

        <!-- STEP 1 -->
        <div id="step1">

            <div class="symbol">♡</div>

            <div class="small">A little something for you</div>

            <h1>Hey, Liza.</h1>

            <p>
                Today is a little more special<br>
                because it's your day.
            </p>

            <button onclick="nextStep(1)">
                Start the surprise ✦
            </button>

        </div>


        <!-- STEP 2 -->
        <div id="step2" class="hidden">

            <div class="symbol">✉</div>

            <div class="small">Step Two</div>

            <h2>There's a little letter...</h2>

            <div class="line"></div>

            <p>
                Not a long one.<br>
                Just something from the heart.
            </p>

            <button onclick="nextStep(2)">
                Open the letter ♡
            </button>

        </div>


        <!-- STEP 3 -->
        <div id="step3" class="hidden">

            <div class="symbol">✧</div>

            <div class="small">A little note</div>

            <h2>Dear Liza,</h2>

            <p>
                Happy Birthday! 🎂
            </p>

            <p>
                I hope your days are filled with
                happiness, laughter and beautiful moments.
            </p>

            <p>
                Thank you for being such a wonderful friend. ♡
            </p>

            <button onclick="nextStep(3)">
                One more thing...
            </button>

        </div>


        <!-- STEP 4 -->
        <div id="step4" class="hidden">

            <div class="symbol">🎂</div>

            <div class="small">The final surprise</div>

            <h1>Happy Birthday!</h1>

            <div class="line"></div>

            <p class="final">
                May this year bring you<br>
                countless reasons to smile.
            </p>

            <h2>Happy Birthday, Liza ♡</h2>

            <p>
                With lots of love,<br>
                Your Friend
            </p>

        </div>

    </div>


    <script>

        function nextStep(current) {

            document.getElementById("step" + current)
                .classList.add("hidden");

            document.getElementById("step" + (current + 1))
                .classList.remove("hidden");
        }


        // Floating hearts

        function createHeart() {

            const heart = document.createElement("div");

            heart.className = "heart";
            heart.innerHTML = "♡";

            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration =
                (4 + Math.random() * 4) + "s";

            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 8000);
        }

        setInterval(createHeart, 900);

    </script>

</body>
</html>

