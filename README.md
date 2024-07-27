## Little python tool to rename a font

Some GUI applications allow the user to select a font for use in the UI but restrict those fonts to certain font families groups. I common example is Ereader apps (like `koreader`) that allow the use of fallback fonts, but only of type "Noto Sans", since for Western script, Sans Serif fonts are the accepted standard. Unfortunately, Tibetan is by it's very nature a Serif script, and therefore Google only provides a "Noto Serif Tibetan" font. Just renaming the font-file doesn't work, since the name of the font is stored in the font-file itself. This tool allows you to rename the font in a way that it will be accepted by the application.

**TLDR: I just want `Tibetan Sans Tibetan.ttf`**: Download a pre-converted font-file [here](blob:https://github.com/493f21aa-2310-48a9-b42e-39556eca4c3d)

### General Usage

Create a virtual environment and install the requirements:

```bash
git clone https://github.com/DigitalTibetan/FontRenamer.git
python -m venv FontRenamer
cd FontRenamer
source bin/activate
pip install -Ur requirements.txt
```

Then run the script with the path to the font-file and the new name of the font:

```bash
python font_renamer.py <path-to-old-font-file.ttf> <path-to-new-font-file.ttf> "New Font Name"
```

### Transforming Noto Serif Tibetan to Noto Sans Tibetan

Download the latest version of Noto Serif Tibetan from [Google Noto Fonts](https://fonts.google.com/noto/specimen/Noto+Serif+Tibetan). Unpack the archive, and look for the main font file. It might be named something like `NotoSerifTibetan-VariableFont_wght.ttf` (Google likes to rename things). Copy the font into this (FontRenamer) directory and then convert the Serif font to a Sans font (by name only):

```bash
python font_renamer.py NotoSerifTibetan-VariableFont_wght.ttf "Noto Sans Tibetan.ttf" "Noto Sans Tibetan"
```

### Alternative: use the pre-converted font

If you don't want to go through the hassle of renaming the font, you can also use the pre-converted font that is included in this repository. It is the 2024-07 version of the Noto Serif Tibetan font, renamed to "Noto Sans Tibetan". You can find it in the [`Resources`](https://github.com/DigitalTibetan/FontRenamer/blob/main/Resources/) directory.

## Resources

- A version of Noto Serif Tibetan renamed internally to [`Tibetan Sans Tibetan.ttf`](https://github.com/DigitalTibetan/FontRenamer/blob/main/Resources/Noto%20Sans%20Tibetan.ttf)
