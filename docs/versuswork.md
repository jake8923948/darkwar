#Alliance Duel Guide by <span style="color: orange;">[RTI] Derto</span>

<div id="versus-timer" style="border: 1px solid #; padding: 10px; border-radius: 5px; background-color: #1a1a1a; margin-bottom: 20px;">
  <h3 style="color: #; margin-top: 0;"></h3>
  
  <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
    <div>
      <p><strong>🕒 Server Time:</strong></p>
      <p><strong>📅 Today's Event:</strong></p>
      <p><strong>⏱️  Until Reset:</strong></p>
    </div>
    <div>
      <p id="current-time" style="font-family: monospace;">--:--:--</p>
      <p id="todays-event" style="font-weight: bold; color: #FFA500;">Loading...</p>
      <p id="countdown" style="font-family: monospace; font-size: 1.1em;">--h --m --s</p>
    </div>
  </div>
</div>

<script>
  // Event section anchor links
  const eventAnchors = {
    "Shelter Expansion": "#shelter",
    "Hero Initiative": "#hero",
    "Keep Progressing": "#progress",
    "Arms Expert": "#arms-expert-thursday",
    "All Round Progress": "#all-round-progress-friday",
    "Enemy Buster": "#enemy-buster"
  };

  // Event schedule (Monday=0 to Sunday=6)
  const eventSchedule = {
    0: "🏗️ Shelter Expansion",
    1: "🦸 Hero Initiative",
    2: "🚀 Keep Progressing", 
    3: "⚙️ Arms Expert",
    4: "🔄 All Round Progress",
    5: "💥 Enemy Buster",
    6: "📦 Preparation Day"
  };
  function updateTimer() {
    const now = new Date();
    const utcTime = now.getTime() + (now.getTimezoneOffset() * 60000);
    const serverTime = new Date(utcTime - (2 * 3600000)); // UTC-2 adjustment
    
    // Format current time
    document.getElementById('current-time').textContent = 
      serverTime.toLocaleTimeString('en-GB', {
        hour12: false,
        hour: '2-digit',
        minute: '2-digit',
        second: '2-digit'
      }) + " | " + 
      serverTime.toLocaleDateString('en-GB', {
        weekday: 'long', 
        month: 'short',
        day: 'numeric'
      });

    // Show today's event (with emoji)
    const dayOfWeek = serverTime.getDay();
    document.getElementById('todays-event').textContent = eventSchedule[dayOfWeek];

    // Calculate time until next reset (00:00 UTC-2)
    const nextReset = new Date(serverTime);
    nextReset.setDate(nextReset.getDate() + 1);
    nextReset.setHours(0, 0, 0, 0);
    
    const diff = nextReset - serverTime;
    const hours = Math.floor(diff / (1000 * 60 * 60)).toString().padStart(2, '0');
    const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60)).toString().padStart(2, '0');
    const seconds = Math.floor((diff % (1000 * 60)) / 1000).toString().padStart(2, '0');

    document.getElementById('countdown').textContent = 
      `${hours}h ${minutes}m ${seconds}s`;
    
    // Flash effect at 1-hour mark
    if (hours === '01' && minutes === '00') {
      document.getElementById('countdown').style.animation = 'blink 1s infinite';
    }
  }

  // Update every second
  updateTimer();
  setInterval(updateTimer, 1000);
</script>

<style>
  @keyframes blink {
    0% { color: inherit; }
    50% { color: #FF4500; }
    100% { color: inherit; }
  }
</style>
---

##🏗️  Shelter Expansion (Monday) {#shelter}
Maximize your score from the start, depending on what's available. For me, who lives in France, the reset happens at 2 a.m. So, I start my vehicles harvesting resources on Sunday evening, before going to sleep. When I wake up, I already have 1 million points, which is the minimum recommended per day in our alliance. But I'm aiming for 2 million, to get all the rewards. Here's how I do it: I start with research requiring Wisdom Medals, prioritizing the Duel tree. Each research in this tree increases my point gains for future duels, so it's a strategic investment. On Mondays, I use my research accelerators to finish everything I start, whether research or building. This allows me to earn as many points as possible for each CP (power) I obtain. Finally, I end the day by starting long builds, lasting more than 7 days,to prepare for the following days.

---

##🦸 Hero Initiative (Tuesday) {#hero}
A simple day, which doesn't require much playtime. I start by doing my basic in-game routine: Spend my energy Complete radar quests Collect daily rewards Then, my goal for the day is the following: Reach at least 1 million points, or even 2 million if possible. Depending on your progress and your account, the difficulty of this day can vary. For example, on my F2P farm account, I sometimes stop at 1 million-so you can do it too, especially since you have the daily rewards and the advantage of being on RTI. Here's my method:I use my recruitment tickets to advance. Based on my score, I raise my heroes' stars in this order: First the blues, Then the purples, And finally the yellows. Note: The goal isn't to empty your entire bag today. If you reach 1 million without using any yellow fragments, great! Contact me with: Your stock of yellow fragments. The current point bonus for each fragment use. I'll tell you whether it's worth using them or not. For example  if you exceed 1.4 million, the excess would be lost. So ifyou can't reach 2 million, stop at 1 million.

---
##🚀 Keep Progressing (Wednesday) {#progress}
Today's goal is to reach 2 million points by combining chest openings, truck *s, andtroop acceleration.Here's the plan for the day:Open your equipment chests. Perform 4 truck*s in an S pattern.You must have kept truck exchange tickets during the week to be able to use them today. S-shaped trucks earn points, so don't waste your tickets on lower-tier trucks. Speed up troop production. This is where you'll earn the majority of your points. Important: Prioritize promoting soldiers over training new ones. It's not the number of troops that matters, but their power. Stronger troops = more points and more effective in the game. With this strategy, reaching 2M points iscompletely doable without too much pressure, if you've managed your resources well beforehand.

---

##⚙️ Arms Expert (Thursday)
This is the easiest day, but also the most boring in terms of game time. Here's what you need to do: Upgrade your vehiclesUse your resources to increase the power of your vehicles. This is an easy source of points. Create giant zombies all day longThis is long, but it pays off well. Try to organize yourself to do them regularly. Complete your radar events. You can save them the day before (Wednesday) to have more to do today.

---

##🔄 All Round Progress (Friday)
This is the hardest day of the week, but with proper preparation, it becomes largely manageable. Here's the plan: Use your Energy Cores first.These are the ones I never asked you to use earlier in the week.Use them first today. Use your Golden Hero Shards. These are the ones I advised you to save for Tuesday. By using them wisely, you can reach 1 million or even 2 million points. Fine-tune your score with long research or construction projects. If you started research or construction projects that took more than 7 days on Monday evening, now is the time to speed them up. Be careful: Never finish a research or construction project on Friday. Plan to finish them on Monday, the time you usually log in. This will allow you to start the following week (Day 1) with a big boost of points as soon as you wake up.

---

##💥 Day 6 Enemy Buster - The Grand Finale
It's war day, time to give it your all! Today's objective: Kill enemy troops, Steal as many resources as possible, and above all... dominate the other servers! It's time to fight for 95 and honor your progress this week.A few tips: Aim for strategic targets: players with few troops defending but plenty of resources to take. Coordinate with the alliance if you need help. Stay protected between attacks if you're an easy target. No need to give points to the enemy for free! On this day, all your efforts this week are for that: to show that you're present and that you're progressing!

---
