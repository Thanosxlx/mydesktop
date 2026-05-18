# MY DESKTOP — Edit Cheat Sheet
A quick reference for maintaining your index.html file on GitHub.

---

## HOW TO EDIT ON GITHUB
1. Go to github.com → open your mydesktop repository
2. Click index.html → click the pencil icon ✏️ (top right)
3. Make your changes
4. Scroll down → click "Commit changes" → "Commit changes" again
5. Wait ~1 minute → hard refresh your site with Ctrl+Shift+R

---

## 1. COLORS
All colors are defined at the top of the file inside :root { }
Find this block near line 11.

  --bg            Background of the whole page
  --surface       Background of buttons and cards
  --border        Lines and borders
  --accent        Blue highlight color (hover borders, glow dot)
  --accent2       Green color (date in header, folder hover)
  --text          Main text color
  --muted         Subtitle text color (under button titles)

HOW TO CHANGE A COLOR
Find the variable name and replace the hex value.

Example — make accent color orange instead of blue:
  BEFORE:  --accent: #4f8ef7;
  AFTER:   --accent: #f79a4f;

Useful color references:
  Blue     #4f8ef7    Green    #7dd3b0    Orange   #f79a4f
  Red      #f76f6f    Purple   #9b7df7    White    #e2e6f0
  Dark bg  #0d0f14    Mid grey #252a38    Light    #a0a8c0

---

## 2. FONT SIZES

Search for the element you want to change and update font-size.

  Page title (MY DESKTOP)       font-size: 15px    → class: topbar-brand
  Clock time                    font-size: 15px    → class: clock-time
  Clock date                    font-size: 11px    → class: clock-date
  Section labels (QUICK LAUNCH) font-size: 11px    → class: section-label
  Button main title             font-size: 15px    → class: launch-btn
  Button subtitle               font-size: 12px    → class: launch-btn .lbl small
  Folder name                   font-size: 15px    → class: folder-header .f-name
  Bookmark links                font-size: 15px    → class: folder-link

HOW TO CHANGE
Find the class in the <style> block and change the px value.

Example — make bookmark links bigger:
  BEFORE:  font-size: 15px;
  AFTER:   font-size: 17px;

---

## 3. QUICK LAUNCH BUTTONS
Each button looks like this — find it in the HTML section:

  <a class="launch-btn fade-up" href="URL" target="_blank" rel="noopener">
    <div class="icon ic-COLORNAME">EMOJI</div>
    <div class="lbl">TITLE<small>SUBTITLE</small></div>
  </a>

TO CHANGE THE URL
  Replace the value inside href="..."

TO CHANGE THE TITLE OR SUBTITLE
  Replace TITLE or SUBTITLE text directly

TO CHANGE THE EMOJI
  Replace the emoji character between > and </div>

TO CHANGE THE ICON BACKGROUND COLOR
  Change ic-COLORNAME to one of: ic-gdrive, ic-onedrive, ic-bitwarden, ic-gmail, ic-outlook
  Or add a custom one in the CSS:
    .ic-custom { background: rgba(255,100,50,0.15); }
  Then use class="icon ic-custom" in the HTML

TO ADD A NEW BUTTON
  Copy an entire <a class="launch-btn ..."> block and paste it after the last one.
  Update the href, emoji, title and subtitle.

TO REMOVE A BUTTON
  Delete the entire <a class="launch-btn ...">...</a> block.

---

## 4. BOOKMARK FOLDERS

Each folder looks like this:

  <div class="folder open">
    <div class="folder-header" onclick="toggleFolder(this)">
      <span class="f-icon">EMOJI</span>
      <span class="f-name">FOLDER NAME</span>
      <span class="chevron">▼</span>
    </div>
    <div class="folder-links">

      <a class="folder-link" href="URL" target="_blank" rel="noopener">
        <div class="fav-fallback">X</div> LINK NAME
      </a>

    </div>
  </div>

TO CHANGE THE FOLDER NAME
  Replace FOLDER NAME between the <span class="f-name"> tags

TO CHANGE THE FOLDER EMOJI
  Replace EMOJI between the <span class="f-icon"> tags

TO ADD A LINK inside a folder
  Copy one <a class="folder-link" ...> block and paste it before the </div> closing the folder-links.
  Update href, the letter inside fav-fallback, and the link name.

  The fav-fallback letter is just the first letter of the site name — for example:
    Google → G    YouTube → Y    Notion → N

TO REMOVE A LINK
  Delete the entire <a class="folder-link" ...>...</a> line.

TO ADD A NEW FOLDER
  Copy an entire <div class="folder open"> ... </div> block.
  Paste it after the last </div> closing the previous folder, inside the folders-grid section.
  Update the folder name, emoji, and all links inside.

TO REMOVE A FOLDER
  Delete the entire <div class="folder open"> ... </div> block.

TO START A FOLDER COLLAPSED (closed by default)
  Change <div class="folder open"> to <div class="folder">

---

## 5. HEADER TITLE
Find this line in the HTML:
  MY DESKTOP
Change the text to anything you like, for example:
  JOHN'S WORKSPACE

---

## 6. FOOTER TEXT
Find this line near the bottom of the HTML:

  MY DESKTOP &nbsp;·&nbsp; stateless &nbsp;·&nbsp; incognito-safe &nbsp;·&nbsp; hosted on github pages

Replace any part of it. The &nbsp;·&nbsp; is just a spaced dot separator.

---

## TIPS
- Always work on GitHub's web editor — no software needed
- Use Ctrl+F in the editor to find text quickly
- If something breaks, click the History tab on GitHub to restore a previous version
- After saving, wait 1 minute then do Ctrl+Shift+R to force refresh
- Test on both desktop and mobile after any change
 
