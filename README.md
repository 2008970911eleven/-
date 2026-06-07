<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>摩斯密碼轉換器</title>
    <style>
        body { font-family: Arial, sans-serif; padding: 20px; max-width: 600px; margin: auto; text-align: center; }
        input { width: 80%; padding: 10px; margin: 10px 0; font-size: 16px; }
        button { padding: 10px 20px; font-size: 16px; background-color: #007bff; color: white; border: none; cursor: pointer; }
        button:hover { background-color: #0056b3; }
        #result { margin-top: 20px; padding: 15px; background: #f0f0f0; font-size: 18px; word-break: break-all; }
    </style>
</head>
<body>

<h2>摩斯密碼轉換器 (A~Z, 0~9)</h2>
    <p>輸入英文或數字（大小寫皆可自動轉換）</p>
    
 <input type="text" id="userInput" placeholder="請輸入要轉換的文字...">
    <br>
    <button onclick="convertToMorse()">轉換成摩斯密碼</button>

 <div id="result">摩斯密碼將顯示在這裡</div>
 <script>
        const MORSE_CODE_DICT = {
            'A': '.-', 'B': '-...', 'C': '-.-.', 'D': '-..', 'E': '.', 
            'F': '..-.', 'G': '--.', 'H': '....', 'I': '..', 'J': '.---', 
            'K': '-.-', 'L': '.-..', 'M': '--', 'N': '-.', 'O': '---', 
            'P': '.--.', 'Q': '--.-', 'R': '.-.', 'S': '...', 'T': '-', 
            'U': '..-', 'V': '...-', 'W': '.--', 'X': '-..-', 'Y': '-.--', 'Z': '--..',
            '1': '.----', '2': '..---', '3': '...--', '4': '....-', '5': '.....', 
            '6': '-....', '7': '--...', '8': '---..', '9': '----.', '0': '-----'
        };

 function convertToMorse() {
            const text = document.getElementById('userInput').value.toUpperCase();
            let morseResult = [];

 for (let char of text) {
                if (MORSE_CODE_DICT[char]) {
                    morseResult.push(MORSE_CODE_DICT[char]);
                } else if (char === ' ') {
                    morseResult.push('/');
                } else {
                    morseResult.push('?');
                }
            }

document.getElementById('result').innerText = morseResult.join(' ');
        }
    </script>
</body>
</html>
