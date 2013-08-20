Renaming
---

Rename all photos in a folder to new names, based on their dates:
    
    exiftool '-FileName<CreateDate' -d %Y%m%d_%H%M_%%f.%%e .
    
(use `-CreateDate` instead of `-FileName<CreateDate` to see preview)

Video conversion
---

    for f in DSC_????.MOV; do avconv -i "$f" -c:v libvpx -b:v 2000k "${f%MOV}encoded.MOV"; done
    trash-put DSC_????.MOV


Auto-stitching panoramas
---

Useful commands:

    pto_gen
    PTBatcherGUI --assistant path/file.pto
    PTBatcherGUI --assistant `find -name '*.pto'`
    
