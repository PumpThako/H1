<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wi-Fi Hacking Simulation</title>
    <style>
        body {
            background-color: #000;
            color: #00FF00; /* Green text for hacking theme */
            font-family: 'Courier New', Courier, monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            position: relative;
        } 

        .code-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: -1;
            color: #00FF00;
            white-space: nowrap;
            font-size: 14px;
        }

        .profile-container {
            background-color: rgba(50, 50, 50, 0.8);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.5);
            width: 300px;
            text-align: center;
            position: relative;
            z-index: 1;
        }

        .profile-img {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 15px;
        }

        .online-status {
            width: 20px;
            height: 20px;
            background-color: #4CAF50; /* Green for online status */
            border-radius: 50%;
            position: absolute;
            bottom: -5px;
            right: -5px;
            border: 2px solid #fff;
        }

        .profile-name {
            font-size: 24px;
            margin: 10px 0;
        }

        .profile-bio {
            font-size: 14px;
            color: #777;
        }

        /* Blinking cursor */
        .cursor {
            display: inline-block;
            width: 10px;
            height: 20px;
            background-color: #00FF00;
            animation: blink 1s step-end infinite;
        }

        @keyframes blink {
            0%, 100% { opacity: 0; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>

    <!-- Background with running hacking code -->
    <div class="code-background" id="codeBackground"></div>

    <!-- Profile Container -->
    <div class="profile-container">
        <div class="online-status"></div>
        <img class="profile-img" src="https://via.placeholder.com/100" alt="Profile Image">
        <h2 class="profile-name">Hacker Name</h2>
        <p class="profile-bio">Attention: Your system has been compromised.

A breach has occurred, and sensitive information is at risk.

Details of the breach:
- Accessed data includes:
  - Personal Identifiable Information (PII)
  - Financial records
  - Login credentials for various accounts

What you need to do:
1. Change all your passwords immediately.
2. Enable two-factor authentication on all accounts.
3. Monitor your financial statements for any unauthorized transactions.
4. Contact your bank and report the breach.

If you wish to prevent further actions, follow these steps:
- Send a payment of $1000 in Bitcoin to the following address:
  [Bitcoin Address]
- Failure to comply will result in the data being leaked online.

Remember, this is your only chance to protect your information.
Act fast, time is running out.</p>
    </div>

    <script>
        const codeLines = [
            "Scanning Wi-Fi networks...",
            "Network found: Home_Network | Signal: Strong",
            "Attempting to connect...",
            "Bypassing security protocols...",
            "Connected to Home_Network!",
            "IP Address assigned: 192.168.1.5",
            "Collecting data...",
            "Accessing sensitive files...",
            "Dumping passwords...",
            "Wi-Fi password: secretPassword123",
            "Scanning for vulnerabilities...",
            "Uploading malicious payload...",
            "Disconnecting from Home_Network...",
            "All data collected successfully."
        ];

        const codeBackground = document.getElementById('codeBackground');

        // Function to type out the code lines
        function typeCode(lines) {
            lines.forEach((line, index) => {
                setTimeout(() => {
                    typeLine(line);
                }, index * 2000); // Wait 2 seconds between each line
            });
        }

        // Function to type out a single line with blinking cursor
        function typeLine(line) {
            let currentIndex = 0;
            const lineContainer = document.createElement('div');
            codeBackground.appendChild(lineContainer);
            const cursor = document.createElement('span');
            cursor.className = 'cursor';
            lineContainer.appendChild(cursor);

            const interval = setInterval(() => {
                if (currentIndex < line.length) {
                    lineContainer.insertBefore(document.createTextNode(line[currentIndex]), cursor);
                    currentIndex++;
                } else {
                    clearInterval(interval);
                    // Remove the cursor when finished typing the line
                    cursor.remove();
                    setTimeout(() => {
                        lineContainer.innerHTML += '<br>'; // New line after finishing the line
                    }, 500); // Slight delay before the new line
                }
            }, 100); // Typing speed (100ms per character)
        }

        // Start typing the code lines
        typeCode(codeLines);
    </script>

</body>
</html>