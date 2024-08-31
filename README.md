# Stopwatch

This project features a simple stopwatch application built using HTML, CSS, and JavaScript. It allows users to start, stop, and reset a timer that displays hours, minutes, seconds, and milliseconds.

## Features

- **Start**: Begins the stopwatch.
- **Stop**: Stops the stopwatch.
- **Reset**: Resets the stopwatch to zero.

## Getting Started

1. **Clone the Repository**:
   git clone https://github.com/khushijain2100/stopwatch.git


2. **Navigate to the Project Directory**:
   cd stopwatch

3. **Open `stopwatch.html` in Your Browser**:
   You can open the `stopwatch.html` file directly in your web browser to view and use the stopwatch.

## File Structure

- `stopwatch.html`: Contains the HTML structure of the stopwatch.
- `stopwatch.css`: Contains the CSS styles for the stopwatch appearance.
- `stopwatch.js`: Contains the JavaScript code for stopwatch functionality.

![image](https://github.com/user-attachments/assets/617022ae-b3e2-41b1-8b36-201bd88fba06)


## Example Code
stopwatch.html
<!DOCTYPE html>
<html lang="en">

<head>
	<link rel="stylesheet" href="stopwatch.css">
</head>

<body>
	<div class="container">
		<h1><i>Stop Watch</i></h1>
		<div id="time">
			<span class="digit" id="hr">
				00</span>
			<span class="txt">Hr</span>
			<span class="digit" id="min">
				00</span>
			<span class="txt">Min</span>
			<span class="digit" id="sec">
				00</span>
			<span id="Sec">Sec</span>
			<span class="digit" id="count">
				00</span>
			<span id="AMPM">AM</span>
		</div>
		<div id="buttons">
			<button class="btn" id="start">
				Start</button>
			<button class="btn" id="stop">
				Stop</button>
			<button class="btn" id="reset">
				Reset</button>
		</div>
	</div>    
    <script src="stopwatch.js"></script>
</body>
</html>

stopwatch.css
body {
	padding: 0;
	margin: 0;
	font-family: verdana;
}

.container {
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	width: 100%;
	height: 100vh;
	background-color: rgb(0, 61, 0);
}

h1 {
	color: rgb(10, 238, 10);
	text-align: center;
}

.digit {
	font-size: 150px;
	color: #fff;
}
#AMPM{

		font-size:30px;
		color: #fff;
	}
#Sec{
	

		font-size:30px;
		color: #fff;
	
}

.txt {
	font-size: 30px;
	color: #fffcd6;
}

#buttons {
	margin-top: 50px;
}

.btn {
	width: 100px;
	padding: 10px 15px;
	margin: 0px 20px;
	border-top-right-radius: 10px;
	border-bottom-left-radius: 10px;
	border-bottom-right-radius: 4px;
	border-top-left-radius: 4px;
	cursor: pointer;
	font-size: 20px;
	transition: 0.5s;
	color: white;
	font-weight: 500;
}

#start {
	background-color: #009779;
}

#stop {
	background-color: #0e85fc;
}

#reset {
	background-color: #c91400;
}



stopwatch.js
let startBtn = document.getElementById('start');
let stopBtn = document.getElementById('stop');
let resetBtn = document.getElementById('reset');

let hour = 11;
let minute = 59;
let second =55;
let count = 0;

startBtn.addEventListener('click', function () {
	timer = true;
	stopWatch();
});

stopBtn.addEventListener('click', function () {
	timer = false;
});

resetBtn.addEventListener('click', function () {
	timer = false;
	hour = 0;
	minute = 0;
	second = 0;
	count = 0;
	document.getElementById('hr').innerHTML = "00";
	document.getElementById('min').innerHTML = "00";
	document.getElementById('sec').innerHTML = "00";
	document.getElementById('count').innerHTML = "00";
});

function stopWatch() {
	if (timer) 
	{
		count++;

		if (count == 100) 
		{
			second++;
			count = 0;
		}

		if (second == 60) 
		{
			minute++;
			second = 0;
		}

		if (minute == 60) 
		{
			hour++;
			minute = 0;
			second = 0;
		}

		let hrString = hour;
		let minString = minute;
		let secString = second;
		let countString = count;
		let AMPM="AM"

		if (hour < 10) 
		{
			hrString = "0" + hrString;
		}

		if(hour>=12)
		{
			AMPM="PM"
		}

		if (minute < 10) 
		{
			minString = "0" + minString;
		}

		if (second < 10) 
		{
			secString = "0" + secString;
		}

		if (count < 10) 
		{
			countString = "0" + countString;
		}

		document.getElementById('hr').innerHTML = hrString;
		document.getElementById('min').innerHTML = minString;
		document.getElementById('sec').innerHTML = secString;
		document.getElementById('count').innerHTML = countString;
		document.getElementById("AMPM").innerText=AMPM;
		setTimeout(stopWatch, 10);
	}
}

Contributing
If you have suggestions or improvements, feel free to open an issue or submit a pull request.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any questions or feedback, please contact me at khushijain21200@gmail.com
LinkedIn: https://www.linkedin.com/in/khushi-jain-735513259/
