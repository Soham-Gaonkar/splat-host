# splat-host

Hosts `.splat` files (3D Gaussian Splatting models and point clouds) for viewing in the browser with
[antimatter15/splat](https://github.com/antimatter15/splat). Click a link to open it; no install needed.

| Scene | File | Splats | Size | View |
|---|---|---|---|---|
| Shelf, 3DGS (30k iterations) | `model.splat` | 1,148,987 | 36.8 MB | [open in viewer](https://antimatter15.com/splat/?url=https://raw.githubusercontent.com/Soham-Gaonkar/splat-host/main/model.splat) |
| Room, 3DGS | `gs_newroom2.splat` | 75,274 | 2.4 MB | [open in viewer](https://antimatter15.com/splat/?url=https://raw.githubusercontent.com/Soham-Gaonkar/splat-host/main/gs_newroom2.splat) |
| Room, point cloud | `pointcloud_newroom2.splat` | 522,531 | 16.7 MB | [open in viewer](https://antimatter15.com/splat/?url=https://raw.githubusercontent.com/Soham-Gaonkar/splat-host/main/pointcloud_newroom2.splat) |

The shelf model is from [Comparing InstantNGP and 3DGS](https://github.com/Soham-Gaonkar/Comparing-InstantNGP-and-3DGS).

## Viewer controls

| Action | Input |
|---|---|
| Rotate | left-drag |
| Pan | right-drag |
| Zoom | scroll |
| Move | arrow keys / WASD |

Large files load progressively (largest splats first) and take a few seconds. The initial camera may
be rotated or upside down because of the COLMAP coordinate convention; rotate to find the scene.

## Adding a file

1. Copy the `.splat` into this repository and push with git (`git add`, `git commit`, `git push`).
   The web upload is limited to 25 MB; git allows up to 100 MB per file. Do not use Git LFS: the
   raw URL would return the LFS pointer instead of the file.
2. Link it as
   `https://antimatter15.com/splat/?url=https://raw.githubusercontent.com/Soham-Gaonkar/splat-host/main/<file>.splat`

Use the `raw.githubusercontent.com` URL, not the GitHub Pages URL: Pages serves the file
gzip-compressed with the compressed `Content-Length`, which makes the viewer fail with
"RangeError: offset out of bounds".
