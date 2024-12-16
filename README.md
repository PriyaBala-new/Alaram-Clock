# Alaram-Clock
Alarm Clock Application Documentation
Overview
The Alarm Clock is a web-based application developed using HTML, CSS, and JavaScript.
It features an interactive user interface allowing users to set alarms, use a stopwatch, and
toggle between different themes. This application is ideal for users seeking a minimalistic yet
functional time management tool.
Features
1. Alarm Clock
- Set alarms for specific dates and times.
- Manage multiple alarms with a display list.
- Trigger notifications and audio alerts when alarms go off.
2. Stopwatch
- Start, pause, and reset the stopwatch.
- Record and display lap times.
3. Themes
- Switch between Default, Dark, and Light themes for personalized viewing.
4. Real-Time Display
- Live display of the current date and time, updating every second.
Code Components
1. HTML Structure
The HTML defines the structure of the application:
`<div class="container alarm-container">: Contains the alarm clock, stopwatch, and theme options.
- Input fields: For setting alarm date and time.
- Buttons: For setting alarms, controlling the stopwatch, and changing themes.
2. CSS Styles
- Body Styling: A fullscreen background image with a flexible layout.
- Container Styling: Pink, rounded background with shadow effects for a polished appearance.
- Button Styling: Dynamic hover effects for better user interactivity.
Css
body {
background: url('background.jpg') no-repeat center center/cover;
}
.container {
background: pink;
border-radius: 10px;
}
button:hover {
background-color: #0056b3;
}
```
3. JavaScript Functionalities
a. Live Time and Date
Real-time updates using setInterval:
Javascript
function updateTime() {
const now = new Date();
document.getElementById('current-time').textContent = now.toLocaleTimeString('en-US', {
hour12: false });
document.getElementById('current-date').textContent = now.toISOString().split('T')[0];
}
setInterval(updateTime, 1000);
b. Alarm Clock
Allows users to set alarms and triggers a sound and alert when the time is reached.
Javascript
function setAlarm() {
const alarmDate = document.getElementById('alarm-date').value;
const alarmTime = document.getElementById('alarm-time').value;
const alarmDateTime = new Date(`${alarmDate}T${alarmTime}`);
if (alarmDateTime > new Date()) {
alarms.push(alarmDateTime);
} else {
alert('Please set a future alarm.');
}
}
c. Stopwatch
Interactive stopwatch with start, pause, reset, and lap recording:
javascript
function startStopwatch() {
stopwatchRunning = true;
stopwatchInterval = setInterval(() => {
stopwatchTime++;
updateStopwatchDisplay();
}, 1000);
}
d. Themes
Users can switch between pre-defined themes dynamically:
Javascript
function setTheme(theme) {
switch (theme) {
case 'dark':
document.body.style.backgroundColor = '#121212';
document.body.style.color = '#FFFFFF';
break;
case 'light':
document.body.style.backgroundColor = '#FFFFFF';
document.body.style.color = '#000000';
break;
default:
document.body.style.background = "url('background.jpg') no-repeat center center/cover";
}
}
File Structure
- index.html: Contains the structure of the web page.
- styles.css: Defines the appearance and layout.
- script.js: Implements the functionalities.
- background.jpg: Used as the background image.
- alarm.mp3: Alarm sound file.
How to Use
1. Setup:
- Ensure all files, including background.jpg and alarm.mp3, are in the same directory as
index.html.
2. Run the Application:
- Open `index.html` in a browser.
3. Set an Alarm:
- Select a date and time using the input fields.
- Click "Set Alarm" to schedule it.
4. Use the Stopwatch:
- Click "Start" to begin.
- Use "Pause," "Reset," and "Lap" for additional control.
5. Change Themes:
- Select a theme from the "Select Theme" section.
Future Enhancements
- Add a countdown timer feature.
- Allow users to upload custom alarm sounds.
- Add more themes with advanced color customization.
Credits
- Developer: Priyanka Gattu
- Technologies Used: HTML, CSS, JavaScript
- Resources: [MDN Web Docs](https://developer.mozilla.org/)
