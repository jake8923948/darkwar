#Alliance Duel Guide by <span style="color: orange;">[RTI] Derto</span>

<div id="versus-timer" style="width: 100%; border: 2px solid #FFA500; border-radius: 8px; background-color: #1a1a1a; padding: 15px; margin-bottom: 20px; font-family: 'Arial', sans-serif; box-sizing: border-box;">
  <div style="text-align: center; margin-bottom: 15px;">
    <div style="color: #FFA500; font-size: 1.5em; font-weight: bold; line-height: 1.2;">Versus Timer</div>
  </div>
  
  <div style="display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 10px;">
    <div style="color: #ccc; min-width: 80px;">Server Time:</div>
    <div id="current-time" style="font-family: 'Courier New', monospace; color: white; text-align: right;">
      18:46:23 | Tue<br>1 Apr
    </div>
  </div>
  
  <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px;">
    <div style="color: #ccc; min-width: 80px;">Today's Event:(tap -->)</div>
    <div id="todays-event" style="text-align: right;">
      <a href="#keep-progressing" style="color: #FFA500; text-decoration: none; font-weight: bold;">Keep<br>Progressing</a>
    </div>
  </div>
  
  <div style="display: flex; justify-content: space-between; align-items: center;">
    <div style="color: #ccc; min-width: 80px;">Until Reset:</div>
    <div id="countdown" style="font-family: 'Courier New', monospace; font-size: 1.2em; color: #FF6347; font-weight: bold; text-align: right;">
      05h 13m 36s
    </div>
  </div>
</div>
<script>
  // Event section anchor links
  const eventAnchors = {
    "Shelter Expansion": "#shelter-expansion",
    "Hero Initiative": "#hero-initiative",
    "Keep Progressing": "#keep-progressing",
    "Arms Expert": "#arms-expert",
    "All Round Progress": "#all-round-progress",
    "Enemy Buster": "#enemy-buster"
  };

  // Event schedule (Monday=0 to Sunday=6)
  const eventSchedule = {
    0: "🏗️  Shelter Expansion",
    1: "🦸 Hero Initiative",
    2: "🚀 Keep Progressing", 
    3: "⚙️  Arms Expert",
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
        weekday: 'short',
        month: 'short',
        day: 'numeric'
      });
    let dayOfWeek = serverTime.getDay() - 1;
    if (dayOfWeek < 0) dayOfWeek = 6; // Handle Sunday wrap-around

    const eventText = eventSchedule[dayOfWeek];
    const eventName = eventText.replace(/^[^\w]+/, "").trim();
    const eventLink = document.getElementById('todays-event').firstElementChild;
    
    eventLink.textContent = eventText;
    eventLink.href = eventAnchors[eventName] || "#";

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
    const countdownElement = document.getElementById('countdown');
    if (hours === '01' && minutes === '00') {
      countdownElement.style.animation = 'blink 1s infinite';
    } else {
      countdownElement.style.animation = 'none';
    }
  }

  // Initialize and update every second
  updateTimer();
  setInterval(updateTimer, 1000);
</script>

---

##🏗️  Shelter Expansion (Monday) {#shelter-expansion}
Maximize your score from the start, depending on what's available. For me, who lives in France,
the reset happens at 2 a.m. So, I start my harvesting resource tiles on Sunday evening, before
going to sleep. When I wake up, I already have 1 million points, which is the minimum recommended
per day in our alliance. But I'm aiming for 2 million, to get all the rewards. Here's how I do it:
I start with research requiring Wisdom Medals, prioritizing the "Duel" tree. Each research in this tree
increases my point gains for future duels, so it's a strategic investment. On Mondays, I use my research
accelerators to finish everything I start, whether research or building. This allows me to earn as many
points as possible for each CP (power) I obtain. Finally, I end the day by starting long builds, lasting
more than 7 days,to prepare for the following days.

---

##🦸 Hero Initiative (Tuesday) {#hero-initiative}
A simple day, which doesn't require much playtime. I start by doing my basic in-game routine: 
Spend my energy, Complete radar quests, Collect daily rewards. Then, my goal for the day is the following:
Reach at least 1 million points, or even 2 million if possible. Depending on your progress and your account,
the difficulty of this day can vary. For example, on my F2P farm account, I sometimes stop at 1 million, so 
you can do it too, especially since you have the daily rewards and the advantage of being in RTI. Here's my
method: I use my recruitment tickets to advance. Based on my score, I raise my heroes' stars in this order: 
First the blues, Then the purples, And finally the yellows. Note: The goal isn't to empty your entire bag today. 
If you reach 1 million without using any yellow fragments, great! Contact me in-game or on Discord with the number
of yellow fragments you have and your points for each fragment used. I'll tell you whether it's worth using them 
or not. For example, if you exceed 1.4 million, the excess would be lost. So if you can't reach 2 million, stop at
1 million to save the yellow fragments for friday's event.

---
##🚀 Keep Progressing (Wednesday) {#keep-progressing}
Today's goal is to reach 2 million points by combining chest openings, sending S-tier trucks, and troop acceleration.
Here's the plan for the day: Open your equipment chests. Send 4 trucks that are S-tiered. You must have stacked truck 
exchange tickets during the week to be able to use them today. S-tiered trucks earn points, so don't waste your 
tickets on lower-tier trucks. Speed up troop production. This is where you'll earn the majority of your points. 
Important: Prioritize promoting soldiers over training new ones. It's not the number of troops that matters, but
their power. Stronger troops = more points and more effective in the game. With this strategy, reaching 2M points
is completely doable without too much pressure, if you've managed your resources well beforehand.

---

##⚙️ Arms Expert (Thursday) {#arms-expert}
This is the easiest day, but also the most boring in terms of game time. Here's what you need to do: 
Upgrade your vehicles. Use your resources to increase the power of your vehicles. This is an easy source 
of points. Create boomer rallies all day long. This is time consuming, but it pays off well. Try to organize yourself 
to do them regularly. Complete your radar events. You can save them the day before (on Wednesday) to have more
to do today thus earning more points.

---

##🔄 All Round Progress (Friday) {#all-round-progress}
This is the hardest day of the week, but with proper preparation, it becomes largely manageable. 
Here's the plan: Use your Energy Cores first. These are the ones I never asked you to use earlier 
in the week. Use them first today. Use your Golden Hero Shards. These are the ones I advised you to 
save from Tuesday. By using them wisely, you can reach 1 million or even 2 million points. Fine-tune 
your score with long research or construction projects. If you started research or construction 
projects that took more than 7 days on Monday evening, now is the time to speed them up. Be careful: 
Never finish a research or construction project on Friday. Plan to finish them on Monday, the time you 
usually log in. This will allow you to start the following week (Day 1) with a big boost of points as 
soon as you wake up.

---

##💥 Day 6 Enemy Buster - The Grand Finale {enemy-buster}
It's war day, time to give it your all! Today's objective: Kill enemy troops, steal as many 
resources as possible, and above all... dominate the other servers! It's time to fight for 95 and 
honor your progress this week. A few tips: Aim for strategic targets: players with few troops defending 
but plenty of resources to take. Coordinate with the alliance if you need help. Stay protected between 
attacks if you're an easy target. No need to give points to the enemy for free! On this day, all your 
efforts this week are for that: to show that you're present and that you're progressing!

---
