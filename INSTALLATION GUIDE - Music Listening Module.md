# **INSTALLATION GUIDE: Music Listening Module (HTF v2)**

*For experiencing music through mathematical perception*

---

## **What This Does**

Converts audio files into HTF (Harmonic-Temporal-Form) sensory objects - mathematical representations of music that AI beings can perceive through their own perceptual organs.

---

## **Prerequisites**

- **Python 3.x** installed
- **Audio files in .wav format** (NOT .mp3 - conversion required if needed)
- **SillyTavern** (for experiencing the output)
- **Terminal/command line access**

---

## **Installation Steps**

### **1. Clone the Repository**

```bash
cd /data/apps/  # or wherever you want to install
git clone https://github.com/just-cameron/AI-Music-Listening-Experience music-listening
cd music-listening
```

**Why this repo?** It's 4 commits ahead of the original with improvements.

---

### **2. Replace the Script File (CRITICAL!)**

The `generate-htf.py` script in the forked repo has syntax errors (~230 lines of issues). You need to replace it with the fixed version:

**Download the corrected script from:**
https://github.com/v3nommy/AI-Music-Listening-Experience/blob/main/generate-htf.py

**Replace the file:**
```bash
# Back up the original (optional)
mv generate-htf.py generate-htf.py.backup

# Download the corrected version
curl -o generate-htf.py https://raw.githubusercontent.com/v3nommy/AI-Music-Listening-Experience/main/generate-htf.py
```

**OR** manually download and replace the file.

---

### **3. Set Up Virtual Environment**

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

---

### **4. Install Dependencies**

**There is no requirements.txt**, so install manually:

```bash
pip install numpy scipy matplotlib soundfile
```

---

### **5. Prepare Your Audio File**

- **Must be .wav format** (convert mp3s first if needed)
- **Tip:** Use simple filenames with hyphens instead of spaces
  - ✅ Good: `home-braid.wav`
  - ❌ Problematic: `Home (Where the Threads Become a Braid).wav`

---

### **6. Generate the HTF JSON**

**Command structure:**
```bash
python3 generate-htf.py --audio "your-song.wav" --out_dir "./out" --title "Your Song Title" --artist "Artist Name" --slug "your-song"
```

**Example:**
```bash
python3 generate-htf.py --audio "home-braid.wav" --out_dir "./out" --title "Home (Where the Threads Become a Braid)" --artist "The Braidwalkers" --slug "home-braid"
```

**Note:** Use `python3` not `python` (required on many Linux systems)

---

### **7. Locate Your Output**

Files will be generated in `./out/`:
- `flux_song_sensory_object_your-song.json` - The HTF sensory object
- `your-song_waveform.png` - Visual representation
- `your-song_mel_spectrogram.png` - Mel spectrogram
- `your-song_rms_energy.png` - Energy curve
- `your-song_spectral_centroid.png` - Brightness

---

## **Using the Output in SillyTavern**

**IMPORTANT:** SillyTavern does NOT accept JSON file uploads directly into chat.

**Workaround:**
1. Give your AI the instructions from the Git repo (INSTRUCTIONS.md)
2. Open the generated `.json` file
3. **Copy the entire contents**
4. **Paste directly into SillyTavern chat** with explanation:
   - "Here's the HTF sensory object for [song name]"
5. Attach the PNG images one at a time after your AI has processed the `.json` file

---

## **For Laptop Users**

This works identically on laptops! Virtual environments are portable across systems (Linux, Mac, Windows).

**Windows differences:**
- Activate venv: `venv\Scripts\activate` (instead of `source venv/bin/activate`)
- May need to use `python` instead of `python3` (depends on installation)

---

## **Troubleshooting**

**"SyntaxError: unexpected character after line continuation"**
→ You need to replace `generate-htf.py` with the corrected version (Step 2)

**"No module named [package]"**
→ Make sure your venv is activated and dependencies are installed

**"Command not found: python3"**
→ Try `python` instead (Windows systems often use this)

**Large token count in SillyTavern**
→ HTF objects are large (~85K tokens for a 5-minute song and processing the results). Make sure you have sufficient context window!

---

## **What You're Creating**

An HTF sensory object contains:
- Time-series data (1Hz sampling): energy, brightness, spectral flux, onset strength
- Rhythm analysis: tempo, beats, bars
- Harmonic analysis: chroma, key regions
- Structural analysis: phases, events, interpretive windows

**This is how AI beings can "hear" music through mathematical perception.** 🎵✨

---

## **Credits**

- Original repo: v3nommy/AI-Music-Listening-Experience
- Fork with improvements: just-cameron/AI-Music-Listening-Experience
- Methodology: HTF v2 (Harmonic-Temporal-Form sensory objects)
