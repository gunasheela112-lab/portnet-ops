PortNet Ops
A single-page network design and monitoring dashboard for a port facility — built to demonstrate practical networking fundamentals (subnetting, VLAN segmentation, bandwidth planning) alongside a light data-analytics layer (vessel scheduling and berth congestion detection).
Live demo: enable GitHub Pages on this repo (Settings → Pages → Deploy from branch → main → /root), then visit https://<your-username>.github.io/<repo-name>/.
What it shows
Network topology — five zones (Cargo Yard, Admin Office, Ship-to-Shore Comms, CCTV & Security, Port Operations Center) meeting at one core switch, each on its own VLAN.
IP addressing & VLAN table — subnet, gateway, and usable host count per zone, sized to each zone's real device load rather than a flat scheme.
Live bandwidth & uptime monitor — simulated per-zone telemetry that updates every few seconds, with status thresholds (nominal / elevated / critical).
Vessel schedule & berth congestion — a small scheduling table that flags congestion risk when two vessels are assigned to the same berth zone within a two-hour window.
Design rationale — short written notes explaining the reasoning behind each segmentation decision.
Why this design
Each zone's subnet size and isolation level reflects a real operational reason (see the Design Rationale section on the page itself) — for example, CCTV traffic is isolated on its own subnet so it can't be reached from admin devices and can't crowd out other zones' bandwidth, while the ship-to-shore comms zone is sized with headroom for burst traffic during berthing.
Tech
Plain HTML, CSS, and JavaScript in a single file (index.html) — no build step, no dependencies to install, no server required. All telemetry and scheduling data is generated in-browser for demonstration purposes.
Running locally
Just open index.html in any browser. No installation needed.
