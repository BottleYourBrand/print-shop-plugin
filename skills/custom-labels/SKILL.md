---
name: custom-labels
description: Make print-ready custom labels with Bottle Your Brand — wine, beer, water bottle, dropper bottle, and square or rectangle labels for jars, candles, boxes and packaging. Use when someone wants a label designed, sized, previewed on a bottle, or ordered, or needs a label size, bleed, or design template.
---

# Custom labels with Bottle Your Brand

Bottle Your Brand prints custom labels from any image. This skill uses the Bottle Your Brand MCP server bundled with this plugin. The server resizes artwork to the exact label size with 0.125" bleed at 300 dpi, so files go straight to print.

## Products

| Product | Sizes (inches) |
| :--- | :--- |
| `wine` | 3.5 × 4 |
| `beer` | 4 × 3.5 |
| `water` (wrap-around) | 8.25 × 1.75, 8 × 2.125 |
| `dropper` | 3 × 2 |
| `square-sticker` | 2 × 2, 3 × 3, 4 × 4, 5 × 5 |
| `rectangle-sticker` | 3 × 2, 4 × 2, 4 × 3, 6 × 4 (prints vertical too) |

For die-cut stickers cut to the shape of the art, use the `custom-stickers` skill instead.

## How to work

1. **Before generating or designing label art, call `get_label_specs`** with the product (and size). Use the shape it gives for the image generator, follow its `artwork_rules`, and keep text inside the safe zone. For someone designing in Canva, Photoshop or Illustrator, share its `design_template` PDF link.
2. **If the image is at a public https URL**, call `order_label_artwork`. Leave `fit` unset (auto). Show the bottle preview and the print preview, and pass on every warning before linking the order.
3. **If the image is a local file or in the conversation**, call `upload_label_artwork` with the product and size. The panel fits it, shows it on the bottle, and gives an order button.
4. **Act on warnings:** a `plain_margin` warning means re-run with `trim_border: true`; a `filled_gap` warning means offer to regenerate the art at the label's shape; low resolution means a larger image is needed.

## Notes

- Ordering and payment happen on bottleyourbrand.com. The tools hand off to the product page with the print-ready file attached; they never place or charge an order.
- Uploaded artwork is stored only to complete the handoff. See https://www.bottleyourbrand.com/privacy-policy.
