# draculize_notes
Have some scanned Paper notes and moving it to digital world, where you love [Dracula Color Scheme](https://draculatheme.com/)? You might need this!

# Motivation

I have a shit ton of handwritten notes which I would love to read digitally, annotate them and keep making new notes as I learn new things. The problem,
well the scanned notes are "light mode" (they are written on White paper with Blue/Black and colored ink). However, when I like to read something digitally
I like to use dark mode since it is easier on the eyes, plus I am a big fan of Dracula (A *universal* Dark theme). 
In some pdf readers you can invert the color however, this inversion does not work well for Scanned PDFs. In addition to that I use 
[GoodNotes] (https://www.goodnotes.com/) on my iPad which does not support dark mode for PDF as of now. Any new notes that I take are Dracula color themed
and I personally hate the disconnect between my scanned and new notes. This I feel is a good enough motivation for me to deal with this issue in all
seriousness once in for all.

# Procedure

(All the working will be shown for 5 Random sampled images from my notes)

1. Scan your notes. 

2. Use [Noteshrink](https://github.com/mzucker/noteshrink) to *shrink* and perform post-processing on the notes. 
The command used is `noteshrink -w -g [IMAGES]`. I used a global palette so that majority of k-means clustering is done using the Noteshrink Algorithm
which is pretty much optimized for scanned notes purposes. The notes are still in Light mode though.

3. Read the image in HSV color space using openCV.

4. Apply the Dracula Palette.

