# ArtDepth3D

ArtDepth3D is a hybrid AI-based pipeline that converts a single 2D image
(photo or artwork) into an object-aware depth map suitable for 3D effects,
parallax animation, and scene reconstruction.

Unlike standard monocular depth models, this project combines modern
transformer-based AI models with classical computer vision and custom
heuristics to produce more convincing depth — especially for illustrations,
paintings, and stylized art.

---

## ✨ Features

- 🎨 Works on **art, illustrations, and photographs**
- 🧠 Transformer-based monocular depth estimation
- 🧩 Object-aware depth refinement using segmentation
- 🌿 Special handling for plants and organic shapes
- 🛠 Hybrid system (AI + classical CV + custom logic)
- 🎥 Ready for 3D parallax, Blender, and AR workflows

---

## 🧠 How It Works

The pipeline is not a single end-to-end neural network. Instead, it uses
multiple stages:

1. **Input Analysis**
   - Determines whether the input is a photo or artwork
   - Selects appropriate preprocessing strategy

2. **Preprocessing**
   - Enhances edges, contrast, and structure (especially for art)
   - Normalizes image for AI models

3. **Segmentation**
   - Uses Meta’s Segment Anything Model (SAM)
   - Separates objects for independent depth treatment

4. **Depth Estimation**
   - Uses MiDaS / DPT transformer-based monocular depth models
   - Produces a relative depth map

5. **Depth Refinement (Custom Logic)**
   - Refines depth per object layer
   - Adds gradients to flat regions
   - Pushes foreground/background objects appropriately

6. **Optional Visual Refinement**
   - Can integrate Stable Diffusion for inpainting or enhancement

---

## 🤖 Models Used

| Task | Model |
|----|----|
| Depth Estimation | MiDaS / DPT (Vision Transformer) |
| Segmentation | Segment Anything Model (SAM) |
| Image Processing | OpenCV, PIL |
| Optional Enhancement | Stable Diffusion |
| Refinement | Rule-based heuristics |

> Note: Depth is **relative**, not metric.

---

## 📥 Installation

```bash
git clone https://github.com/yourusername/ArtDepth3D.git
cd ArtDepth3D
pip install -r requirements.txt
