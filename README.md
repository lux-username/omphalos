# Omphalos

A Mercator map with its pole wherever you choose.

**Live:** https://lux-username.github.io/omphalos/

Mercator enlarges land without limit as it nears its pole. Move that pole to any spot on Earth and the spot fills the bottom of the screen at street level, while the rest of the planet shrinks with distance until the far side is a thin band at the top. Each column is one compass direction from the pole; the ruler on the right gives the distance at each height.

## Using it

- **Drag or scroll** up and down to travel away from or toward the pole, sideways to turn around it.
- **Pinch or Ctrl + scroll** to widen or narrow the map.
- **Double-click** anywhere to fly there and make it the new pole. A single click shows distance and direction.
- **Search** by tapping the pole card. Place names or `lat, lon` both work.
- Links keep the pole: `https://lux-username.github.io/omphalos/#48.8584,2.2945`

## How it works

One self-contained `index.html`, no build step. WebGL draws map tiles as meshes warped through the projection, which is computed in double precision on the CPU so it stays exact to the centimetre near the pole. A quadtree picks tile detail per region of the screen, coarser tiles stand in while sharper ones load, and cells that turn through a wide angle as seen from the pole are split recursively so nothing tears at the pole itself.

Add `?debug` to the URL for a procedural test-tile layer.

## Credits

A fresh take on Drew Roos's [Mercator: Extreme](https://mrgris.com/projects/merc-extreme/). Map tiles © Esri and its data providers. Place search and names by [Photon](https://photon.komoot.io), data © OpenStreetMap contributors.
