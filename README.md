<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="theme-color" content="#6200EA">
    <title>Bhagyavan - Lucky Draw App</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        body {
            margin: 0;
            font-family: 'Arial', sans-serif;
            background-color: #f4f6f9;
            color: #333;
        }

        header {
            background-color: #6200EA;
            color: white;
            text-align: center;
            padding: 1.5rem;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

        header h1 {
            font-size: 2rem;
        }

        .container {
            padding: 1rem;
            max-width: 1200px;
            margin: auto;
        }

        .wallet {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #fff;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            margin-bottom: 1rem;
        }

        .wallet span {
            font-size: 1.5rem;
            font-weight: bold;
            color: #333;
        }

        .wallet button {
            background-color: #FF9800;
            border: none;
            color: white;
            padding: 0.75rem 2rem;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.3s;
        }

        .wallet button:hover {
            background-color: #E68900;
        }

        .card {
            background: white;
            margin: 1rem 0;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease-in-out;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card h2 {
            font-size: 1.5rem;
            color: #333;
        }

        .card p {
            margin: 0.5rem 0;
            color: #666;
            font-size: 1rem;
        }

        .card button {
            background-color: #6200EA;
            color: white;
            border: none;
            padding: 1rem 2rem;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.3s;
            font-size: 1rem;
        }

        .card button:hover {
            background-color: #5E00D1;
        }

        .bottom-nav {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            background-color: #6200EA;
            color: white;
            display: flex;
            justify-content: space-around;
            padding: 1rem 0;
            box-shadow: 0 -4px 10px rgba(0, 0, 0, 0.1);
        }

        .bottom-nav a {
            color: white;
            text-decoration: none;
            text-align: center;
            font-size: 1rem;
        }

        .bottom-nav a i {
            display: block;
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
        }

        /* Responsive Design */
        @media (max-width: 600px) {
            header h1 {
                font-size: 1.5rem;
                padding: 1rem;
            }

            .wallet {
                flex-direction: column;
                align-items: flex-start;
                padding: 1rem;
            }

            .wallet button {
                width: 100%;
                margin-top: 1rem;
            }

            .card button {
                width: 100%;
            }

            .bottom-nav a {
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to Bhagyavan</h1>
    </header>

    <div class="container">
        <div class="wallet">
            <span id="wallet-balance">Wallet Balance: ₹500</span>
            <button onclick="addMoney()">Add Money</button>
        </div>

        <div class="card">
            <h2>Win an iPhone 14 Pro</h2>
            <p>Entry Fee: ₹100</p>
            <p>Winners: 1 Grand Prize + 5 Lucky Winners</p>
            <button onclick="joinDraw('iPhone 14 Pro', 100)">Join Draw</button>
        </div>

        <div class="card">
            <h2>Exclusive 90% Discount on Headphones</h2>
            <p>Entry Fee: ₹50</p>
            <p>Winners: 50% Participants</p>
            <button onclick="joinDraw('Headphones Discount', 50)">Join Draw</button>
        </div>
    </div>

    <div class="bottom-nav">
        <a href="#">
            <i class="fas fa-home"></i>
            Home
        </a>
        <a href="#">
            <i class="fas fa-wallet"></i>
            Wallet
        </a>
        <a href="#">
            <i class="fas fa-trophy"></i>
            Rewards
        </a>
        <a href="#">
            <i class="fas fa-user"></i>
            Profile
        </a>
    </div>

    <script>
        let walletBalance = 500;

        // Function to add money to wallet
        function addMoney() {
            let amount = prompt("Enter the amount to add to wallet:");
            if (amount && !isNaN(amount)) {
                walletBalance += parseInt(amount);
                document.getElementById("wallet-balance").textContent = `Wallet Balance: ₹${walletBalance}`;
                alert(`₹${amount} added to your wallet!`);
            } else {
                alert("Please enter a valid amount.");
            }
        }

        // Function to join a draw
        function joinDraw(drawName, fee) {
            if (walletBalance >= fee) {
                walletBalance -= fee;
                document.getElementById("wallet-balance").textContent = `Wallet Balance: ₹${walletBalance}`;
                alert(`You have successfully joined the ${drawName} draw!`);
            } else {
                alert("Insufficient balance. Please add money to your wallet.");
            }
        }
    </script>
</body>
</html>
