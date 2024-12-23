<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Real-Time Ocean Plastic Cleanup</title>
    <style>
        body {
            background: linear-gradient(90deg, rgb(0, 143, 225), aqua, lightblue);
            margin: 0;
            padding: 0;
        }
        nav {
            background-color: black;
            overflow: hidden;
            box-shadow: 6px 12px white;
        }
        nav ul {
            list-style-type: none;
            display: flex;
            margin: 0;
            padding: 10px;
            text-align: center;
            justify-content: center;
        }
        nav ul li {
            padding: 0;
            font-size: 20px;
        }
        nav ul li a {
            padding: 10px;
            font-size: 25px;
            text-decoration: none;
            color: white;
            align-items: center;
            text-align: center;
        }
        pre {
            color: white;
            background-color: black;
            font-style: bold;
            text-align: center;
        }
        main {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 20px;
            align-items: center;
            text-align: center;
        }
        .card {
            background-color: aliceblue;
            width: 270px;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 4px 8px pink;
            box-sizing: 100px;
            height: 210px;
        }
        button {
            background-color: rgb(232, 146, 146);
            color: white;
            padding: 30px;
            border-radius: 100px;
            display: flex;
            box-sizing: initial;
            align-items: center;
            text-align: center;
            width: 230px;
        }
        button:hover {
            background-color: rgb(227, 158, 209);
            color: black;
        }
        .card2 {
            color: black;
            font-style: normal;
            background-color: white;
            padding: 10px;
            border-radius: 10px;
            align-items: center;
            text-align: center;
            margin: 50px;
            height: 230px;
        }
        .dashboard {
            color: black;
            background-color: rgb(240, 240, 163);
            padding: 10px;
            border-radius: 5px;
            align-items: center;
            text-align: center;
            margin: 4px;
            width: 250px;
            height: 25px;
        }
        .chart-container {
            background-color: aliceblue;
            width: 570px;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 4px 8px pink;
            box-sizing: 100px;
            height: 400px;
        }
        canvas {
            width: 100%;
            height: 200%;
        }
    </style>
</head>
<body>
    <nav>
        <h1><ul><li><a href="#">Real-Time Ocean Plastic Cleanup</a></li></ul></h1>
        <h3><pre>Monitor Cleanup Progress and Environmental Impact</pre></h3>
    </nav>
    <main>
        <!-- Live Data Section for Cleanup Stats -->
        <div class="card" id="liveData">
            <h3>Live Cleanup Data</h3>
            <p><b>Current Location:</b> <span id="location">Lat: 40.7128° N, Lon: 74.0060° W</span></p>
            <script>
                const locationElement = document.getElementById("location");
                function updateLocation() {
                    locationElement.textContent = `Lat: ${(Math.random() * 180 - 90).toFixed(4)}° N, Lon: ${(Math.random() * 360 - 180).toFixed(4)}° W`;
                }
                setInterval(updateLocation, 2000); // Update location every 2 seconds
            </script>
             <p><b>Plastic Collected:</b> <span id="plasticAmount">12.5</span> kg</p>
            <script>
                const plasticAmountElement = document.getElementById("plasticAmount");
                function updatePlasticAmount() {
                    plasticAmountElement.textContent = ((Math.random() * 50) + 1).toFixed(1); // Simulate plastic collected between 1 and 50 kg
                }
                setInterval(updatePlasticAmount, 5000); // Update collected plastic every 5 seconds
            </script>
            <p><b>Cleanup Device Status:</b> <span style="color:black;">Active</span></p>
        </div>
        <!-- Alerts for Cleanup -->
        <div class="card2" id="SensoryAlerts">
            <h3>Cleanup Alerts</h3>
            <div class="dashboard">Plastic Density: High</div>
            <div class="dashboard1">Cleanup Device Operational</div>
            <div class="dashboard2">Alert: Ocean Trash Accumulation!</div>
            <div class="dashboard3">Device Battery: 75%</div>
        </div>
        <!-- Graphs for Tracking Cleanup Progress -->
        <div class="chart-container">
            <h1>Cleanup Progress Graph</h1>
            <canvas id="cleanupChart"></canvas>
            <script src=https://web-api-me35.onrender.com"></script>
            <script>
                const ctx = document.getElementById('cleanupChart').getContext('2d');
                const cleanupData = [5, 10, 15, 20, 25];
                const cleanupChart = new Chart(ctx, {
                type: 'line',
                data: {
                    labels: ['1m', '2m', '3m', '4m', '5m'],
                        datasets: [{
                            label: 'Plastic Collected (k g)',
                            data:cleanupData,
                            borderColor: '#33FF57', // Green
                            fill: true,
                            backgroundColor: 'rgba(51, 255, 87, 0.2)',
                        }]
                    }
                });
                    function updateGraph() {
                    const collectedPlastic = (Math.random() * 10 + 5).toFixed(1); // Simulate collection between 5 and 15 kg
                    cleanupData.push(collectedPlastic);
                    cleanupData.shift(); // Remove the oldest data point
                    cleanupChart.update();
                }
                setInterval(updateGraph, 10000); // Update graph every 10 seconds
            </script>
        </div>
        </main>

</body>
</html>
