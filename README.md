!doctype html>
<html>

<head>
    <meta charset="utf-8" />

    <title>Un ramo para ti</title>
    <style>
        body {
            height: 100%;
            width: 100%;
            background: #080f1a;
            overflow: hidden;
        }

        .container {
            position: absolute;
            left: 50%;
            top: 30%;
            transform: translate(-50%, -50%);
        }

        .glass {
            height: 800px;
            width: 600px;
            background: #122139;
            border-radius: 300px 300px 0px 0px;
        }

        .glass:before {
            content: "";
            height: 40px;
            width: 40px;
            transform-origin: center;
            border: 25px solid #122139;
            border-radius: 100%;
            position: absolute;
            left: 256px;
            top: -74px;
        }

        .glass:after {
            content: "";
            position: absolute;
            height: 15px;
            width: 600px;
            background: #a52a2a;
            top: 100%;
            left: 0%;
        }

        .shine {
            width: 26px;
            height: 330px;
            background: white;
            opacity: 0.2;
            position: absolute;
            left: 85%;
            top: 200px;
            border-radius: 100px;
            z-index: 10;
        }

        .shine:before {
            content: "";
            width: 26px;
            height: 40px;
            position: absolute;
            background: white;
            top: 365px;
            border-radius: 100px;
        }

        .petals>div {
            position: absolute;
            background: #d52d58;
            width: 85px;
            height: 120px;
            top: 200px;
            transition: all 0.5s ease-out;
        }

        .petals>div:nth-child(1) {
            border-radius: 15px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, 1);
            left: 268px;
            top: 200px;
            background: #d52d58;
        }

        .petals>div:nth-child(2),
        .petals>div:nth-child(4),
        .petals>div:nth-child(6) {
            background: #b81b43;
            left: 230px;
            border-radius: 0px 50px 0px 50px;
            transform-origin: bottom right;
        }

        .petals>div:nth-child(3),
        .petals>div:nth-child(5),
        .petals>div:nth-child(7) {
            background: #b81b43;
            left: 300px;
            border-radius: 50px 0px 50px 0px;
            transform-origin: bottom left;
        }

        .petals>div:nth-child(2) {
            z-index: 5;
            background: #ab1a3f;
            top: 218px;
            height: 130px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, .5);
            animation: bloom2 3s ease-in-out;
            animation-fill-mode: forwards;
        }

        .petals>div:nth-child(3) {
            z-index: 4;
            background: #ab1a3f;
            top: 218px;
            height: 130px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, .5);
            animation: bloom3 3s ease-in-out, glowing 2.5s ease-in-out infinite;
            animation-fill-mode: forwards;
        }

        .petals>div:nth-child(4) {
            z-index: 3;
            background: #b81b43;
            top: 213px;
            height: 135px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, .5);
            animation: bloom4 3s ease-in-out, glowing 2.5s ease-in-out infinite;
            animation-fill-mode: forwards;
        }

        .petals>div:nth-child(5) {
            z-index: 2;
            background: #b81b43;
            top: 213px;
            height: 135px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, .5);
            animation: bloom5 3s ease-in-out, glowing 2.5s ease-in-out infinite;
            animation-fill-mode: forwards;
        }

        .petals>div:nth-child(6) {
            z-index: 1;
            background: #c9204b;
            top: 200px;
            height: 130px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, .3);
            animation: bloom6 3s ease-in-out, glowing 2.5s ease-in-out infinite;
            animation-fill-mode: forwards;
        }

        .petals>div:nth-child(7) {
            z-index: 0;
            background: #c9204b;
            top: 200px;
            height: 130px;
            box-shadow: 0px 0px 60px rgba(245, 148, 184, .3);
            animation: bloom7 3s ease-in-out, glowing 2.5s ease-in-out infinite;
            animation-fill-mode: forwards;
        }

        .deadPetals>div {
            position: absolute;
            background: #d52d58;
            width: 20px;
            height: 15px;
            top: 200px;
            border-radius: 0px 30px 0px 30px;
            box-shadow: 0px 0px 30px rgba(245, 148, 184, .5);
            transition: all 0.5s ease-out;
        }

        .deadPetals>div:nth-child(1) {
            left: 119229959987px;
            transform: rotate(-30deg);
            animation: falling 20s 4s ease-in-out infinite;
        }

        .deadPetals>div:nth-child(2) {
            left: 26331084746px;
            transform: rotate(-30deg);
            animation: falling 20s 8s ease-in-out infinite;
        }

        .deadPetals>div:nth-child(3) {
            left: 129759500363px;
            transform: rotate(-30deg);
            animation: falling 20s 12s ease-in-out infinite;
        }

        .deadPetals>div:nth-child(4) {
            left: 99323149959px;
            transform: rotate(-30deg);
            animation: falling 20s 16s ease-in-out infinite;
        }

        .leaves>div:nth-last-child(1) {
            position: absolute;
            width: 55px;
            height: 30px;
            background: #338f37;
            top: 334px;
            left: 278px;
            border-radius: 100px;
        }

        .leaves>div:nth-child(1) {
            position: absolute;
            width: 15px;
            height: 390px;
            background: #054c05;
            top: 308px;
            left: 300px;
            border-radius: 0 0 100px 100px;
        }

        .leaves>div:nth-child(2) {
            position: absolute;
            width: 60px;
            height: 100px;
            top: 53px;
            border-radius: 10px 80px 40px 80px;
            background: #054c05;
            transform-origin: bottom;
            transform: rotate(-30deg);
            top: 412px;
            left: 254px;
            box-shadow: inset 10px 10px #066406;
        }

        .leaves>div:nth-child(3) {
            position: absolute;
            width: 60px;
            height: 100px;
            top: 53px;
            border-radius: 80px 1px 80px 40px;
            background: #054c05;
            transform-origin: bottom;
            transform: rotate(30deg);
            top: 360px;
            left: 300px;
            box-shadow: inset -10px 10px #066406;
        }

        .thorns>div {
            position: absolute;
            width: 0;
            height: 0;
            top: 200px;
        }

        .thorns>div:nth-child(odd) {
            border-top: 15px solid transparent;
            border-bottom: 15px solid transparent;
            border-left: 15px solid #054c05;
            left: 315px;
        }

        .thorns>div:nth-child(even) {
            border-top: 15px solid transparent;
            border-bottom: 15px solid transparent;
            border-right: 15px solid #054c05;
            left: 285px;
        }

        .thorns>div:nth-child(1) {
            top: 465px;
        }

        .thorns>div:nth-child(2) {
            top: 390px;
        }

        .thorns>div:nth-child(4) {
            top: 525px;
        }

        @keyframes bloom2 {
            50% {
                transform: rotate(-90deg);
                top: 400px;
                left: 150px;
            }

            100% {
                transform: rotate(-60deg);
                top: 615px;
                left: 100px;
                background: #71122a;
                box-shadow: 0px 0px 0px rgba(245, 148, 184, 0);
            }
        }

        @keyframes bloom3 {
            100% {
                transform: rotate(50deg);
            }
        }

        @keyframes bloom4 {
            100% {
                transform: rotate(-25deg);
            }
        }

        @keyframes bloom5 {
            100% {
                transform: rotate(25deg);
            }
        }

        @keyframes bloom6 {
            100% {
                transform: rotate(-10deg);
            }
        }

        @keyframes bloom7 {
            100% {
                transform: rotate(10deg);
            }
        }

        @keyframes glowing {
            50% {
                background: #d7365f;
                box-shadow: 0px 0px 60px rgba(245, 148, 184, 1);
            }
        }

        @keyframes falling {
            20% {
                top: 335px;
                background: #9d193b;
                box-shadow: 0px 0px 0px rgba(245, 148, 184, 0);
            }

            100% {
                top: 335px;
                opacity: 0;
            }
        }

        .texto {
            top: 50%;
            color: white;
            font-size: 35px;
            position: absolute;
            left: 10%;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="glass">
            <div class="shine"></div>
        </div>
        <div class="thorns">
            <div></div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="leaves">
            <div></div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="petals">
            <div></div>
            <div></div>
            <div></div>
            <div></div>
            <div></div>
            <div></div>
            <div></div>
        </div>
        <div class="deadPetals">
            <div></div>
            <div></div>
            <div></div>
            <div></div>
        </div>
    </div>
    <div>
        <h4 class="texto">Mi amor por ti durará hasta que caiga el último pétalo ❤️</h>
    </div>
</body>

</html>
