# Pavitara S · Portfolio

**Live: [pavitara.vercel.app](https://pavitara.vercel.app)**

A portfolio you can drive. The page opens on a kart heading down a neon road into a twilight sunset, and the kart is yours. Each section of the site is a sector of one lap, ending with a cooldown lap.

## Controls

| | Desktop | Phone |
|---|---|---|
| Steer | Mouse, or ← → / A D | Hold boost and slide your thumb |
| Boost | Hold the mouse button on empty space, or Space / W | Hold the boost button |

Keep boosting for 5 seconds to trigger a **time warp** 🌀. The sunset turns into a ringed planet and the billboards start saying different things. Do it again to get back to 2026.

## How it's built

One `index.html` file, with no framework and no build step.

- **Canvas 2D** draws the world: sky, sun, skyline, palms, road and everything at the trackside.
- **three.js** renders a small low-poly 3D kart on top. If it fails to load, a 2D kart takes its place.
- **Vercel** hosts it.

## The physics, briefly

- **Throttle and drag:** speed eases toward a target every frame, so the kart surges when you boost and coasts when you let go.
- **Steering:** a damped spring pulls the kart toward your pointer. Grip drops as speed rises, so fast turns overshoot a little and settle, like a kart sliding on its tyres.
- **Suspension:** random road bumps kick a second spring, and they come more often at higher speed.
- **The kart reacts:** the wheels spin and steer, and the body rolls in corners, squats under acceleration and dives when you lift off.
- **Camera:** it leans into turns, zooms out and shakes on boost, and stretches the stars into streaks at full speed.

The road looks 3D but is plain 2D perspective: anything at distance `z` is drawn at scale `1.2 / z`. The trackside objects sit on a 30-unit loop that repeats forever, and every 40 units counts as a lap.

## Accessibility

- With **reduce motion** turned on, the scene shows a single still frame.
- The animation pauses when the tab is hidden.
- Screen readers skip the canvases and read the content.

## Run it locally

Clone the repo and open `portfolio/PORTFOLIO/index.html` in a browser. There's nothing to install.
