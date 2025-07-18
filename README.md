# C-code PBR Hi3DGen

**C-code PBR Hi3DGen** is a powerful toolkit for generating 3D models and PBR (Physically Based Rendering) textures from images, with seamless Blender integration and advanced texture variation tools. It is designed for artists, researchers, and developers who want to quickly create high-quality 3D assets from 2D images.

---

## Features

- **Blender Add-on**: Generate 3D meshes and PBR textures directly inside Blender.
- **PBR Texture Generation**: Supports albedo, normal, roughness, metallic, AO, and more.
- **Texture Variation Tool**: Create and select multiple texture variations using a PySide6 GUI powered by Stable Diffusion and ControlNet.
- **Customizable Pipelines**: Integrate with your own models or pipelines.
- **User-Friendly UI**: Intuitive panels and controls in Blender and the external tool.
- **Background Removal**: Optional background removal for cleaner results.
- **Cross-Platform**: Works on Windows.
 Linux, and macOS (with Python and Blender support).- Not Known

---

## Table of Contents

- [Installation](#installation)
- [Blender Add-on Usage](#blender-add-on-usage)
- [Texture Variation Tool](#texture-variation-tool)
- [Project Structure](#project-structure)
- [Troubleshooting](#troubleshooting)
- [Contact & Support](#contact--support)
- [License](#license)

---

## Installation

### Prerequisites

- **Blender 4.2+** (tested on 4.5 LTS)
- **Python 3.10+** (matching your Blender version)
- **Miniconda/Anaconda** (for environment management)
- **PySide6**, **diffusers**, **torch**, **Pillow**, **opencv-python**, and other dependencies (see `requirements.txt`)

### 1. Clone the Repository

```bash
git clone https://github.com/Dahandla/C-code-PBR-Hi3DGen.git
cd C-code-PBR-Hi3DGen
```

### 2. Set Up Python Environment

It is recommended to use a conda environment:

```bash
conda create -n hi3dgen python=3.10
conda activate hi3dgen
pip install -r requirements.txt
```

### 3. Install the Blender Add-on

- In Blender, go to **Edit > Preferences > Add-ons > Install**.
- Select `BlenderPlugins/hi3dgen_blender_addon` (the folder or the `.py` file).
- Enable the add-on: search for "Hi3DGen" in the add-ons list and check the box.

### 4. (Optional) Download Model Weights

Some features require additional model weights (e.g., Stable Diffusion, ControlNet, RealESRGAN). Place these in the appropriate `ckpt/` or `models/` folders as described in the documentation.

---

## Blender Add-on Usage

1. **Open Blender** and switch to the **3D View**.
2. Open the **Sidebar** (`N` key) and find the **Hi3DGen** tab.
3. **Input Section**:  
   - Select an input image.
   - (Optional) Select or load a mesh file.
4. **Output Section**:  
   - Set output directory, resolution, and other options.
5. **PBR Options**:  
   - Choose whether to generate textures, decimate mesh, remove background, etc.
   - Click **Generate PBR Model** to start the process.
6. **Tools Section**:  
   - Decimate mesh, add RGB curve, launch texture variation tool, import last variation, etc.
7. **Status**:  
   - Progress and error messages are shown at the bottom.

**Preferences**:  
- Set paths for Python, conda, backend scripts, and output folders in the add-on preferences.
- Find contact info, support links, and donation options in the preferences panel.

---

## Texture Variation Tool

The external texture variation tool (`run eccg.py`) allows you to:

- Generate multiple texture variations using Stable Diffusion + ControlNet.
- Select and import your favorite variation back into Blender with one click.
- Use advanced options: canny thresholds, prompt/negative prompt, steps, guidance scale, etc.

**To launch:**
- Use the "Open Texture Variation Tool" button in the Blender add-on, or run directly:
  ```bash
  python run eccg.py call the ccode3dgen_tex.pyd file.
  ```

---

## Project Structure

```
C-code-PBR-Hi3DGen/
├── BlenderPlugins/
│   └── hi3dgen_blender_addon/   # Blender add-on
├── ccode3dgen_tex.py            # Texture variation tool (PySide6 GUI)
├── models/                      # Model weights (pytorch, caffemodel, etc.)
├── ckpt/                        # Checkpoints for upscaling, etc.
├── hy3dgen/                     # Core 3D/texturing logic
├── hy3dpaint/                   # Differentiable renderer, painting logic
├── hy3dshape/                   # Shape generation logic
├── assets/                      # Example images, meshes, HDRIs, etc.
├── requirements.txt             # Python dependencies
├── README.md                    # This file
└── ...
```

---

## Troubleshooting

- **Preview not showing?**  
  - Make sure your image file name is not too long or contains only safe characters. The add-on now uses hash-based names to avoid Blender's data-block name length limits.
  - Check the Blender console for `[Preview]` debug messages.
- **Add-on not appearing?**  
  - Ensure you installed the correct folder/file and enabled the add-on in Blender preferences.
- **Missing models?**  
  - Download required model weights and place them in the correct folders.
- **Python/conda issues?**  
  - Make sure your conda environment matches your Blender Python version.

---

## Contact & Support

- **Home page:** [https://www.ccodestudio.com/](https://www.ccodestudio.com/)
- **Email:** saraintelai@gmail.com
- **GitHub:** [https://github.com/Dahandla/C-code-PBR-Hi3DGen/tree/main](https://github.com/Dahandla/C-code-PBR-Hi3DGen/tree/main)
- **PayPal:** [https://paypal.me/AndreDickinson?locale.x=en_US](https://paypal.me/AndreDickinson?locale.x=en_US)
- **Cash App:** `$anykeyad`
- **README.txt:** Included in the repository for offline help.

---

## License

This project is licensed under the MIT License.  
See [LICENSE](LICENSE) for details.

---

## Acknowledgements

- [Blender](https://www.blender.org/)
- [PySide6](https://wiki.qt.io/Qt_for_Python)
- [Diffusers](https://github.com/huggingface/diffusers)
- [Stable Diffusion](https://stability.ai/)
- [ControlNet](https://github.com/lllyasviel/ControlNet)
- [RealESRGAN](https://github.com/xinntao/Real-ESRGAN)
- And all open-source contributors!

---

**Enjoy creating amazing 3D content with C-code PBR Hi3DGen!** 