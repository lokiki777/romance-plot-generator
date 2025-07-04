<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Romance Plotline Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #fff4f8;
      padding: 20px;
      color: #333;
    }
    select, button {
      padding: 10px;
      margin: 10px 0;
      font-size: 16px;
    }
    #plot {
      margin-top: 20px;
      font-size: 18px;
      background: #ffe6f0;
      padding: 15px;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <h1>Romance Plotline Generator</h1>

  <label for="genre">Choose a genre:</label><br>
  <select id="genre">
    <option value="werewolf">Werewolf</option>
    <option value="mafia">Mafia</option>
    <option value="billionaire">Billionaire</option>
  </select><br>

  <label for="spice">Spice level:</label><br>
  <select id="spice">
    <option value="innocent">Innocent</option>
    <option value="spicy">Spicy</option>
  </select><br>

  <label for="setting">Setting:</label><br>
  <select id="setting">
    <option value="urban">Urban</option>
    <option value="fantasy">Fantasy</option>
  </select><br>

  <button onclick="generatePlot()">Generate Plot</button>

  <div id="plot"></div>

  <script>
    const plotDatabase = {
      werewolf_innocent_urban: [
        "A shy college girl discovers her roommate is a protective werewolf prince hiding in plain sight.",
        "He’s a motorcycle-riding lone wolf. She’s the mayor’s daughter who hates trouble... until she meets him."
      ],
      werewolf_spicy_fantasy: [
        "The Alpha of the Blood Moon Pack claims his mate on the battlefield, and she’s the enemy’s healer.",
        "Every full moon, the Alpha’s heat grows unbearable — until a rogue witch offers herself to tame the beast."
      ],
      mafia_spicy_urban: [
        "He’s the ruthless don. She’s the undercover agent sent to destroy his empire — but ends up in his bed.",
        "Kidnapped by the mafia, she expects death. What she gets is obsession... and a diamond collar."
      ],
      mafia_innocent_urban: [
        "To save her brother, she agrees to marry the mafia boss — only to find he’s a soft-hearted protector behind closed doors.",
        "He kills for power. She lives for kindness. Their worlds were never meant to collide — but fate had other plans."
      ],
      billionaire_innocent_urban: [
        "The grumpy CEO accidentally sends a love letter to his new intern.",
        "She's cleaning offices at night. He’s working late. One spilled coffee starts a fairytale."
      ],
      billionaire_spicy_urban: [
        "She signs a contract to fake-date the billionaire — but the bedroom clause wasn’t a joke.",
        "He buys the company. She’s the only one who stands up to him. He makes her his assistant... and his obsession."
      ]
    };

    function generatePlot() {
      const genre = document.getElementById('genre').value;
      const spice = document.getElementById('spice').value;
      const setting = document.getElementById('setting').value;

      const key = `${genre}_${spice}_${setting}`;
      const plotList = plotDatabase[key];

      if (plotList && plotList.length > 0) {
        const randomIndex = Math.floor(Math.random() * plotList.length);
        document.getElementById('plot').innerText = plotList[randomIndex];
      } else {
        document.getElementById('plot').innerText = "No plot found for this combo. Try a different one!";
      }
    }
  </script>
</body>
</html>
