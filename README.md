# website.github.io
!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>University Programs</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      background-color: #f4f4f9;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    .container {
      display: flex;
      justify-content: space-around;
      margin-top: 30px;
    }
    .input-box {
      width: 30%;
      padding: 10px;
      margin: 0 10px;
      border: 1px solid #ddd;
      border-radius: 5px;
    }
    button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
      border-radius: 5px;
    }
    button:hover {
      background-color: #45a049;
    }
    .output {
      margin-top: 20px;
      padding: 10px;
      background-color: #fff;
      border: 1px solid #ddd;
      border-radius: 5px;
      min-height: 100px;
      color: #333;
    }
  </style>
</head>
<body>
  <h1>University Programs</h1>

  <div class="container">
    <!-- Input Boxes for links -->
    <div>
      <input type="url" id="link1" class="input-box" placeholder="Enter Program Link 1">
      <button onclick="fetchData(1)">Fetch Data</button>
      <div id="output1" class="output"></div>
    </div>
    <div>
      <input type="url" id="link2" class="input-box" placeholder="Enter Program Link 2">
      <button onclick="fetchData(2)">Fetch Data</button>
      <div id="output2" class="output"></div>
    </div>
    <div>
      <input type="url" id="link3" class="input-box" placeholder="Enter Program Link 3">
      <button onclick="fetchData(3)">Fetch Data</button>
      <div id="output3" class="output"></div>
    </div>
  </div>

  <script>
    // Function to fetch data from the provided link
    function fetchData(boxId) {
      let link = document.getElementById(`link${boxId}`).value;
      if (!link) {
        alert('Please enter a link.');
        return;
      }
      
      // Perform an HTTP request to fetch the content of the URL
      fetch(link)
        .then(response => response.text())
        .then(data => {
          document.getElementById(`output${boxId}`).innerHTML = data;
        })
        .catch(error => {
          document.getElementById(`output${boxId}`).innerHTML = 'Unable to fetch data. Please check the link and try again.';
          console.error('Error fetching data:', error);
        });
    }
  </script>

</body>
</html>
