# Troop Camps

The Troop Camps are where you train the different style of troops, shooters, fighers and riders,
to attack enemies. Upgrading it increases your Combat Power (CP) and unlocks higher tiers of each faction.
Since all 3 camps have the same time and RSS cost, the below values apply to all of them


## Upgrade Requirements

| Level | Cap   |  CP                                    | Time             | Resource Cost   |
|-------|-------|--------------------------------------|------------------|-------------------|
| 1     | -     | 1,800                                | -                | -                 |
| 2     | -     | 3,600                                | -                | -                 |
| 3     | -     | 5,400                                | -                | -                 |
| 4     | -     | 7,200                                | -                | -                 |
| 5     | -     | 9,000                                | -                | -                 |
| 6     | -     | 11,500                               | -                | -                 |
| 7     | -     | 15.300                               | -                | -                 |
| 8     | -     | 20.200                               | -                | -                 |
| 9     | -     | 28.100                               | -                | -                 |
| 10    | -     | 37.500                               | 1h 27m           | 330k              |
| 11    | -     | 49.400                               | 4h 52m           | 550k              |
| 12    | -     | 63.700                               | -                | -                 |
| 13    | -     | 79.400                               | -                | -                 |
| 14    | -     | 98.000                               | 3h 25m           | 2.2M                 |
| 15    | -     | 120.100                              | 4h 26m           | 3M                 |
| 16    | -     | 148,800                              | 7h 33m           | 4M                 |
| 17    | -     | 182,900                              | -                | -                 |
| 18    | -     | 221,700                              | -                | -                 |
| 19    | 29    | 268,700                              | -                | -                 |
| 20    | 30    | 323,900                              | 20h 25m 15s      | 14M               |
| 21    | 31    | 389,200                              | -                | -                 |
| 22    | 32    | 472,800                              | 1d 15h 49m 13s   | 26.2M             |
| 23    | 33    | 572,100                              | 2d 07h 44m 54s   | 32.5M             |
| 24    | 34    | 692,300                              | 3d 06h 02m 51s   | 43.4M             |
| 25    | 35    | 838,300                              | 4d 13h 15m 59s   | 60.4M             |
| 26    | 36    | 999,500                              | 5d 05h 39m 23s   | 72.4M             |
| 27    | 37    | 1,185,400                            | 6d 06h 47m 16s   | 96.8M             |
| 28    | 38    | 1,396,900                            | 7d 05h 24m 21s   | 132M              |
| 29    | 39    | 1,633,300                            | 8d 07h 25m 00s   | 167.2M            |
| 30    | 40    | 1,901,100                            | -                | -                 |

---

## Calculator!
<div style="
  background: linear-gradient(135deg, #1e1e1e 0%, #2a2a2a 100%);
  border: 1px solid #444;
  border-radius: 8px;
  padding: 25px;
  margin: 30px 0;
  box-shadow: 0 4px 12px rgba(0,0,0,0.3);
  text-align: center;
">
  <h3 style="
    color: #FF6B00;
    font-family: 'Eater', cursive;
    text-shadow: 0 0 8px rgba(255,107,0,0.5);
    margin-bottom: 25px;
    font-size: 1.8em;
  ">🏗️ Building Cost Calculator</h3>

  <div style="
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin: 30px 0;
    text-align: left;
  ">
    <!-- Calculator Inputs -->
    <div style="background: rgba(42,42,42,0.7); padding: 15px; border-radius: 6px;">
      <h4 style="color: #FFA366; margin-top: 0; border-bottom: 1px solid #444; padding-bottom: 8px;">Calculate Your Costs</h4>
      <div style="margin-bottom: 12px;">
        <label style="display: block; color: #e0e0e0; margin-bottom: 5px;">Current Level:</label>
        <input type="number" id="currentLevel" min="1" max="30" style="
          width: 100%;
          padding: 8px;
          background: #333;
          border: 1px solid #555;
          border-radius: 4px;
          color: white;
        ">
      </div>
      <div style="margin-bottom: 12px;">
        <label style="display: block; color: #e0e0e0; margin-bottom: 5px;">Target Level:</label>
        <input type="number" id="targetLevel" min="1" max="30" style="
          width: 100%;
          padding: 8px;
          background: #333;
          border: 1px solid #555;
          border-radius: 4px;
          color: white;
        ">
      </div>
      <button onclick="calculateCosts()" style="
        background: linear-gradient(to right, #FF6B00, #FF8C00);
        color: white;
        border: none;
        padding: 10px 15px;
        border-radius: 4px;
        cursor: pointer;
        width: 100%;
        font-weight: bold;
        transition: all 0.2s;
      ">Calculate</button>
    </div>

    <!-- Results Display -->
    <div style="background: rgba(42,42,42,0.7); padding: 15px; border-radius: 6px;">
      <h4 style="color: #FFA366; margin-top: 0; border-bottom: 1px solid #444; padding-bottom: 8px;">Estimated Costs</h4>
      <div style="margin-bottom: 10px;">
        <span style="color: #e0e0e0;">Total Time:</span>
        <span id="totalTime" style="color: #FF6B00; float: right; font-weight: bold;">-</span>
      </div>
      <div style="margin-bottom: 10px;">
        <span style="color: #e0e0e0;">Total Wood:</span>
        <span id="totalWood" style="color: #8BC34A; float: right; font-weight: bold;">-</span>
      </div>
      <div style="margin-bottom: 10px;">
        <span style="color: #e0e0e0;">Total Stone:</span>
        <span id="totalStone" style="color: #9E9E9E; float: right; font-weight: bold;">-</span>
      </div>
      <div style="margin-bottom: 10px;">
        <span style="color: #e0e0e0;">Total Iron:</span>
        <span id="totalIron" style="color: #607D8B; float: right; font-weight: bold;">-</span>
      </div>
    </div>
  </div>

  <div style="margin-top: 20px;">
    <p style="color: #FFA366; font-size: 1.1em; margin-bottom: 20px;">
      Found incorrect data? Help improve this guide!
    </p>
    <div style="display: flex; justify-content: center; gap: 15px;">
      <div style="
        background-color: #2A2A2A;
        border-radius: 5px;
        padding: 10px 20px;
      ">
        <span style="
          color: #FF6B00;
          font-weight: bold;
          font-size: 1.2em;
        ">[RTI] Jake</span>
      </div>
      <a href="https://discordapp.com/users/401691637434023938" style="text-decoration: none;">
        <div style="
          background-color: #2A2A2A;
          border-radius: 5px;
          padding: 10px 20px;
          display: flex;
          align-items: center;
          gap: 8px;
        ">
          <img src="https://www.svgrepo.com/show/353655/discord-icon.svg" 
               alt="Discord" 
               width="20" 
               height="20">
          <span style="
            color: #5865F2;
            font-weight: bold;
            font-size: 1.2em;
          ">Jake7761</span>
        </div>
      </a>
    </div>
  </div>
</div>

<script>
// Sample data - replace with your actual building cost data
const buildingCosts = {
  1: { time: 0, wood: 0, stone: 0, iron: 0 },
  2: { time: 0, wood: 0, stone: 0, iron: 0 },
  3: { time: 0, wood: 0, stone: 0, iron: 0 },
  4: { time: 0, wood: 0, stone: 0, iron: 0 },
  5: { time: 0, wood: 0, stone: 0, iron: 0 },
  6: { time: 0, wood: 0, stone: 0, iron: 0 },
  7: { time: 0, wood: 0, stone: 0, iron: 0 },
  8: { time: 0, wood: 0, stone: 0, iron: 0 },
  9: { time: 0, wood: 0, stone: 0, iron: 0 },
  10: { time: 0, wood: 0, stone: 0, iron: 0 },
  11: { time: 0, wood: 0, stone: 0, iron: 0 },
  12: { time: 0, wood: 0, stone: 0, iron: 0 },
  13: { time: 0, wood: 0, stone: 0, iron: 0 },
  14: { time: 0, wood: 0, stone: 0, iron: 0 },
  15: { time: 0, wood: 0, stone: 0, iron: 0 },
  16: { time: 0, wood: 0, stone: 0, iron: 0 },
  17: { time: 0, wood: 0, stone: 0, iron: 0 },
  18: { time: 0, wood: 0, stone: 0, iron: 0 },
  19: { time: 0, wood: 0, stone: 0, iron: 0 },
  20: { time: 73515, wood: 14000000, stone: 14000000, iron: 14000000 },
  21: { time: 0, wood: 0, stone: 0, iron: 0 },
  22: { time: 142153, wood: 26200000, stone: 26200000, iron: 26200000 },
  23: { time: 194694, wood: 32500000, stone: 32500000, iron: 32500000 },
  24: { time: 272571, wood: 43400000, stone: 43400000, iron: 43400000 },
  25: { time: 393359, wood: 58800000, stone: 58800000, iron: 58800000 },
  26: { time: 455963, wood: 72400000, stone: 72400000, iron: 72400000 },
  27: { time: 550036, wood: 96800000, stone: 96800000, iron: 96800000 },
  28: { time: 617061, wood: 132000000, stone: 132000000, iron: 132000000 },
  29: { time: 720300, wood: 167200000, stone: 167200000, iron: 167200000 },
  30: { time: 0, wood: 0, stone: 0, iron: 0 }
};

function calculateCosts() {
  const current = parseInt(document.getElementById('currentLevel').value);
  const target = parseInt(document.getElementById('targetLevel').value);
  
  if (isNaN(current) || isNaN(target) || current >= target) {
    alert("Please enter valid level range (current < target)");
    return;
  }

  let totalTime = 0;
  let totalWood = 0;
  let totalStone = 0;
  let totalIron = 0;

  for (let level = current + 1; level <= target; level++) {
    if (buildingCosts[level]) {
      totalTime += buildingCosts[level].time;
      totalWood += buildingCosts[level].wood;
      totalStone += buildingCosts[level].stone;
      totalIron += buildingCosts[level].iron;
    }
  }

  // Format time
  const days = Math.floor(totalTime / 86400);
  const hours = Math.floor((totalTime % 86400) / 3600);
  const minutes = Math.floor((totalTime % 3600) / 60);
  const seconds = totalTime % 60;
  
  let timeString = "";
  if (days > 0) timeString += `${days}d `;
  if (hours > 0) timeString += `${hours}h `;
  if (minutes > 0) timeString += `${minutes}m `;
  if (seconds > 0 || timeString === "") timeString += `${seconds}s`;

  // Update results
  document.getElementById('totalTime').textContent = timeString;
  document.getElementById('totalWood').textContent = totalWood.toLocaleString();
  document.getElementById('totalStone').textContent = totalStone.toLocaleString();
  document.getElementById('totalIron').textContent = totalIron.toLocaleString();
}
</script>


---
