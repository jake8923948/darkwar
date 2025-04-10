---
title: Hi
content: "*"
---
<link href="https://fonts.googleapis.com/css2?family=Eater&family=Nosifer&family=Charm&display=swap" rel="stylesheet">
<style>
  .title-main {
    font-family: 'Nosifer', cursive;
    color: #3A0000 !important; /* Deep blood red */
    text-shadow: 
      0 0 5px #FF0000,  /* Inner glow */
      0 0 10px #800000,  /* Mid glow */
      2px 2px 4px #000;  /* Hard shadow */
    font-size: 2.8rem;
    text-align: center;
    letter-spacing: 1px;
    transition: color 0.3s;
  }

  .title-main:hover {
    color: #5E0000 !important; /* Slightly brighter on hover */
  }  
  .title-survivor {
    font-family: 'Eater', cursive;
    color: #2B0000 !important;
    font-size: 4rem;
    text-shadow: 2px 2px 4px #000, 0 0 10px #FF0000;
    text-align: center;
    letter-spacing: 2px;
    filter: drop-shadow(2px 2px 3px black);
    animation: flicker 4s infinite alternate;
  }
  
  @keyframes flicker {
    0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
      opacity: 1;
      text-shadow: 2px 2px 4px #000, 0 0 10px #FF0000;
    }
    20%, 24%, 55% {
      opacity: 0.3;
      text-shadow: 2px 2px 6px #000, 0 0 15px #FF0000;
    }
  }
</style>

<div style="text-align: center;">
  <h1 class="title-main">Welcome to the Dark War Guide! 🎮</h1>
  
  <img id="secretImage" 
       src="/images/logo.jpg" 
       alt="Dark War Logo"
       width="450"
       style="border: 2px solid #444; border-radius: 5px; cursor: pointer; transition: all 0.5s ease;"
       title="Psst... tap me! ( ͡° ͜ʖ ͡°)">
  
  <div id="lennyFace" style="
    font-size: 3rem;
    opacity: 0;
    height: 0;
    overflow: hidden;
    transform: rotate(0deg);
    transition: all 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    margin: 0;
  ">
    ( ͡° ͜ʖ ͡°)
  </div>
  <br>
  
  <h1 class="title-survivor">Welcome, Survivor!</h1>
</div>


<!-- Add this audio element (hidden) somewhere in your HTML -->
<audio id="lennySound" preload="auto">
  <source src="" type="audio/mpeg">
  Your browser doesn't support audio
</audio>

<script>
  const image = document.getElementById('secretImage');
  const lenny = document.getElementById('lennyFace');
  const lennySound = document.getElementById('lennySound');
  let isAnimating = false;

  // Preload the sound when page loads
  window.addEventListener('load', () => {
    lennySound.volume = 0.005; // Lower volume to avoid startling users
    lennySound.load();
  });

  image.addEventListener('click', function() {
    if (isAnimating) return;
    isAnimating = true;
    
    // Fade out image
    image.style.opacity = '0';
    image.style.transform = 'scale(0.5) rotate(180deg)';
    
    // Animate Lenny face with sound
    setTimeout(() => {
      lennySound.currentTime = 0; // Rewind sound if already playing
      lennySound.play().catch(e => console.log("Audio play failed:", e));
      
      lenny.style.opacity = '1';
      lenny.style.height = 'auto';
      lenny.style.margin = '20px 0';
      lenny.style.transform = 'rotate(360deg)';
      
      // Bounce effect
      setTimeout(() => {
        lenny.style.transform = 'rotate(360deg) scale(1.2)';
        setTimeout(() => lenny.style.transform = 'rotate(360deg) scale(1)', 200);
      }, 300);
    }, 500);
    
    // Reset after 4 seconds
    setTimeout(() => {
      image.style.opacity = '1';
      image.style.transform = 'scale(1) rotate(0deg)';
      lenny.style.opacity = '0';
      lenny.style.height = '0';
      lenny.style.margin = '0';
      lenny.style.transform = 'rotate(0deg)';
      isAnimating = false;
    }, 4000);
  });
</script>


---

<div style="
  background-color: #1e1e1e;
  border: 1px solid #333;
  border-radius: 5px;
  padding: 20px;
  margin: 30px 0;
  text-align: center;
">
  <h3 style="
    color: #FF6B00;
    font-family: 'Eater', cursive;
    text-shadow: 0 0 5px #000;
    margin-bottom: 25px;
  ">Help Improve This Guide!</h3>

  <p style="
    color: #FFA366;
    font-size: 1.1em;
    margin-top: 30px;
    margin-bottom: 25px;
    line-height: 1.5;
  ">I need your help to find missing data!</p>

  <p style="color: #e0e0e0; margin-bottom: 20px;">
    If you have information about time or resource costs for any building levels, please<br>
    message me in-game or on Discord(Press it!):
  </p>

  <div style="display: flex; flex-direction: column; align-items: center; gap: 8px;">
    <div style="
      background-color: #2A2A2A;
      border-radius: 3px;
      padding: 10px 15px;
      display: inline-block;
    ">
      <span style="
        color: #FF6B00;
        font-weight: bold;
        font-size: 1.3em;
        letter-spacing: 1px;
      ">[RTI] Jake</span>
    </div>

    <a href="https://discordapp.com/users/401691637434023938" style="text-decoration: none;">
      <div style="
        background-color: #2A2A2A;
        border-radius: 3px;
        padding: 10px 15px;
        display: inline-flex;
        align-items: center;
        gap: 8px;
        transition: background-color 0.2s;
      ">
        <img src="https://www.svgrepo.com/show/353655/discord-icon.svg" 
             alt="Discord" 
             width="24" 
             height="24"
             style="vertical-align: middle;">
        <span style="
          color: #5865F2;
          font-weight: bold;
          font-size: 1.3em;
          letter-spacing: 1px;
        ">Jakee7761</span>
      </div>
    </a>
  </div>
</div>


Every piece of data helps fellow survivors! Your contributions will be credited in the guide.
Whether you're a seasoned veteran or just starting your journey in **Dark War Survival**, this guide is here to help you build, upgrade, and dominate! 🌟

Below, you'll find links to detailed guides for each building in the game. From the **Watchtower** to the **Alliance Plaza**, we've got you covered with upgrade requirements, tips, and strategies to make your base unstoppable. Let's get started! 💪

---
## 🏆 [Alliance Duel Guide](versus.md) By [RTI] Derto
Every battle shapes our survival! Your duel strategies and reports help strengthen the entire alliance. Whether you're a frontline fighter or a strategic planner, this guide will help you dominate the versus arena.

Below you'll find key tactics for each duel phase. From Monday preparations to Saturday's grand finale, we cover optimal resource use and scoring strategies:

    Shelter Expansion (Monday)

    Hero Initiative (Tuesday)

    Keep Progressing (Wednesday)

    Arms Expert (Thursday)

    All Round Progress (Friday)

    Enemy Buster (Saturday Grand Finale)
---


## 📚 Building Guides

Here’s a list of all the buildings in Dark War Survival. Click on any building to learn more about its upgrades and how to maximize its potential:

- [⚔️   All Troop Camps](buildings/camps.md)
- [🔬  Research Center](buildings/research-center.md)
- [🤝  Alliance Hall](buildings/alliance-hall.md)
- [🎪  Alliance Plaza](buildings/alliance-plaza.md)
- [🏰  Watchtower](buildings/watchtower.md)
- [🎖️   Military Center](buildings/military-center.md)
- [🚧  City Gate](buildings/city-gate.md)
- [🏥  Hospital](buildings/hospital.md) *(New!)*
---

## 💡 Tips for Success

- **Plan Ahead**: Always check the upgrade requirements for your buildings and plan your resources accordingly. Don't open packs before you are ready to start a building upgrade.
- **Team Up**: Join an active alliance to get help with upgrades, alliance tech and reinforcements.
- **Balance is Key**: Don’t focus on just one type of troop or building. A balanced base is a strong base!
- **Use Boosts**: Speed-ups and resource boosts (like Megan, the Construction Hall and Library) can save you a lot of time and effort.

---

## 🛠️  Need Help?

If you have any questions or suggestions, feel free to reach out to the community or leave a comment on this guide. Together, we can build the ultimate survival strategy! 🚀

---

Happy gaming, Survivor! May your base thrive and your enemies tremble! 🔥

---

## 💬 Comments
<script src="https://giscus.app/client.js"
        data-repo="jake8923948/DW-Comments"
        data-repo-id="R_kgDOOOCjpA"
        data-mapping="number"
        data-term="1"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="en"
        crossorigin="anonymous"
        async>
</script>
