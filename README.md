# Encadro — Support

Encadro turns an iPhone screen recording into a framed product demo: a real
device mockup on a background you choose, with zoom moves and tap feedback on a
timeline, exported ready to post.

**Requires macOS 14 (Sonoma) or later.**

## Getting help

Email **support@luistorres.app**. Please include:

- what you were doing when it went wrong,
- your macOS version (Apple menu → About This Mac),
- the Encadro version (Encadro → About Encadro),
- and, if it involves a specific recording, how long it is and what device it
  came from.

## Common questions

**Does Encadro record my screen?**
No. Record on your iPhone (Control Centre → Screen Recording), then bring the
file to your Mac and bring it into Encadro — drag it onto the window, or use
**File ▸ Import Recording…** (⇧⌘I). Encadro is the part that makes the
recording look good. (⌘O opens a saved Encadro project, not a recording.)

**Is my work saved when I quit?**
Yes. A project is a real macOS document. Press **⌘S** and the whole session —
the recording, its trim, every zoom and tap, the framing and the background —
is written to a `.encadro` file wherever you keep your work. **⌘O**, **Open
Recent**, **Duplicate**, **Rename**, **Versions** and autosave all behave the
way they do in any other Mac app.

**Can I delete the original screen recording afterwards?**
Yes. The recording is copied *inside* the `.encadro` document, and so is any
image you used as a background. Bin the original files, or hand the `.encadro`
to someone on another Mac, and it still opens with the video and the look
intact. Nothing in a saved project points at a file elsewhere on your disk.

**My video already has a phone around it.**
You have most likely re-imported a video Encadro already exported. Exports are
named `Encadro-export.mp4` by default (`Encadro-export.mov` for a transparent
one), so check the filename. Start from the original screen recording instead.

**How do I get a transparent background?**
Set Background to **None**. The export switches to `.mov` with HEVC and a real
alpha channel, which you can drop straight into Final Cut, Premiere, After
Effects or Keynote without masking. Note that not every app or web player
supports alpha video — if the background comes out black somewhere, that player
is ignoring the alpha channel.

**What is a saved template?**
Everything about a look — device, colour, background, shadow, framing — plus
your zoom and tap timing. Timing is stored proportionally, so a template built
on a twelve second clip still lands correctly on a forty second one. If the
template carries motion and your timeline already has some, Encadro asks before
touching it — **Replace**, **Keep mine** (apply the look only) or **Cancel** —
because there is no undo.

**Where are my templates stored?**
`~/Library/Containers/com.luistorres.Encadro/Data/Library/Application Support/Encadro/`
— a `my-templates.json` file plus a `TemplateAssets` folder holding a copy of
any background image you picked. Saved projects are separate: those are the
`.encadro` documents you save yourself, wherever you put them.

**Does Encadro send anything anywhere?**
No. There is no networking code in the app at all. See the
[privacy policy](PRIVACY.md).

## Accessibility

Encadro answers **yes to six of the eight** items on Apple's App Store
accessibility questionnaire: Dark Interface, Reduced Motion, Sufficient
Contrast, Differentiate Without Color, VoiceOver and Voice Control. The other
two — Captions and Audio Descriptions — do not apply, because Encadro presents
no captioned media.

- **VoiceOver reaches the timeline.** Every zoom block, every tap block and the
  playhead are focusable and speak their position — *"Zoom, 2.0 times, 1.5
  seconds — Starts at 3.2 seconds"*. VoiceOver's adjustable gesture moves a
  block a step at a time and speaks its new start, and each block carries
  custom actions for Edit, Duplicate and Delete.
- **A Timeline menu of 30 commands**, in seven sections — Selection, Blocks,
  Adjust Selected Block, Playhead, Playback, Clip and Trim, Canvas — gives
  every timeline action a named keyboard route. Adding, selecting, nudging,
  resizing, trimming and moving the phone all work without a mouse, and a
  command that cannot run says why (*"Last block"*, *"No block at the
  playhead"*) rather than doing nothing silently. The menu doubles as the
  shortcut cheat sheet.
- **Voice Control works by name** rather than by numbered overlays — *"click
  Play or Pause"*, *"click Export"*, *"click Shadow colour"*.
- **Reduce Motion is honoured** across the launch splash, the editor panel and
  the trim handle, which swaps its scale cue for a change in width.
- **No state is signalled by colour alone.** Selections carry a checkmark,
  out-of-trim blocks carry a dashed border, drop targets change symbol, and
  disabled buttons show their reason as text instead of only on hover.

**What is not covered yet**, so you know before you rely on it:

- **Full Keyboard Access tab order has not been verified.** Tabbing through the
  sidebar and panels should reach everything, but the *order* it visits them in
  has not been checked and may jump around.
- **Larger Text is not supported in the timeline.** Most type there is a fixed
  size inside a fixed-height track.
- **Gradient swatches announce as "Gradient preset 3"** rather than by name.

If something here does not work as described, please email
**support@luistorres.app** — these behaviours are checked by hand, so a report
is the fastest way they get fixed.

## Known limitations

- Tap and zoom focus positioning assumes portrait recordings; landscape footage
  frames correctly but focus points may be off.
- **There is no undo.** Undo and redo are designed but not built yet, which is
  why anything destructive — applying a template over existing motion, for
  instance — stops and asks first. Your saved work is safe; it is the last edit
  inside a session that cannot be taken back.
- iPhone frame artwork is around 450×920 (473×932 for the iPhone 15 Pro), which
  is ample for 1080p output and may soften above it.

## Privacy

Encadro collects no data. Full policy: [PRIVACY.md](PRIVACY.md).
