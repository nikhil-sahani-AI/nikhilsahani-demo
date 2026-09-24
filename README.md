# nikhilsahani-demo
This is my first Animated login page .
<br>
author-NIKHIL SAHANI
<br.
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>AI Login Bot</title>

    <!-- ==================================================
         CSS START
    ================================================== -->

    <style>

        /* ---------- BASIC RESET ---------- */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }


        /* ---------- PAGE ---------- */

        body {
            min-height: 100vh;

            display: flex;
            justify-content: center;
            align-items: center;

            font-family: Arial, sans-serif;

            background:
                linear-gradient(
                    135deg,
                    #020b2e,
                    #003b91,
                    #008cff
                );

            overflow: hidden;
        }


        /* ---------- LOGIN CARD ---------- */

        .login-box {
            position: relative;

            width: 400px;

            padding: 90px 35px 35px;

            border-radius: 25px;

            background: rgba(0, 20, 70, 0.55);

            border: 1px solid #00cfff;

            box-shadow:
                0 0 30px rgba(0, 200, 255, 0.35);

            backdrop-filter: blur(15px);
        }


        /* ==================================================
           BOT
        ================================================== */

        .bot-wrapper {
            position: absolute;

            width: 160px;
            height: 160px;

            top: -115px;
            left: 50%;

            transform: translateX(-50%);

            transition: 0.2s;
        }


        /* ---------- BOT HEAD ---------- */

        .bot {
            position: relative;

            width: 150px;
            height: 150px;

            margin: auto;

            border-radius: 50%;

            background:
                linear-gradient(
                    to bottom,
                    #087ed1 0%,
                    #087ed1 52%,
                    #ecfbff 52%,
                    #ecfbff 100%
                );

            border: 2px solid rgba(255,255,255,0.4);

            box-shadow:
                0 0 20px #00d9ff,
                0 0 40px rgba(0,200,255,0.5);

            transition: 0.2s;
        }


        /* ==================================================
           EYES
        ================================================== */

        .eye {
            position: absolute;

            top: 38px;

            width: 45px;
            height: 45px;

            border-radius: 50%;

            background: #006fc1;

            display: flex;
            justify-content: center;
            align-items: center;

            overflow: hidden;
        }


        .eye.left {
            left: 22px;
        }


        .eye.right {
            right: 22px;
        }


        /* ---------- PUPIL ---------- */

        .pupil {
            width: 16px;
            height: 16px;

            background: white;

            border-radius: 50%;

            transition: 0.08s;
        }


        /* ==================================================
           EYELID
        ================================================== */

        .eyelid {
            position: absolute;

            left: -5px;
            top: -30px;

            width: 55px;
            height: 30px;

            background: #087ed1;

            border-radius: 50%;

            transition: 0.12s;

            z-index: 5;
        }


        /* ---------- BLINK ---------- */

        .bot.blink .eyelid {
            top: 8px;
        }


        /* ---------- PASSWORD EYE COVER ---------- */

        .bot.cover-eyes .eyelid {
            top: 7px;

            height: 35px;
        }


        /* ==================================================
           NOSE
        ================================================== */

        .nose {
            position: absolute;

            top: 76px;
            left: 50%;

            transform: translateX(-50%);

            width: 25px;
            height: 18px;

            background: #111;

            border-radius: 50%;
        }


        /* ==================================================
           MOUTH
        ================================================== */

        .mouth {
            position: absolute;

            top: 96px;
            left: 50%;

            transform: translateX(-50%);

            width: 40px;
            height: 18px;

            border-bottom: 4px solid #111;

            border-radius:
                0 0 50px 50px;

            transition: 0.25s;
        }


        /* ---------- SMILE ---------- */

        .bot.happy .mouth {
            width: 48px;

            height: 25px;

            border-bottom: 5px solid #111;

            border-radius:
                0 0 60px 60px;

            transform:
                translateX(-50%)
                scale(1.1);
        }


        /* ==================================================
           CHEEKS
        ================================================== */

        .cheek {
            position: absolute;

            top: 90px;

            width: 25px;
            height: 15px;

            background: #ff9daa;

            border-radius: 50%;
        }


        .cheek.left {
            left: 12px;
        }


        .cheek.right {
            right: 12px;
        }


        /* ==================================================
           HEAD MOVEMENT WHILE TYPING
        ================================================== */

        .bot-wrapper.typing {
            animation:
                headMove
                0.5s
                infinite
                alternate
                ease-in-out;
        }


        @keyframes headMove {

            0% {
                transform:
                    translateX(-50%)
                    translateY(0)
                    rotate(-2deg);
            }

            50% {
                transform:
                    translateX(-50%)
                    translateY(-6px)
                    rotate(2deg);
            }

            100% {
                transform:
                    translateX(-50%)
                    translateY(-2px)
                    rotate(-1deg);
            }
        }


        /* ==================================================
           TITLE
        ================================================== */

        h1 {
            text-align: center;

            color: #00d9ff;

            font-size: 30px;

            margin-bottom: 8px;
        }


        .subtitle {
            text-align: center;

            color: #b8efff;

            font-size: 14px;

            margin-bottom: 35px;
        }


        /* ==================================================
           INPUT
        ================================================== */

        .input-box {
            position: relative;

            margin-bottom: 25px;
        }


        .input-box label {
            position: absolute;

            left: 20px;
            top: -8px;

            padding: 0 5px;

            background: #073878;

            color: #a9efff;

            font-size: 13px;
        }


        .input-box input {
            width: 100%;

            padding: 16px 20px;

            border: 1px solid transparent;

            outline: none;

            border-radius: 20px;

            background: rgba(0,180,255,0.55);

            color: white;

            font-size: 16px;

            transition: 0.25s;
        }


        .input-box input:focus {
            border-color: #00e5ff;

            box-shadow:
                0 0 15px rgba(0,220,255,0.4);
        }


        .input-box input::placeholder {
            color: #b9edff;
        }


        /* ==================================================
           OPTIONS
        ================================================== */

        .options {
            display: flex;

            justify-content: space-between;

            align-items: center;

            color: white;

            font-size: 13px;

            margin-bottom: 25px;
        }


        .options a {
            color: #a8edff;

            text-decoration: none;
        }


        /* ==================================================
           BUTTON
        ================================================== */

        button {
            width: 100%;

            padding: 16px;

            border: none;

            border-radius: 20px;

            background:
                linear-gradient(
                    90deg,
                    #00aeea,
                    #00d4ff
                );

            color: white;

            font-size: 17px;

            font-weight: bold;

            cursor: pointer;

            transition: 0.25s;
        }


        button:hover {
            transform: translateY(-2px);

            box-shadow:
                0 0 25px
                rgba(0,220,255,0.6);
        }


        button:active {
            transform: scale(0.97);
        }


        /* ==================================================
           MOBILE
        ================================================== */

        @media (max-width: 500px) {

            .login-box {
                width: 90%;

                padding-left: 25px;
                padding-right: 25px;
            }
        }

    </style>

    <!-- ==================================================
         CSS END
    ================================================== -->

</head>


<body>


    <!-- ==================================================
         LOGIN BOX START
    ================================================== -->

    <div class="login-box">


        <!-- ---------- BOT ---------- -->

        <div class="bot-wrapper" id="botWrapper">

            <div class="bot" id="bot">


                <!-- LEFT EYE -->

                <div class="eye left">

                    <div
                        class="pupil"
                        id="leftPupil">
                    </div>

                    <div class="eyelid"></div>

                </div>


                <!-- RIGHT EYE -->

                <div class="eye right">

                    <div
                        class="pupil"
                        id="rightPupil">
                    </div>

                    <div class="eyelid"></div>

                </div>


                <!-- NOSE -->

                <div class="nose"></div>


                <!-- MOUTH -->

                <div
                    class="mouth"
                    id="mouth">
                </div>


                <!-- CHEEKS -->

                <div class="cheek left"></div>

                <div class="cheek right"></div>

            </div>

        </div>


        <!-- ---------- TITLE ---------- -->

        <h1>NIKHIL SAHANI</h1>

        <div class="subtitle">
            Welcome back. Your AI bot is watching.
        </div>


        <!-- ---------- USERNAME ---------- -->

        <div class="input-box">

            <label>Username</label>

            <input
                type="text"
                id="username"
                placeholder="Enter username"
                autocomplete="off"
            >

        </div>


        <!-- ---------- PASSWORD ---------- -->

        <div class="input-box">

            <label>Password</label>

            <input
                type="password"
                id="password"
                placeholder="Enter password"
            >

        </div>


        <!-- ---------- OPTIONS ---------- -->

        <div class="options">

            <label>

                <input type="checkbox">

                Remember me

            </label>


            <a href="#">
                Forgot password?
            </a>

        </div>


        <!-- ---------- BUTTON ---------- -->

        <button id="loginBtn">
            Sign In
        </button>


    </div>

    <!-- ==================================================
         LOGIN BOX END
    ================================================== -->



    <!-- ==================================================
         JAVASCRIPT START
    ================================================== -->

    <script>


        /* ==================================================
           1. GET HTML ELEMENTS
        ================================================== */

        const bot =
            document.getElementById("bot");

        const botWrapper =
            document.getElementById("botWrapper");

        const username =
            document.getElementById("username");

        const password =
            document.getElementById("password");

        const loginBtn =
            document.getElementById("loginBtn");

        const leftPupil =
            document.getElementById("leftPupil");

        const rightPupil =
            document.getElementById("rightPupil");



        /* ==================================================
           2. EYES FOLLOW MOUSE
        ================================================== */

        document.addEventListener(
            "mousemove",
            function(event) {

                /* Don't move eyes during password */

                if (
                    document.activeElement === password
                ) {
                    return;
                }


                const rect =
                    bot.getBoundingClientRect();


                const centerX =
                    rect.left +
                    rect.width / 2;


                const centerY =
                    rect.top +
                    rect.height / 2;


                let x =
                    event.clientX - centerX;


                let y =
                    event.clientY - centerY;


                /* Limit eye movement */

                x = Math.max(
                    -10,
                    Math.min(10, x / 25)
                );


                y = Math.max(
                    -10,
                    Math.min(10, y / 25)
                );


                /* Move pupils */

                leftPupil.style.transform =
                    `translate(${x}px, ${y}px)`;


                rightPupil.style.transform =
                    `translate(${x}px, ${y}px)`;

            }
        );



        /* ==================================================
           3. AUTOMATIC BLINKING
        ================================================== */

        function blink() {

            /* Don't blink while password is active */

            if (
                document.activeElement !== password
            ) {

                bot.classList.add("blink");


                setTimeout(
                    function() {

                        bot.classList.remove(
                            "blink"
                        );

                    },
                    140
                );
            }


            /* Random blink time */

            const nextBlink =
                Math.random() * 3000 + 2000;


            setTimeout(
                blink,
                nextBlink
            );
        }


        /* Start blinking */

        setTimeout(
            blink,
            2000
        );



        /* ==================================================
           4. USERNAME CLICK
        ================================================== */

        username.addEventListener(
            "focus",
            function() {

                /* Head movement */

                botWrapper.classList.add(
                    "typing"
                );


                /* Smile */

                bot.classList.add(
                    "happy"
                );

            }
        );



        /* ==================================================
           5. USERNAME TYPING
        ================================================== */

        username.addEventListener(
            "input",
            function() {

                /* Head movement */

                botWrapper.classList.add(
                    "typing"
                );


                /* Smile */

                bot.classList.add(
                    "happy"
                );

            }
        );



        /* ==================================================
           6. PASSWORD CLICK
        ================================================== */

        password.addEventListener(
            "focus",
            function() {

                /* Cover eyes */

                bot.classList.add(
                    "cover-eyes"
                );


                /* Remove smile */

                bot.classList.remove(
                    "happy"
                );


                /* Stop head movement */

                botWrapper.classList.remove(
                    "typing"
                );

            }
        );



        /* ==================================================
           7. PASSWORD TYPING
        ================================================== */

        password.addEventListener(
            "input",
            function() {

                /* Keep eyes covered */

                bot.classList.add(
                    "cover-eyes"
                );


                /* Small head movement */

                botWrapper.classList.add(
                    "typing"
                );

            }
        );



        /* ==================================================
           8. PASSWORD BLUR
        ================================================== */

        password.addEventListener(
            "blur",
            function() {

                /* Remove eye cover */

                bot.classList.remove(
                    "cover-eyes"
                );


                /* Stop typing animation */

                botWrapper.classList.remove(
                    "typing"
                );

            }
        );



        /* ==================================================
           9. USERNAME BLUR
        ================================================== */

        username.addEventListener(
            "blur",
            function() {

                /*
                 * Only remove typing
                 * if password is not active
                 */

                if (
                    document.activeElement !== password
                ) {

                    botWrapper.classList.remove(
                        "typing"
                    );

                }

            }
        );



        /* ==================================================
           10. SIGN IN BUTTON
        ================================================== */

        loginBtn.addEventListener(
            "click",
            function() {

                /* Happy bot */

                bot.classList.add(
                    "happy"
                );


                /* Head movement */

                botWrapper.classList.add(
                    "typing"
                );


                /* Change button */

                loginBtn.innerText =
                    "Signing in...";


                /* Demo delay */

                setTimeout(
                    function() {

                        loginBtn.innerText =
                            "Sign In";


                        botWrapper.classList.remove(
                            "typing"
                        );

                    },
                    1500
                );

            }
        );


    </script>

    <!-- ==================================================
         JAVASCRIPT END
    ==========================================
