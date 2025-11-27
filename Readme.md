# AI-Powered Image Generator

A text-to-image generation system built with Stable Diffusion that lets you create stunning images from simple text descriptions. This project demonstrates practical implementation of generative AI for creative applications.

![Sample Generation](sample_images/banner.png)

## About This Project

I built this as part of my exploration into generative AI and deep learning. The system uses Stable Diffusion 1.5 to convert text prompts into images, with a clean web interface that makes it easy for anyone to use. It's been a great learning experience working with diffusion models and understanding how they transform text into visual content.

## Features

- **Text-to-Image Generation**: Simply describe what you want and watch it come to life
- **Multiple Style Presets**: Choose from realistic, artistic, anime, oil painting, and more
- **Smart Prompt Enhancement**: Automatically improves your prompts with quality-boosting keywords
- **Content Filtering**: Built-in safety checks to prevent inappropriate content generation
- **Batch Processing**: Generate multiple images from different prompts in one go
- **Metadata Storage**: Every image is saved with its generation parameters for reproducibility
- **Style Comparison Tool**: See how different artistic styles affect the same prompt
- **Interactive Web UI**: Easy-to-use interface built with Gradio

## Tech Stack

**Model & Framework:**
- Stable Diffusion 1.5 (runwayml/stable-diffusion-v1-5)
- PyTorch for deep learning operations
- Hugging Face Diffusers library for model management

**Interface & Tools:**
- Gradio for the web interface
- Pillow (PIL) for image processing
- Google Colab for GPU access

## Getting Started

### Prerequisites

Since this runs on Google Colab, you don't need to install anything locally! Just need:
- A Google account
- Decent internet connection (model is ~4GB)
- About 10-15 minutes for first-time setup

### Running the Project

1. **Open Google Colab**
   - Go to [colab.research.google.com](https://colab.research.google.com)
   - Click on `File` → `Open Notebook` → `GitHub` tab
   - Paste this repository URL

2. **Set Up GPU**
   - Click `Runtime` → `Change runtime type`
   - Select `T4 GPU` from the dropdown
   - Click `Save`

3. **Run the Cells**
   - Run Cell 1 to install dependencies (takes 2-3 minutes)
   - Run Cell 2 to load the model (takes 5-10 minutes on first run)
   - Run Cell 3 to launch the interface
   - Optionally run Cell 4 for advanced features

4. **Start Creating**
   - Once Cell 3 runs, you'll get a public URL
   - Click the Gradio link and start generating!

### Hardware Requirements

**With GPU (Recommended):**
- Google Colab's free T4 GPU works perfectly
- Generation time: 20-30 seconds per image
- Can generate up to 4 images at once

**CPU Fallback:**
- Works but significantly slower (5-10 minutes per image)
- Recommended only for testing
- Requires 16GB+ RAM

## Usage Examples

Here are some prompts that work really well:

```
"A serene mountain landscape with a crystal clear lake at sunset, photorealistic, highly detailed"

"A cute robot reading a book in a cozy library, warm lighting, digital art"

"Portrait of a wise old wizard with a long white beard, oil painting style, detailed"

"A futuristic cyberpunk city with neon lights at night, 8k, cinematic"

"A magical forest with glowing mushrooms and fireflies, fantasy art, ethereal"
```

### Tips for Better Results

**Be Specific**: Instead of "a car", try "a red sports car on a mountain road at sunset"

**Add Quality Keywords**: Include words like "detailed", "high quality", "8k", "professional"

**Specify Style**: Mention the artistic style you want - "photorealistic", "oil painting", "anime style"

**Use Negative Prompts**: Tell it what to avoid - "blurry", "low quality", "distorted"

**Experiment**: Try different guidance scales (7-12 works best) and styles to see what you like

## How It Works

The system uses a diffusion model, which is basically a type of AI that learns to create images by reversing a noise-adding process. Here's the simplified version:

1. **You enter a text prompt** describing what you want
2. **The text encoder** converts your words into numerical representations
3. **The diffusion model** starts with random noise and gradually refines it
4. **Through multiple steps** (20-50 iterations), the noise transforms into a coherent image
5. **The decoder** converts the final result into a viewable image

The "guidance scale" parameter controls how closely the model follows your prompt - higher values stick closer to your description but might look less natural.

## Project Structure

```
ai-image-generator/
│
├── AI_Image_Generator.ipynb    # Main Colab notebook with all code
├── README.md                    # This file
├── requirements.txt             # Python dependencies
├── sample_images/               # Example generated images
│   ├── realistic_landscape.png
│   ├── robot_library.png
│   ├── wizard_portrait.png
│   └── cyberpunk_city.png
└── outputs/                     # Generated images (auto-created)
    ├── images/
    └── metadata/
```

## Limitations & Challenges

**Current Limitations:**
- Image resolution limited to 512x512 (due to model and GPU memory)
- Generation takes 20-30 seconds per image
- Quality not quite at the level of commercial tools like DALL-E 3 or Midjourney
- Struggles with fine details like hands, text, and complex scenes
- Google Colab sessions timeout after 90 minutes of inactivity

**What I Learned:**
- Working with diffusion models is resource-intensive
- Prompt engineering makes a huge difference in output quality
- Balancing quality vs speed is tricky - more steps = better quality but slower
- Content filtering is important but hard to make perfect

## Future Improvements

If I had more time and resources, I'd love to add:

- **Higher Resolution**: Support for 768x768 or 1024x1024 images
- **Fine-tuning**: Train on specific styles or subjects
- **Image-to-Image**: Upload a reference image and modify it
- **Inpainting**: Edit specific parts of generated images
- **Better Models**: Upgrade to Stable Diffusion XL or SD 2.1 for quality boost
- **Style Transfer**: Apply specific artistic styles to existing images
- **Better UI**: More advanced controls and gallery view
- **Local Deployment**: Package it to run on local machines

## Ethical Considerations

**Responsible Use Guidelines:**
- All generated images should be labeled as AI-generated
- Don't use this to create misleading or harmful content
- Respect copyright - avoid trying to replicate specific artworks or artists' styles
- Be mindful of potential biases in the training data
- This is meant for creative and educational purposes only

**Content Filtering:**
The system includes basic keyword filtering to prevent inappropriate content generation, though it's not perfect. If you encounter issues, please use the tool responsibly.

**Attribution:**
Images are generated using Stable Diffusion 1.5 by Stability AI, licensed under CreativeML Open RAIL-M License.

## Acknowledgments

- **Stability AI** for creating and open-sourcing Stable Diffusion
- **Hugging Face** for the amazing Diffusers library that made this much easier
- **Google Colab** for providing free GPU access
- **Gradio** for the simple yet powerful UI framework



## License

This project is open source and available under the MIT License. The Stable Diffusion model itself is under the CreativeML Open RAIL-M License.

