# 🎶 Scene2Music

*AI-Powered Prompt-Based Music Generation*  
Convert natural language descriptions of scenes into expressive music through a dual-stage deep learning pipeline.

## 🧠 Overview

*Scene2Music* is a deep learning framework that transforms *free-form textual scene descriptions* into *musical compositions*.  
Our architecture leverages large language models and symbolic music generation to bridge the gap between language and sound.

| Stage | Component | Description |
|-------|-----------|-------------|
| *1* | 🎯 *T5-Large (Fine-tuned)* | Converts a scene prompt into a structured musical caption |
| *2* | 🎼 *Text2MIDI* | Converts the caption into a symbolic MIDI sequence |
| *3* | 🔊 *FluidSynth* | Renders MIDI to playable audio |

## 📊 Datasets Used

### Custom Dataset: scene_caption_pairs.json

A curated dataset of 7000+ scene-caption pairs used to train the T5-large model to generate musical captions from scene descriptions.

- *Structure*: Each entry includes a natural scene and a corresponding rich musical caption.
- *Creation*:
  1. Captions sourced from MIDIcaps dataset.
  2. Matching scene descriptions generated using ChatGPT.
  3. Paired and saved in JSON format.

### Example

```json
{
  "scene": "A motivational startup launch video showcasing innovation and teamwork.",
  "caption": "This electronic song, infused with pop elements, exudes a joyful and motivational atmosphere... tempo of 130 bpm, in the key of A minor."
}

```
## 💡 Example

*Prompt:*  
> “A calm sunset over the ocean with gentle waves”

*Generated Caption:*  
> “A relaxing and meditative ambient song featuring piano, soft strings, and oceanic textures in C major at 80 BPM.”

### Generated Outputs:
- [Download .mid file](audio/generated.mid)
- [Download .wav file](audio/generated.wav)
- [Download .mp3 file](audio/generated.mp3)

## 🛠 Installation

### 1. Clone Repository

bash
git clone https://github.com/yourusername/Scene2Music.git
cd Scene2Music


### 2. Setup Python Environment

bash
python -m venv venv
source venv/bin/activate   # or use `venv\Scripts\activate` on Windows
pip install -r requirements.txt

### 3. Install FluidSynth

- *Ubuntu:*
  bash
  sudo apt-get install fluidsynth
  
- *macOS:*
  bash
  brew install fluid-synth
    
- *Windows:*  
  Download from [FluidSynth](https://github.com/FluidSynth/FluidSynth/releases)
  
 ⚠ Use a compatible SoundFont (e.g., FluidR3_GM.sf2)

 

## 📥 Download Pretrained Model

You can download the pretrained T5-Large model used in this project from Google Drive:

🔗 [Download T5_Large_TrainedModel (Google Drive)](https://drive.google.com/file/d/16bsUBfp9o0D5FdCFOpv271haRpzB2F7h/view?usp=drive_link)



## 🚀 How to Run

### 🔹 Stage 1: Scene → Musical Caption
Run notebooks/T5_Large_TrainedModel_Scene2Caption.ipynb to:

- Load or fine-tune the T5-Large model
- Generate musical descriptions for scene prompts

### 🔹 Stage 2: Caption → MIDI
Run notebooks/Scene2Music.ipynb to:

- Use Text2MIDI for caption-to-MIDI generation
- Render MIDI using FluidSynth
- Export .mp3 using pydub

## 📈 Results

| Metric            | Result                                    |
|-------------------|-------------------------------------------|
| Caption Relevance |  High semantic alignment with prompt    |
| MIDI Coherence    |  Structured, rhythmically sound         |
| Audio Realism     |  Good with proper SoundFont             |
| Prompt Control    |  Strong interpretability and mood consistency |

## 📌 Highlights
🔹 Fine-tuned T5-Large on handcrafted scene–caption dataset  
🔹 Deep integration with Text2MIDI  
🔹 Seamless MIDI to WAV/MP3 conversion with FluidSynth  
🔹 End-to-end interactive pipeline for text-to-music generation

## 🧑‍💻 Authors

Developed with dedication by:

- *K. Lakshmi Sripriya*
- *D. Poojitha*
- *P. Bhuvana*
- *G. Thanusha*
- *S. Vidya Sagar*

> This project is a collaborative effort by 3rd-year B.Tech Computer Science and Engineering students, exploring the intersection of artificial intelligence and music generation.  
> Key contributions include dataset curation, model training, pipeline development, and audio rendering.

## 📚 References

- [Text2MIDI – AMAAI Lab](https://github.com/amasciul/text2midi)
- [T5: Exploring the Limits of Transfer Learning](https://arxiv.org/abs/1910.10683)
- [FluidSynth](https://www.fluidsynth.org/)
