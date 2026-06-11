# main.html
this html program or website helps the person to know their bank details
<!DOCTYPE html>
<html>
<head>
    <title>Bank Account Details</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
        }
        .container {
            width: 350px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
        input {
            width: 100%;
            padding: 8px;
            margin: 8px 0;
        }
        button {
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
        }
        #result {
            margin-top: 15px;
        }
    </style>
</head>
<body>

<div class="container">
    <h2>Bank Account Details</h2>

    <label>Customer Name:</label>
    <input type="text" id="name">

    <label>Principal Amount:</label>
    <input type="number" id="principal">

    <label>Withdrawal Amount:</label>
    <input type="number" id="withdraw">

    <button onclick="calculateBalance()">Submit</button>

    <div id="result"></div>
</div>

<script>
function calculateBalance() {
    let name = document.getElementById("name").value;
    let principal = parseFloat(document.getElementById("principal").value);
    let withdraw = parseFloat(document.getElementById("withdraw").value);

    let result = document.getElementById("result");

    if (withdraw > principal) {
        result.innerHTML = "<p style='color:red;'>Insufficient Balance!</p>";
    } else {
        let balance = principal - withdraw;

        result.innerHTML = `
            <h3>Account Details</h3>
            <p><strong>Customer Name:</strong> ${name}</p>
            <p><strong>Principal Amount:</strong> ${principal}</p>
            <p><strong>Withdrawal Amount:</strong> ${withdraw}</p>
            <p><strong>Remaining Balance:</strong> ${balance}</p>
        `;
    }
}
</script>

</body>
</html>
