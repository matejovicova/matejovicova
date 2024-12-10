<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pexeso</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #game {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 10px;
            max-width: 600px;
            margin: 20px auto;
        }
        .card {
            background-color: #f0f0f0;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 20px;
            font-size: 16px;
            cursor: pointer;
            user-select: none;
        }
        .card.flipped {
            background-color: #a6dcef;
            color: white;
            cursor: default;
        }
        .hidden {
            visibility: hidden;
        }
    </style>
</head>
<body>
    <h1>Pexeso</h1>
    <p>Najdi všechny dvojice!</p>
    <div id="game"></div>
    <script>
        const pairs = [
            "Mach", "Šebestová", "Křemílek", "Vochomůrka", "Štaflík", "Špagetka",
            "Jája", "Pája", "Velen", "Večernice", "Anče", "Kuba",
            "Spejbl", "Hurvínek", "Rumcajs", "Manka", "Čert", "Káča",
            "Lotrando", "Zubejda", "Jeníček", "Mařenka", "Dařbuján", "Pandrhola",
            "Dorotka", "Papoušek", "Káťa", "Škubánek", "Bob", "Bobek",
            "Pejsek", "Kočička", "Maková panenka", "motýl Emanuel",
            "hajný Robátko", "jelen Větrník", "Kráska", "Zvíře",
            "Pat", "Mat", "Bolek", "Lolek"
        ];

        let shuffledPairs = [...pairs, ...pairs].sort(() => 0.5 - Math.random());
        const gameContainer = document.getElemen
