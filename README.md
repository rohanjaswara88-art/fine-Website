# LUXE TECH: interactive electronics storefront

**Live site: [lux-techh.netlify.app](https://lux-techh.netlify.app/)**

A responsive demo storefront built with Vite and vanilla JavaScript. Open a product to drag through its views, zoom in, pick a finish and add it to a working cart. One product, the GRAPHITE Cascade perfume box, is a real 3D model you can rotate, rendered with Three.js.

**Tech:** JavaScript · Vite · Three.js (GLTFLoader) · HTML · CSS

> Built by [Rohan Jaswara](https://rohanjaswara88-art.github.io/portfolio/), a BCA (AI & ML) student.

The full source (`src/`, `public/`) is in `luxe-tech-graphite-cascade-integrated.zip`; unzip it before running locally.

## Run locally

```bash
npm install
npm run dev
```

Open the local URL Vite prints, usually http://localhost:5173.

## Important: photo-based rotation

The demo ships with four example product photos per product from remote Unsplash image URLs. They are **not** a calibrated 360-degree photo sequence and some frames show different examples of the product category. The drag viewer switches between those available example views to demonstrate the interaction; it cannot reveal unseen sides like a true 3D model.

For a convincing 360-degree photo viewer, take a consistent set of photos of the *same product* at evenly spaced angles. For horizontal rotation, 24–72 frames around the product is common. To support vertical viewing too, capture multiple elevation rows (for example, 3 rows × 36 frames). Save files in folders such as `public/frames/headphones/row-1/frame-000.webp` and update each product's `images` array in `src/main.js` to list the frames in order. For production, consider preloading adjacent frames and loading lower-resolution previews first.

## Replace demo images

In `src/main.js`, each product has an `images` array of image URLs. Replace those URLs with local paths such as `/frames/headphones/frame-000.webp`. Keep the frame order consistent. Use images of the same exact product and lighting setup for smooth rotation.

## Current features

- Responsive luxury-minimal storefront
- Product detail modal
- Drag horizontally/vertically to cycle through the available demo views
- Mouse-wheel and button zoom (1×–2.2×)
- Finish selector
- Add to bag, quantity controls, remove item, subtotal
- Escape key and backdrop close behavior
- No backend or payment integration; checkout is intentionally a demo

## Limitations and next step

This is a front-end prototype. The cart is in memory and resets on refresh. Prices are sample USD prices. For real payments, inventory, sign-in, persistent carts, or orders, connect a backend and a trusted payment provider. For true geometric 3D rotation, integrate a `.glb`/`.gltf` model with Three.js or `<model-viewer>`.


## Added product: GRAPHITE Cascade Eau de Parfum (50 ml)

The GRAPHITE Cascade packaging model is loaded from `public/models/graphite-cascade-box.glb` using Three.js `GLTFLoader`. The product is added to the collection as item 004. Its card uses the supplied front photo at `public/products/graphite-cascade-front.jpg`.

**Accuracy note:** the 3D carton is an approximate reconstruction from the supplied photos, not a photogrammetry scan. Dimensions, small print, and unseen top/bottom artwork are inferred/simplified. The listed `$24` is a demo storefront price; change `price` in the `graphite-cascade` object in `src/main.js` to your intended price.

Run it as usual:

```bash
npm install
npm run dev
```

Then open the local Vite URL and select **GRAPHITE Cascade** in the collection. Drag to rotate and use the zoom controls.
