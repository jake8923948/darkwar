# Troop Camps

The Troop Camps are where you train the different style of troops, shooters, fishers and riders, to attack enemies. Upgrading it increases your Combat Power (CP) and unlocks higher tiers of each faction. Since all 3 camps have the same time and RSS cost, the below values apply to all of them.

<div style="
  background: linear-gradient(135deg, #1e1e1e 0%, #2a2a2a 100%);
  border: 1px solid #444;
  border-radius: 8px;
  padding: 15px;
  margin: 20px 0;
  box-shadow: 0 2px 8px rgba(0,0,0,0.2);
">

  <h3 style="color: #FFA366; margin-top: 0;">Boost Calculator</h3>
  
  <div style="display: flex; align-items: center; gap: 15px; margin-bottom: 15px;">
    <label style="color: #e0e0e0; min-width: 120px;">Your Speed Boost:</label>
    <input type="number" id="boostPercent" min="0" max="100" value="0" style="
      padding: 8px 12px;
      background: #333;
      border: 1px solid #555;
      border-radius: 4px;
      color: white;
      width: 80px;
    "> %
  </div>
  
  <div style="display: flex; align-items: center; gap: 15px;">
    <label style="color: #e0e0e0; min-width: 120px;">Your RSS Reduction:</label>
    <input type="number" id="rssReduction" min="0" max="100" value="0" style="
      padding: 8px 12px;
      background: #333;
      border: 1px solid #555;
      border-radius: 4px;
      color: white;
      width: 80px;
    "> %
  </div>
</div>

## Upgrade Requirements

| Level | Cap    | CP    | Time   | Resource Cost |
|---|---|---|---|---|
| 1    | -    | 1,800    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 2    | -    | 3,600    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 3    | -    | 5,400    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 4    | -    | 7,200    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 5    | -    | 9,000    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 7    | -    | 15,300    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 8    | -    | 20,200    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 9    | -    | 28,100    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 10    | -    | 37,500    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |
| 11    | -    | 49,400    | <span class="time-value">-</span>    | <span class="rss-value">-</span>    |

<script>
// Base costs - replace with your actual values
const baseCosts = {
  1: { time: 452363, rss: 80000000 }, // Hospital base RSS: 80M
  2: { time: 619461, rss: 150000000 },
  3: { time: 267592, rss: 15909000 },
  // Add all levels with their base time (in seconds) and resource costs
  11: { time: 86400, rss: 500000 }
};

function updateTable() {
  const boostPercent = parseFloat(document.getElementById('boostPercent').value) || 0;
  const rssReduction = parseFloat(document.getElementById('rssReduction').value) || 0;
  
  // Time calculation (boost reduction)
  document.querySelectorAll('.time-value').forEach((el, index) => {
    const level = index + 1;
    if (baseCosts[level]) {
      const exactTime = baseCosts[level].time / (1 + (boostPercent / 100));
      const seconds = Math.trunc(exactTime);
      el.textContent = formatTime(seconds);
    }
  });

  // RSS calculation (cost reduction)
  document.querySelectorAll('.rss-value').forEach((el, index) => {
    const level = index + 1;
    if (baseCosts[level]) {
      const baseRSS = baseCosts[level].rss;
      // CORRECTED: Use rssReduction instead of boostPercent for resources
      const reducedRSS = Math.round(baseRSS * (1 - (rssReduction / 100)));
      // Format with conditional decimal
      const formatted = (reducedRSS / 1000000).toFixed(1).replace(/\.0$/, '');
      el.textContent = `${formatted}M`;
    }
  });
}

function formatTime(totalSeconds) {
  const days = Math.trunc(totalSeconds / 86400);
  const hours = Math.trunc((totalSeconds % 86400) / 3600);
  const minutes = Math.trunc((totalSeconds % 3600) / 60);
  const seconds = totalSeconds % 60;
  
  const parts = [];
  if (days > 0) parts.push(`${days}d`);
  if (hours > 0) parts.push(`${hours}h`);
  if (minutes > 0) parts.push(`${minutes}m`);
  if (seconds > 0 || parts.length === 0) parts.push(`${seconds}s`);
  
  return parts.join(' ');
}

// Initialize with base values
document.getElementById('boostPercent').addEventListener('input', updateTable);
document.getElementById('rssReduction').addEventListener('input', updateTable);
updateTable();
</script>
