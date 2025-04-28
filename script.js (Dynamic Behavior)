// Static 40-minute countdown always when page loads
function startCountdown(duration) {
    let timer = duration, minutes, seconds;
    const dynamicLine = document.getElementById('dynamic-line');
    const timerElement = document.getElementById('timer');

    dynamicLine.innerText = "Next Multi in:";

    const interval = setInterval(() => {
        minutes = parseInt(timer / 60, 10);
        seconds = parseInt(timer % 60, 10);

        timerElement.textContent = `${minutes}:${seconds < 10 ? '0' : ''}${seconds}`;

        if (--timer < 0) {
            clearInterval(interval);
            dynamicLine.innerText = "Coming Soon";
            timerElement.textContent = "";
        }
    }, 1000);
}

// Fetch IP address and Location using free API
async function loadIPLocation() {
    try {
        const res = await fetch('https://ipapi.co/json/');
        const data = await res.json();
        document.getElementById('ip-location').innerText = `IP: ${data.ip} | Location: ${data.city}, ${data.country_name}`;
    } catch (error) {
        document.getElementById('ip-location').innerText = 'Could not load IP and Location';
    }
}

// Update Current Time every second
setInterval(() => {
    document.getElementById('current-time').innerText = new Date().toLocaleTimeString();
}, 1000);

// Start everything when page loads
window.onload = function () {
    startCountdown(39 * 60 + 59); // Start 39:59 countdown
    loadIPLocation();
};
