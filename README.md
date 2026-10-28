Neon Rush - 3D-Style Racing Game

A fast arcade racing game that runs in the browser. Drive from the START gate to the FINISH line, dodge traffic, and set a time on the leaderboard.

Built from scratch in JavaScript and HTML5 Canvas, with a custom pseudo-3D rendering engine. No game engine and no 3D library.

Screenshots / demo: add a GIF or screenshots here (home page, race, finish screen). Live demo: add your link here.

Features
Pseudo-3D road engine: perspective projection with curves, hills, rumble strips, lane markings, and a parallax skyline.
Smooth driving feel: fixed-timestep physics loop at 60 updates per second, with eased steering and speed-based steering response.
Traffic: 45 AI cars drive on the road, with collision detection, speed loss on impact, and camera shake.
Free off-road driving: leaving the asphalt does not slow or trap the car.
Complete game flow: home page, 3-2-1-GO countdown, START and FINISH gates with checkered lines, a live progress bar, and a finish screen.
In-game controls: a bottom dashboard with Quit (back to the home page) and Restart, plus a pause menu on Esc.
Leaderboard: the top 5 race times, saved in the browser and shown after reaching the finish line.
Visual style: a neon home page and a bright daytime race scene, with a HUD for speed, time, and race progress.
Controls
Key	Action
W / Up Arrow	Accelerate
S / Down Arrow	Brake
A D / Left Right	Steer
Esc or P	Pause / resume
R	Restart the race
Enter	Start the race from the home or finish screen
How to Run
Download or clone this repository.
Keep Main.dc.html, support.js and the vendor/ folder together in the same folder.
Open Main.dc.html in a modern browser (Chrome or Edge).

If the page is blank because the browser blocks local files, run it through a local server. In VS Code, install the Live Server extension, then right-click Main.dc.html and choose Open with Live Server.

Project Structure
.
├── Main.dc.html    # The game: markup and all game logic (JavaScript)
├── support.js      # Runtime that loads the page
├── vendor/         # Bundled libraries used by the runtime (React)
└── README.md
Technical Highlights
Perspective projection: the road is split into short segments, and each frame the segments in front of the car are projected to screen coordinates and drawn back to front. Curves are built by accumulating the horizontal offset of each segment, and hills by interpolating segment heights.
Fixed timestep with a separate render loop: physics always advances in 1/60 s steps while drawing runs on requestAnimationFrame, so the game behaves the same on fast and slow machines.
Steering and curve force: steering input is smoothed with an exponential ease, and the car is pushed outward on curves in proportion to speed and curve strength.
Collision detection: traffic cars are matched against the player by distance along the track and lateral lane offset.
Persistent leaderboard: results are sorted and stored with localStorage, with safe fallbacks if storage is unavailable.
Tech Stack
JavaScript (game logic and rendering)
HTML5 Canvas 2D API
HTML and CSS
Roadmap
 Port the game to Unity (C#) with true 3D physics using WheelColliders
 Opponent AI that follows a racing line
 Multiple tracks, car selection, and tuning options
 Engine sound that changes with speed
 Online leaderboard
Credits
Game design, programming, and UI: Aswini S
Home page artwork: add the source and credit here, or replace it with your own artwork before sharing publicly.
