# BMI-Calculator
Easily calculate your BMI, receive personalized feedback, and stay motivated on your path to a healthier you. Get insights into your weight status and embrace a well-balanced lifestyle. 







<!DOCTYPE html>

<html>

<head>

  <title>BMI Calculator</title>

  <style>

    body {

      font-family: Arial, sans-serif;

    }

    h1 {

      text-align: center;

    }

    .container {

      max-width: 400px;

      margin: 50px auto;

      padding: 20px;

      border: 1px solid #ccc;

      border-radius: 5px;

      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

      animation: fade-in 1s ease;

    }

    @keyframes fade-in {

      0% {

        opacity: 0;

        transform: translateY(-20px);

      }

      100% {

        opacity: 1;

        transform: translateY(0);

      }

    }

    label {

      display: block;

      margin-top: 10px;

      animation: slide-left 1s ease;

    }

    @keyframes slide-left {

      0% {

        opacity: 0;

        transform: translateX(-20px);

      }

      100% {

        opacity: 1;

        transform: translateX(0);

      }

    }

    input[type="text"], select {

      width: 100%;

      padding: 5px;

      animation: slide-right 1s ease;

    }

    @keyframes slide-right {

      0% {

        opacity: 0;

        transform: translateX(20px);

      }

       100% {

        opacity: 1;

        transform: translateX(0);

      }

    }

    button {

      display: block;

      width: 100%;

      margin-top: 10px;

      padding: 10px;

      background-color: #4CAF50;

      color: white;

      border: none;

      cursor: pointer;

      animation: scale-in 1s ease;

    }

    @keyframes scale-in {

      0% {

        opacity: 0;

        transform: scale(0.8);

      }

      100% {

        opacity: 1;

        transform: scale(1);

      }

    }

    .result {

      margin-top: 20px;

      font-weight: bold;

      text-align: center;

      animation: fade-in 1s ease;

    }

    .message {

      margin-top: 20px;

      text-align: center;

      font-style: italic;

    }

    .copyright {

      margin-top: 30px;

      text-align: center;

      color: #aaa;

      font-size: 13px;

    }

  </style>

</head>

<body>

  <div class="container">

    <h1>BMI Calculator</h1>

    <label for="gender">Gender:</label>

    <select id="gender">

      <option value="male">Male</option>

      <option value="female">Female</option>

    </select>

    <label for="weight">Weight (kg):</label>

    <input type="text" id="weight" placeholder="Enter your weight">

    <label for="height">Height (cm):</label>

    <input type="text" id="height" placeholder="Enter your height">

    <button onclick="calculateBMI()">Calculate</button>

    <button onclick="resetForm()">Reset</button>

    <div class="result" id="result"></div>

    <div class="message" id="message"></div>

  </div>

  <script>

    var goodSpeaks = [

      'Well done! Keep up the great work.',

      'You are on the right track. Stay committed!',

      'Great job! Your efforts are paying off.',

      'Congratulations! Keep striving for success.',

      'Fantastic job! Keep up the amazing progress.'

    ];

    var motivationSpeaks = [

      'Believe in yourself and all that you are. Know that there is something inside you that is greater than any obstacle.',

      'The only bad workout is the one that didn',

      'The only person you are destined to become is the person you decide to be.',

      'Success is not final, failure is not fatal: It is the courage to continue that counts.',

      'Set goals. Say prayers. Work hard.'

    ];

    function getRandomItem(items) {

      return items[Math.floor(Math.random() * items.length)];

    }

    function calculateBMI() {

      var gender = document.getElementById('gender').value;

      var weight = parseFloat(document.getElementById('weight').value);

      var height = parseFloat(document.getElementById('height').value);

      if (isNaN(weight) || isNaN(height) || weight <= 0 || height <= 0) {

        document.getElementById('result').innerHTML = 'Please enter valid values for weight and height.';

        document.getElementById('message').innerHTML = '';

        return;

      }

      var bmi = weight / ((height / 100) * (height / 100));

      bmi = bmi.toFixed(2);

      var interpretation = '';

      var message = '';

      if (gender === 'male') {

        if (bmi < 18.5) {

          interpretation = 'Underweight';

          message = getRandomItem(goodSpeaks);

        } else if (bmi >= 18.5 && bmi <= 24.9) {

          interpretation = 'Normal weight';

          message = getRandomItem(goodSpeaks);

        } else if (bmi >= 25 && bmi <= 29.9) {

          interpretation = 'Overweight';

          message = getRandomItem(goodSpeaks);

        } else {

          interpretation = 'Obese';

          message = getRandomItem(goodSpeaks);

        }

      } else if (gender === 'female') {

        if (bmi < 18.5) {

          interpretation = 'Underweight';

          message = getRandomItem(goodSpeaks);

        } else if (bmi >= 18.5 && bmi <= 24.9) {

          interpretation = 'Normal weight';

          message = getRandomItem(goodSpeaks);

        } else if (bmi >= 25 && bmi <= 29.9) {

          interpretation = 'Overweight';

          message = getRandomItem(goodSpeaks);

        } else {

          interpretation = 'Obese';

          message = getRandomItem(goodSpeaks);

        }

      }

      if (message.includes('Tips')) {

        message += '<br><br><strong>Motivational Saying:</strong><br>';

        message += getRandomItem(motivationSpeaks);

      }

      document.getElementById('result').innerHTML = 'Your BMI is: ' + bmi + ' (' + interpretation + ')';

      document.getElementById('message').innerHTML = message;

    }

    function resetForm() {

      document.getElementById('gender').selectedIndex = 0;

      document.getElementById('weight').value = '';

      document.getElementById('height').value = '';

      document.getElementById('result').innerHTML = '';

      document.getElementById('message').innerHTML = '';

    }

  </script>

  <div class="copyright">

    Made by Aaron with ❤️ and effort | 2023 Copyright All Rights reserved

  </div>

</body>

</html>

