# Smart-Day-Suggestor

This is an Emotion Based Personal Day Planner made using HTML,CSS, and JavaScript.

---

### HTML,CSS and JavaScript Code  ('index.html','index.css','index.js')
```html,css and javascript

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Emotion Day Planner</title>
    <link rel="stylesheet" href="index.css">
</head>
<body>
    <div class="planner-container">
        <h1>⛅Emotion Based Personal Day Planner</h1>
        <div class="selector">
            <label for="mood">Mood:</label>
            <select  id="mood"><option value="happy">☺️Happy</option>
            <option value="sad">😓Sad</option>
        <option value="tired">😴Tired</option>
    <option value="anxious">😨Anxious</option>
<option value="in_love">🥰In-Love</option></select>
    <label for="weather">Weather:</label>
    <select id="weather"><option value="sunny">🌞Sunny</option>
    <option value="rainy">🌧Rainy</option>
<option value="cloudy">☁Cloudy</option>
<option value="fog">🌫Fog</option>
<option value="starry_night">ཐི❤︎ཋྀStarry Night</option></select>
        </div>
        <button onclick="generatePlan()">💣Generate My Plan</button>
        <div class="output"><h2 id="quote">💬Quote:</h2>
        <div id="plan"><p>🌅Morning:
        <span id="morning"></span></p>
    
    <p>☀️Afternoon:
        <span id="afternoon"></span></p>
        <p>🌇Evening:
            <span id="evening"></span>
        </p>
    </div>
<button onclick="playMusic()">🎧Recommended Playlist :▶︎•၊၊||၊|။||||။‌‌‌‌၊၊|• 0:10</button>
<audio id="audio" src="lofi-girl-lofi-ambient-music-365952.mp3"></audio>
<script src="index.js"></script>
</div>
    </div>

    
</body>
</html>
 

body{
    text-align: center;
    text-transform: uppercase;
    border: 400px;
    border-radius: 500px;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-size: cover;
    background-position: center;
    color: white;
    transition: background 0.5s ease-in-out;
}
.planner-container{
    background-color: rgba(0, 0, 0, 0.6);
    margin: 50px auto;
    padding: 30px;
    max-width: 900px;
    border-radius: 100px;
    text-align: center;
    box-shadow: 0 0 20px rgba(0,0,0,0.5);
}
select,button{
    padding: 10px;
    margin: 10px;
    font-size: 16px;
    border-radius: 8px;
    border: none;
}
button{
    background-color: #ffcc00;
    color: #222;
    cursor: pointer;
    font-weight: bold;
    
}
button:hover{
    background-color: #ffaa00;
}
.output{
    margin-top: 20px;
}
#plan p{
    margin: 8px 0;
}


function generatePlan()  {
    const mood = document.getElementById("mood").value;
    const weather=document.getElementById("weather").value;
    const quotes={
        happy:"Your smile is your SuperPower !",
        sad:"It's okay to not to be okay.Take it slow.",
        tired:"Rest is also Productive.",
        anxious:"Breathe. You're stronger than you think.",
        in_love:"In your smile,I see my world."
    };
    const plans = {
        sunny :{
            morning:"Take a refreshing wallk in the sun.",
            afternoon:"Work on your passion project.",
            evening:"Enjoy sunset with soft music."

        },
        rainy: {
            morning:"Stay in and enjoy a warm drink.",
            afternoon:"Watch your comfort movie.",
            evening:"Listen to lo-fi beats and relax."
        },
        fog:{
            morning:"Do light stretching indoors.",
            afternoon:"Read a book or journal.",
            evening:"Meditate for 10 minutes."
        },
        cloudy:{
            morning:"Wrap up and do yoga.",
            afternoon:"Bake or cook something new.",
            evening:"Netflix and chill under a blanket."
        },
        starry_Night :{
            morning:"Soft sunlight, light pink sky.",
            afternoon:"Spring breeze,soft cloude.",
            evening:"Sunset glow,orange-pink sky."
        }
    };
    const backgrounds={
        sunny:"c:\Users\HP\Downloads\sunny.jpg",
        rainy:"assets/images/rainy.jpg",
        foggy:"assets/images/fog.jpg",
        cloudy:"assets/images/cold.jpg"
    };
    document.getElementById("quote").innerText = "💬Quote:"+quotes[mood];
    document.getElementById("morning").innerText=plans[weather].morning;
    document.getElementById("afternoon").innerText=plans[weather].afternoon;
    document.getElementById("evening").innerText=plans[weather].evening;
    document.body.style.backgroundImage = 'url($backgrounds[weather]})';

}
function playMusic() {
    const audio = document.getElementById("audio");
    audio.play();
}