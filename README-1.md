---
title: AI Video Editor
emoji: 🎬
colorFrom: blue
colorTo: purple
sdk: gradio
sdk_version: 4.44.0
app_file: app.py
pinned: false
---

# 🎬 AI Video Editor (Free & Open Source)

Video upload karo, text mein bata do kya edit karna hai, aur edited video wapas milega.
Poora free — Gradio + FFmpeg use karta hai, koi paid API nahi chahiye.

---

## 📁 Files kya kya hain

| File | Kaam |
|---|---|
| `app.py` | Poora app ka code (UI + editing logic) |
| `requirements.txt` | Python libraries jo chahiye |
| `packages.txt` | System package (ffmpeg) — Hugging Face isse apt se install karta hai |
| `README.md` | Yeh file (instructions) |

---

## 🚀 STEP 1: GitHub par daalna

1. [github.com](https://github.com) par jao aur account banao (agar nahi hai)
2. Top-right "+" icon → **New repository**
3. Naam do jaise `ai-video-editor` → **Create repository**
4. Us naye repo ke page par **"uploading an existing file"** link par click karo
5. Yahan par yeh teen files drag-drop kar do: `app.py`, `requirements.txt`, `packages.txt`, `README.md`
6. Neeche **Commit changes** button dabao

Bas, tumhara code GitHub par live hai.

---

## 🌐 STEP 2: Free mein deploy karna (Hugging Face Spaces)

Hugging Face Spaces ek **free hosting** hai jo Gradio apps ke liye best hai.

1. [huggingface.co/join](https://huggingface.co/join) par account banao (free)
2. Login karne ke baad top-right profile icon → **New Space**
3. Space ka naam do (jaise `ai-video-editor`)
4. **SDK** mein "**Gradio**" select karo
5. **Space hardware**: "CPU basic - Free" hi rehne do
6. **Create Space** dabao

Ab do tarike hain files daalne ke:

### Tarika A (aasaan - website se hi):
1. Naye Space ke page par **"Files"** tab par jao
2. **"Add file" → "Upload files"** dabao
3. Apne saari files (`app.py`, `requirements.txt`, `packages.txt`) upload kar do
4. Commit kar do

### Tarika B (GitHub se link karna):
Agar tum chahte ho GitHub aur Hugging Face dono sync rahein, toh Space settings mein
"GitHub repository" link kar sakte ho — lekin Tarika A shuru mein sabse simple hai.

Files upload karte hi Space **automatically build hona shuru** ho jaayega
(2-5 minute lagte hain). Build complete hote hi tumhara app live URL par chalega:

```
https://huggingface.co/spaces/<tumhara-username>/ai-video-editor
```

Yeh link kisi ko bhi bhej sakte ho — wo seedha browser mein video upload karke
instruction de sakta hai, koi installation nahi chahiye.

---

## 💻 STEP 3 (optional): Apne computer/Colab par test karna

Agar deploy karne se pehle khud test karna hai:

```bash
pip install -r requirements.txt
# ffmpeg install karo agar nahi hai:
# Ubuntu/Colab: apt-get install ffmpeg
# Windows: https://ffmpeg.org/download.html se download karo

python app.py
```

Terminal mein ek local URL milega (jaise `http://127.0.0.1:7860`) — usse browser mein kholo.

**Google Colab mein chalane ke liye:**
```python
!apt-get install -y ffmpeg
!pip install gradio
!python app.py
```
Colab `share=True` chahiye public link ke liye — `app.py` ke last line mein
`demo.launch()` ko `demo.launch(share=True)` kar do.

---

## 🛠️ Abhi kya kya edit kar sakta hai

- Video trim/cut karna (start ya end se seconds specify karke)
- Text overlay add karna
- Speed fast/slow karna
- Audio mute karna
- GIF mein convert karna
- Audio nikaal ke MP3 banana
- Black & white karna

## 🔮 Aage kya add kar sakte ho (Phase 2)

- Smarter command samajhna: `parse_instruction()` function ko replace karo
  ek free LLM API se (Groq free tier ya Google Gemini free tier) taaki
  complex Hindi/English instructions bhi samjhe
- Subtitles auto-generate karna (OpenAI Whisper add karke)
- Background music add karna
- Multiple clips joinna/merge karna
- Object removal / AI effects (yeh heavy hai — GPU chahiye, paid API jaise
  Runway/Kling ka use karna padega scale ke liye)

---

## ⚠️ Free tier limits (jaan lo)

- Hugging Face free CPU Space: video processing thoda slow hoga (GPU nahi hai)
- Bahut badi ya lambi videos (jaise 10+ minute, 1GB+) free tier par timeout ho sakti hain
- Agar zyada traffic/users aaye, free Space "sleep" mode mein chala jaata hai
  jab tak koi use na kare — pehli request thoda slow hogi (cold start)

Chhoti videos (1-2 minute tak) ke liye yeh perfectly kaam karega.
