# Blesson-Feba-Wedding
Blesson Feba Wedding
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wedding Countdown</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Our Wedding Countdown</h1>
        <img src="C:\Users\HP\OneDrive\Pictures\bdc1e54d4315152f1e6eb2c28bcfd093" alt="Couple Picture" class="couple-picture">
        <div id="countdown">
            <div><span id="days"></span>Days</div>
            <div><span id="hours"></span>Hours</div>
            <div><span id="minutes"></span>Minutes</div>
            <div><span id="seconds"></span>Seconds</div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
}

.container {
    text-align: center;
    background: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

h1 {
    font-size: 2em;
    color: #333;
}

.couple-picture {
    width: 100%;
    max-width: 300px;
    border-radius: 10px;
    margin: 20px 0;
}

#countdown {
    display: flex;
    justify-content: center;
    gap: 15px;
    font-size: 1.5em;
    color: #555;
}

#countdown div {
    background: #eee;
    padding: 10px;
    border-radius: 5px;
}


// Set the date of the wedding
const weddingDate = new Date("2025-06-01T00:00:00").getTime();

// Update the countdown every second
const countdown = setInterval(() => {
    const now = new Date().getTime();
    const distance = weddingDate - now;

    // Calculate days, hours, minutes and seconds
    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    // Display the result in the corresponding elements
    document.getElementById("days").innerText = days;
    document.getElementById("hours").innerText = hours;
    document.getElementById("minutes").innerText = minutes;
    document.getElementById("seconds").innerText = seconds;

    // If the countdown is over, display some text
    if (distance < 0) {
        clearInterval(countdown);
        document.getElementById("countdown").innerHTML = "The Wedding Day is here!";
    }
}, 1000);
