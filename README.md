# 🎧 Free EPUB to Audiobook Converter

**Convert EPUB files to professional audiobooks using AI-powered text-to-speech technology - completely free!**

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Google Colab](https://img.shields.io/badge/Google%20Colab-GPU%20Enabled-red.svg)](https://colab.research.google.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)]()

## 🚀 Quick Start

1. **Open in Google Colab**: [Click here to open the notebook](https://colab.research.google.com)
2. **Enable GPU**: Runtime → Change runtime type → GPU
3. **Upload your EPUB**: Replace the EPUB file path in the first cell
4. **Run all cells**: Sit back and let AI create your audiobook!

**⚡ Performance**: 500 pages processed in just 16-18 minutes with GPU acceleration!

## ✨ Features

- **🆓 100% Free**: No API keys, no subscriptions, no hidden costs
- **⚡ GPU Accelerated**: 6x faster processing with Google Colab GPU
- **🎯 High Quality**: Professional TTS with natural-sounding voices
- **📁 Multiple Formats**: Output in WAV (uncompressed) and M4B (compressed)
- **🔧 Easy to Use**: No coding experience required
- **🌍 Multi-language**: Support for English, French, German, Italian, Japanese, and more
- **📊 Progress Tracking**: See real-time conversion progress
- **🎵 Audio Preview**: Play segments directly in the notebook

## 📋 What This Tool Does

This Google Colab notebook converts your EPUB books into audiobooks in three simple steps:

1. **Extract Text**: Parses EPUB files and extracts clean, readable text
2. **Text-to-Speech**: Uses KOKORO TTS (state-of-the-art neural TTS) to convert text to speech
3. **Combine Audio**: Merges all audio segments into a single, professional audiobook file

## 🔧 Technical Requirements

### Required Software
- **Google Colab Account** (free)
- **EPUB File** (your book to convert)

### Python Libraries (Auto-installed)
- `ebooklib` - EPUB file parsing
- `beautifulsoup4` - HTML content extraction
- `kokoro` - Advanced text-to-speech engine
- `torch` - Deep learning framework
- `soundfile` - Audio file processing
- `numpy` - Numerical operations

### System Requirements
- **GPU Runtime** (highly recommended - 6x faster!)
- Internet connection for library installation
- ~2GB free space for processing

## 📖 Step-by-Step Guide

### 1. Setup Google Colab

```bash
# Open the notebook in Google Colab
# Click "Runtime" → "Change runtime type" → Select "GPU" → Click "Save"
```

**⚠️ Important**: Using GPU reduces processing time from 90+ minutes to just 16-18 minutes for a 500-page book!

### 2. Upload Your EPUB

```python
# Replace this path with your EPUB file location
epub_path = "/content/your-book.epub"
```

### 3. Run the Conversion

```bash
# Click "Runtime" → "Run all" 
# Or run each cell sequentially with Shift+Enter
```

### 4. Download Your Audiobook

Once processing completes:
- Find `audiobook.wav` (high quality, ~100-200MB)
- Find `audiobook.m4b` (compressed, ~50-100MB)
- Right-click → Download

## 🎯 Performance Benchmarks

| Book Size | GPU Time | CPU Time | Speed Improvement |
|-----------|----------|----------|-------------------|
| 100 pages | ~3-4 min | ~18 min | 6x faster |
| 300 pages | ~10-12 min | ~54 min | 6x faster |
| 500 pages | ~16-18 min | ~90 min | 6x faster |
| 1000 pages | ~32-36 min | ~180 min | 6x faster |

## 🌍 Supported Languages

KOKORO TTS supports multiple languages and accents:

- **English (American)** - `lang_code="a"`
- **English (British)** - `lang_code="b"`
- **French** - `lang_code="f"`
- **German** - `lang_code="g"`
- **Italian** - `lang_code="i"`
- **Japanese** - `lang_code="j"`
- **Spanish** - `lang_code="s"`

To change language, modify this line in the notebook:
```python
pipeline = KPipeline(lang_code="a")  # Change "a" to your desired language code
```

## 🎨 Voice Options

Multiple voice options are available:

- `af_heart` - Female American English (default, warm and clear)
- Additional voices can be explored in KOKORO documentation

## 📁 Output Formats

### WAV Format
- **Quality**: Uncompressed, CD-quality audio
- **Size**: Larger file (~100-200MB for 500 pages)
- **Use Case**: Archival, high-fidelity listening

### M4B Format
- **Quality**: Compressed, good quality
- **Size**: Smaller file (~50-100MB for 500 pages)
- **Use Case**: Mobile devices, easy sharing, audiobook players

## 🔍 How It Works

### EPUB Extraction
The notebook uses `ebooklib` to parse the EPUB structure and `BeautifulSoup` to extract clean text from HTML content, preserving paragraph structure and formatting.

### Text Chunking
Text is intelligently split into 1000-character chunks at sentence boundaries to:
- Stay within TTS model limits
- Maintain natural speech flow
- Enable progress tracking

### Text-to-Speech
KOKORO TTS uses advanced neural networks to generate natural-sounding speech with:
- Proper intonation and emphasis
- Natural pauses and rhythm
- Clear pronunciation

### Audio Combination
All audio segments are seamlessly combined into a single file using `numpy` and `soundfile`, ensuring no gaps or audio artifacts.

## 🛠️ Advanced Features

### Individual Segment Processing
The notebook includes an alternative method to:
- Create individual WAV files for each text chunk
- Review and edit specific segments
- Combine segments with custom processing

### Custom Chunk Sizes
Modify chunk size for different processing strategies:
```python
chunks = chunk_text(full_text, max_chars=2000)  # Larger chunks
chunks = chunk_text(full_text, max_chars=500)   # Smaller chunks
```

## ❓ FAQ

### Why use GPU?
GPU acceleration makes text-to-speech processing **6 times faster**. A 500-page book takes 16-18 minutes instead of 90+ minutes.

### Can I use this offline?
This notebook requires Google Colab, which needs an internet connection. However, you can download the output files for offline listening.

### What EPUB formats are supported?
All standard EPUB 2.0 and 3.0 formats are supported, including those with:
- Images (ignored during TTS)
- Tables (converted to text)
- Footnotes (included in main text)
- Multiple chapters (processed sequentially)

### How is audio quality?
KOKORO TTS produces high-quality, natural-sounding speech at 24kHz sample rate - suitable for professional audiobook production.

### Can I process multiple books?
Yes! Simply run the notebook multiple times with different EPUB files, or modify the code to batch process multiple files.

### What if I get memory errors?
- Use smaller chunk sizes (reduce `max_chars`)
- Close other Colab tabs
- Use the M4B output format (smaller file size)

## 🚀 Tips for Best Results

1. **Always use GPU runtime** - 6x speed improvement
2. **Check EPUB formatting** - Well-formatted EPUBs produce better results
3. **Preview text extraction** - Verify the first 2000 characters look correct
4. **Use headphones** - Better for reviewing audio quality
5. **Save frequently** - Colab sessions timeout after 12 hours

## 📊 Project Structure

```
freeEPUBtoAudiobook/
├── test.ipynb          # Main Colab notebook
├── README.md           # This file
├── LICENSE             # MIT License
└── .gitattributes      # Git configuration
```

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest improvements
- Add support for new languages
- Enhance audio quality
- Add new features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

- This tool is for personal use only
- Respect copyright laws - only convert books you own or have permission to convert
- The developers are not responsible for misuse of this tool

## 🔗 Useful Links

- [Google Colab](https://colab.research.google.com) - Run the notebook
- [KOKORO TTS](https://github.com/kokoro-tts/kokoro) - TTS engine documentation
- [EPUB Format](https://www.w3.org/publishing/epub32/) - EPUB specification
- [FFmpeg](https://ffmpeg.org) - Audio conversion tool

## 📈 Version History

- **v1.0** - Initial release with GPU acceleration and multi-format output
- **v1.1** - Added individual segment processing and WAV combination function
- **v1.2** - Enhanced documentation and SEO optimization

## 🎉 Acknowledgments

- **KOKORO TTS** - For the amazing text-to-speech engine
- **Google Colab** - For providing free GPU resources
- **Open Source Community** - For all the amazing libraries used

---

**Ready to convert your first EPUB to audiobook?** 

👉 [Open in Google Colab](https://colab.research.google.com) and start creating!

**⭐ Don't forget to star this repository if you find it useful!**
