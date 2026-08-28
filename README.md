# ytfzf custom

A custom terminal-based YouTube Music player written entirely in Bash.

This is an old project that took around **8 months of development**. It started as a small experiment and slowly turned into a complete TUI for searching and playing YouTube music directly from the terminal.

Inspired by **fff (Fucking File Manager)**.

> Built for the terminal. No fancy GUI, just Bash, fzf, mpv, and questionable amounts of free time.

## ✨ Features

* 🔎 Search YouTube music directly from the terminal
* 🎵 Play tracks using `mpv`
* 📋 Interactive TUI powered by `fzf`
* 🖼️ YouTube thumbnail preview
* 🖥️ SIXEL image support through `chafa`
* 🎤 Synced lyrics through LRCLIB
* 🔄 Lyrics fallback search
* ⚡ Temporary thumbnail caching
* ⌨️ `j` / `k` navigation
* 🚫 Filters out live videos from search results
* 📱 Designed with Termux in mind

## 📦 Dependencies

Make sure these programs are installed:

```text
bash
fzf
jq
curl
awk
mpv
yt-dlp
chafa
img2sixel
```

### Termux

On Termux, install the required packages with:

```bash
pkg install bash fzf jq curl gawk mpv yt-dlp chafa
```

`img2sixel` is required if you want to use SIXEL image output.

## 🚀 Usage

Make the script executable:

```bash
chmod +x ytfzf
```

Then run:

```bash
./ytfzf
```

Enter a search query and select a track using `fzf`.

Press `Enter` to start playback.

You can also use:

```text
j → move down
k → move up
```

## 🎤 Lyrics

Lyrics are fetched from **LRCLIB**.

The script first searches using the detected track name and falls back to the video title if no synced lyrics are found.

Lyrics are then passed directly to `mpv` as an `.lrc` subtitle file.

> Lyrics availability depends on the source. Not every song will have synced lyrics.

Lyrics matching is not perfect either, so sometimes the returned lyrics may not be the exact version you expected.

## 🖼️ Thumbnail Preview

The TUI displays YouTube thumbnails using `chafa` with SIXEL output.

The thumbnails are temporarily cached while the program is running to avoid downloading the same image repeatedly.

The cache is automatically removed when the script exits.

## ⚠️ Known Issues

### tmux / zellij

Scrolling may become laggy when running the script inside:

* tmux
* zellij

### Performance

Some operations can be a little slow, especially metadata searching and thumbnail loading.

I've optimized it as much as I could, but it's still a Bash script doing things that probably shouldn't be done in Bash.

## 🧪 Compatibility

The project was mainly developed and tested in a **Termux environment**.

Other Linux environments may work as long as all dependencies are available.

## 📝 Notes

This project is considered **finished for now**.

After spending around 8 months working on it, I'm taking a long break from Termux.

So don't expect frequent updates, maintenance, or detailed explanations of every part of the code.

If you want to understand how it works, feel free to read the source and experiment with it yourself.

That's basically how I built it in the first place.

## 🔧 Customization

The script is intentionally kept as a single Bash file, so customization should be relatively straightforward.

You can modify things such as:

* fzf colors
* key bindings
* layout
* preview size
* thumbnail rendering
* metadata formatting
* lyrics handling
* mpv arguments

Fork it, break it, fix it, make it weird.

## 📜 License

Currently, this project does **not include a license**.

If you want to reuse or redistribute the code, check the repository's licensing status first.

## ⭐ Final words

This started as a simple idea and somehow turned into an 8-month project.

If you find it useful, cool.

If you find something broken, feel free to fix it.

I'm probably somewhere riding a bicycle instead of debugging Bash.

---

**Made with Bash, fzf, mpv, yt-dlp, and too much time.**


