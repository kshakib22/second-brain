Ooh bonus content hehe.
# Simple Portrait Editing Workflow in GIMP (No Brushes)

## Step 1: Open the Image
- Go to `File > Open` and select your portrait image.

## Step 2: Duplicate the Layer
- In the Layers panel:
  - Right-click the Background layer → `Duplicate Layer`
  - Work on the new layer to preserve the original

## Step 3: Crop and Straighten (if needed)
- Use the **Crop Tool** (`Shift + C`) to improve framing
- Use **Rotate Tool** (`Shift + R`) if the image is tilted

## Step 4: Automatic Color Enhancement
- Go to `Colors > Auto > White Balance`
- Then try `Colors > Auto > Color Enhance`
- If needed, undo either with `Ctrl + Z` and try manually below

## Step 5: Adjust Brightness and Contrast
- Go to `Colors > Levels`
  - Use the Auto button or adjust the input sliders to brighten skin tones
- Optionally fine-tune with `Colors > Brightness-Contrast`

## Step 6: Smooth the Skin (Gaussian Blur)
- Duplicate your current working layer
- Go to `Filters > Blur > Gaussian Blur`
  - Radius: 4 to 6 px (depends on your image)
- Lower the layer's **opacity** to ~50–70% for a soft skin effect

## Step 7: Enhance Color
- Go to `Colors > Hue-Saturation`
  - Slightly increase **Saturation** (+5 to +10)
  - If needed, select individual color channels (like Reds) to boost lips or cheeks

## Step 8: Sharpen the Image
- Merge visible layers: `Image > Merge Visible Layers`
- Go to `Filters > Enhance > Unsharp Mask`
  - Radius: 1.0–1.5 px
  - Amount: 0.5–1.0
  - Threshold: 0

## Step 9: Optional Vignette Effect
- Go to `Filters > Light and Shadow > Vignette`
  - Adjust Radius, Softness, and Opacity to taste

## Step 10: Export the Image
- Go to `File > Export As`
  - Choose `.jpg` or `.png`
  - Set quality to 90–100 for high resolution output