Overlaying eps files
====================
Based on
    http://stackoverflow.com/questions/9820646/overlay-two-postscript-files-command-line-approach

Create a ps file 'overlay_tmp.ps' with the following contents:
------------------------------------------------------------------------------
/Oldshowpage /showpage load def
/showpage {} def
gsave
    (layer_1.eps) run
grestore
    (layer_2.eps) run
Oldshowpage
------------------------------------------------------------------------------
Figures 'layer_1.eps' and 'layer_2.eps' contain the layers of the resulting
image.

A final figure can be obtained by calling
    'eps2eps -I. overlay_tmp.ps  result.eps',
where '-I.' specifies the folder, where the included files are located. 'ps2ps'
can be used as well.



Fix broken fonts (missing letters) in PDF
=========================================

1. convert pdf to ps
2. convert ps back to pdf using
`ps2pdf -dPDFSETTINGS=/prepress -dSubsetFonts=true -dEmbedAllFonts=true -dMaxSubsetPct=100 -dCompatibilityLevel=1.3`



Reduce size (density of images)
===============================
    gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dDownsampleColorImages=true \
    -dColorImageResolution=100 -dNOPAUSE -dBATCH -sOutputFile=output.pdf input.pdf


Join two sequential pages to one (e.g. 2xA5 -> A4)
==================================================
    pdfjam --nup '1x2' --no-landscape -- <filename>
