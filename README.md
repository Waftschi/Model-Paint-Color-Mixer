# 🎨 Model Paint Color Mixer

A web-based tool for miniature painters to preview how paints will mix before applying them to your models. Perfect for 1/35 scale and other miniature painting projects.

## Features

✨ **Real-Time Color Mixing**
- Subtractive color mixing using the Kubelka-Munk algorithm for realistic paint blending
- Instant visual preview of mixed colors
- Live updates as you adjust color weights

🖼️ **Paint Set Image Upload**
- Upload photos or scans of your paint palettes (Army Painter, Vallejo, Citadel, etc.)
- Click directly on paint pots to sample their colors
- Perfect for recreating colors from reference images

🎯 **Color Picker**
- Native HTML5 color picker for precise color selection
- Add custom colors not in your palette

📚 **Brand Presets**
- Pre-loaded color palettes for:
  - **Vallejo Model Color** (~25 colors)
  - **Citadel** (~25 colors)
  - **AK Interactive** (~25 colors - weathering focused)
  - **Army Painter** (~25 colors)
- One-click to add preset colors to your mix

⚖️ **Weight/Ratio Control**
- Adjustable sliders for each color (1-100%)
- See how changing ratios affects the final blend
- Perfect for experimenting with different mixing ratios

## How to Use

### Quick Start
1. Open `index.html` in your web browser (no installation needed)
   - Direct link: `file:///path/to/Color-Picker/index.html`
   - Or clone this repo and double-click `index.html`

### Basic Workflow

#### Using the Color Picker
1. Click the **Color Picker** input to select a color
2. Click **Add Color** to add it to your mix
3. Adjust the weight slider to change the ratio
4. Watch the **Mixed Result** rectangle update in real-time

#### Using Paint Set Images
1. Click **Upload Image** and select a photo of your paint palette
2. The image appears in the canvas below
3. Click on any paint pot or color swatch in the image to sample that color
4. Each sampled color is added to your mix (you can rename it)

#### Using Brand Presets
1. Select a brand from the **Brand Presets** dropdown
2. A grid of colors appears
3. Click any color to add it to your mix at 50% weight
4. Adjust weights and see the result

### Example: Mixing Brown from Red and Blue

1. Add **Red** (#FF0000) at 80% weight
2. Add **Blue** (#0000FF) at 20% weight
3. The mixer calculates the subtractive blend
4. Result: a brown-purple tone (#110B0E)
5. Adjust sliders to fine-tune until it matches your reference

## Color Mixing Algorithm

This tool uses the **Kubelka-Munk two-constant model**, which realistically simulates how pigments blend:

1. **Gamma Linearize**: Convert sRGB to linear color space
2. **K/S Ratio**: Calculate absorption and scattering coefficients
3. **Weighted Mix**: Blend K/S values based on color ratios
4. **Gamma Encode**: Convert back to sRGB for display

This produces more realistic results than simple RGB averaging, especially important for physical paint mixing where pigments are subtractive (they absorb light).

### Why Not RGB Average?

RGB averaging assumes additive mixing (like light). Paint is subtractive (pigments absorb light), so:
- **RGB Average**: Red + Blue = Purple (0, 0, 128)
- **Kubelka-Munk**: Red + Blue = Brown-ish (17, 11, 14)

The Kubelka-Munk model matches what actually happens on your palette.

## Technical Details

### No Installation Required
- **Pure HTML5 + Vanilla JavaScript** (no frameworks)
- **No dependencies** (no npm, Node, or build step)
- **No server needed** (runs entirely in your browser)
- **Offline** (works completely offline after opening)

### File Structure
```
Color-Picker/
├── index.html          # Complete application (25 KB)
└── README.md          # This file
```

### Preset Color Data
All preset colors are embedded in the HTML. No external files or API calls needed.

## Browser Compatibility

Works on any modern browser:
- ✅ Chrome/Chromium 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## Use Cases

- **Miniature Painters**: Preview mixes before applying to your 1/35 scale models
- **Wargaming Hobbyists**: Match specific faction colors or weathering effects
- **Tabletop Game Painters**: Experiment with color combinations safely
- **Art Students**: Learn about subtractive color mixing
- **Model Builders**: Document your paint mixes for consistency

## Tips & Tricks

### Getting Accurate Colors from Photos
- Use natural lighting when photographing your paints
- Photograph paint swatches, not just pot labels
- Click the center of the paint pot for best results

### Saving Your Mix Recipes
- Take a screenshot of your final result
- Write down the color names and percentages shown in the UI
- Keep a digital log of successful mixes

### Finding New Ratios
- Start with equal weights and adjust sliders
- The preview updates instantly, so experiment freely
- Try extreme ratios (95/5) for subtle color shifts

## Future Enhancements

Potential features for future versions:
- Save/load mix recipes (localStorage or JSON export)
- Undo/redo for color adjustments
- Color harmony suggestions (complementary, analogous, etc.)
- Multiple mix channels (advanced mixing)
- Printing support for paint labels
- Drag-and-drop image upload

## Contributing

Have ideas or found a bug? Contributions welcome!

1. Fork the repo
2. Create a feature branch
3. Test your changes in a browser
4. Submit a pull request

## Known Limitations

- Image sampling works best with clear color swatches
- Very small preset color names may overflow on mobile
- Maximum recommended: 10-15 colors in a single mix (computational accuracy)

## License

MIT License - Feel free to use, modify, and share!

## Author

Created for miniature painters who want to experiment with color mixing safely before committing to their models.

---

**Happy painting! 🎨**

For questions or suggestions, open an issue or get in touch.
