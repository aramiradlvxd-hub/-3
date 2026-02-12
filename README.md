<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Valentine ❤️</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #ff9eb5, #ffc2d1);
    text-align: center;
    color: #333;
}

.section {
    padding: 20px;
    min-height: 100vh;
    opacity: 1;
    transition: opacity 0.6s ease;
}

.hidden {
    opacity: 0;
    pointer-events: none;
    position: absolute;
    width: 100%;
}

img {
    width: 90%;
    max-width: 400px;
    border-radius: 20px;
    margin-top: 15px;
    box-shadow: 0 8px 20px rgba(0,0,0,0.2);
}

#letterText {
    white-space: pre-line;
    text-align: left;
    margin: 20px auto;
    max-width: 500px;
    font-size: 18px;
    min-height: 200px;
    background: rgba(255,255,255,0.75);
    padding: 15px;
    border-radius: 15px;
}

button {
    padding: 14px 22px;
    font-size: 18px;
    border: none;
    border-radius: 12px;
    margin: 10px;
    cursor: pointer;
    background: #ff4d6d;
    color: white;
}

#resultText {
    font-size: 26px;
    margin-top: 20px;
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div id="page1" class="section">
    <img src="photo.jpg">
    <div id="letterText"></div>
    <button onclick="showPage2()">Next ❤️</button>
</div>

<!-- PAGE 2 -->
<div id="page2" class="section hidden">
    <h2>Will you be my Valentine? ❤️</h2>

    <button onclick="sayYes()">Yes 💖</button>
    <button onclick="sayNo()">No</button>

    <div id="resultText"></div>
    <img id="yayImg" src="yay.jpg" class="hidden">
</div>

<script>
/* LETTER */
const letter = `HI ПИПСКВИК,

I still don't really understand why I have to ask you to be my Valentine since you are my girlfriend, because whose Valentine are you going to be????

But being serious, this is the second Valentine's Day that we will go through together, and every time I think about how long you've been my babin, I get soooooo happy.

I love you so so so so so much, and I can't even imagine what I would do without you. Without you in my life, Valentine's Day would just be another useless and unimportant day that I would want to skip. But since I have you, I can't wait to spend every single minute I have with you and only with you.

And since it is going to be on the 14th of February, I will list 14 things I love about you the most:

1. Your jokes
2. Your beautiful voice when you sing
3. The way you laugh (it's really cute)
4. Your long and beautiful hair
5. You make the best food
6. Your face is the prettiest thing I've ever seen
7. You are the most ambitious and strong girl in the world
8. You always support me in my hardest times
9. You believe in me and everything I do
10. You are always right
11. You are the smartest person in the world
12. Your cute little (huge) burps and farts
13. Your beautiful vision of our future life
14. You being my best gym buddy

Ok, well, I think it's time for you to answer my final question that you and I have been waiting for for so long)))))))`;

let i = 0;
const textArea = document.getElementById("letterText");

function typeWriter() {
    if (i < letter.length) {
        textArea.innerHTML += letter.charAt(i);
        i++;
        setTimeout(typeWriter, 20);
    }
}
typeWriter();

/* PAGE SWITCH */
function showPage2() {
    document.getElementById("page1").classList.add("hidden");
    document.getElementById("page2").classList.remove("hidden");
    window.scrollTo(0,0);
}

/* NO LOOP */
const noMessages = [
    "Are you sure about that????",
    "Seriously???",
    "Ok that's not funny",
    "Wrong answer",
    "Again wrong",
    "Again",
    "And again"
];

let noIndex = 0;

function sayNo() {
    document.getElementById("resultText").innerText =
        noMessages[noIndex];
    noIndex = (noIndex + 1) % noMessages.length;
}

/* YES */
function sayYes() {
    document.getElementById("resultText").innerText = "YAY!!!!";
    document.getElementById("yayImg").classList.remove("hidden");
}
</script>

</body>
</html>
