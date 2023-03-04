# draculize_notes
Have some scanned Paper notes and moving it to digital world, where you love [Dracula Color Scheme](https://draculatheme.com/)? You might need this!

# Motivation

I have a shit ton of handwritten notes which I would love to read digitally, annotate them and keep making new notes as I learn new things. The problem,
well the scanned notes are "light mode" (they are written on White paper with Blue/Black and colored ink). However, when I like to read something digitally
I like to use dark mode since it is easier on the eyes, plus I am a big fan of Dracula (A *universal* Dark theme). 
In some pdf readers you can invert the color however, this inversion does not work well for Scanned PDFs. In addition to that I use 
[GoodNotes](https://www.goodnotes.com/) on my iPad which does not support dark mode for PDF as of now. Any new notes that I take are Dracula color themed
and I personally hate the disconnect between my scanned and new notes. This I feel is a good enough motivation for me to deal with this issue in all
seriousness once in for all.

# Procedure

(All the working will be shown for 5 Random sampled images from my notes)

1. Scan your notes. 

2. Use [Noteshrink](https://github.com/mzucker/noteshrink) to *shrink* and perform post-processing on the notes. 
The command used is `noteshrink -w -g [IMAGES]`. I used a global palette so that majority of k-means clustering is done using the Noteshrink Algorithm
which is pretty much optimized for scanned notes purposes. The notes are still in Light mode though.

# Draculization of the *shrinked* notes

For the initial approach, I had in mind was that since I would be limiting the color palette then hardcoding each color palette color to the color that
I want represented. However, I would have to change the code for every different color palette. Additionally, using a global palette meant that I 
lost on certain number of colors just because they were used less on an average of 100 pages which was the typical size of notes I used for global
palette generation. 

Another tempting idea was to do this color transformation within the noteshrink code itself. However, I would have lost the modularity with 
this approach. Hence the below approach. (Of course this is subject to change as I am still in conception phase).

## Dracula Theme Color Palette

[Source](https://github.com/dracula/dracula-theme)

| Palette      | Hex       | RGB           | HSL             | ![Color Picker Boxes](https://draculatheme.com/static/img/color-boxes/eyedropper.png)   |
| ------------ | --------- | ------------- | --------------- | --------------------------------------------------------------------------------------- |
| Background   | `#282a36` | `40 42 54`    | `231° 15% 18%`  | ![Background Color](https://draculatheme.com/static/img/color-boxes/background.png)     |
| Foreground   | `#f8f8f2` | `248 248 242` | `60° 30% 96%`   | ![Foreground Color](https://draculatheme.com/static/img/color-boxes/foreground.png)     |
| Comment      | `#6272a4` | `98 114 164`  | `225° 27% 51%`  | ![Comment Color](https://draculatheme.com/static/img/color-boxes/comment.png)           |
| Cyan         | `#8be9fd` | `139 233 253` | `191° 97% 77%`  | ![Cyan Color](https://draculatheme.com/static/img/color-boxes/cyan.png)                 |
| Green        | `#50fa7b` | `80 250 123`  | `135° 94% 65%`  | ![Green Color](https://draculatheme.com/static/img/color-boxes/green.png)               |
| Orange       | `#ffb86c` | `255 184 108` | `31° 100% 71%`  | ![Orange Color](https://draculatheme.com/static/img/color-boxes/orange.png)             |
| Pink         | `#ff79c6` | `255 121 198` | `326° 100% 74%` | ![Pink Color](https://draculatheme.com/static/img/color-boxes/pink.png)                 |
| Purple       | `#bd93f9` | `189 147 249` | `265° 89% 78%`  | ![Purple Color](https://draculatheme.com/static/img/color-boxes/purple.png)             |
| Red          | `#ff5555` | `255 85 85`   | `0° 100% 67%`   | ![Red Color](https://draculatheme.com/static/img/color-boxes/red.png)                   |
| Yellow       | `#f1fa8c` | `241 250 140` | `65° 92% 76%`   | ![Yellow Color](https://draculatheme.com/static/img/color-boxes/yellow.png)             |

## Transform Table

