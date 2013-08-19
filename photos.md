
Rename all photos in a folder to new names, based on their dates:
    
    exiftool '-FileName<CreateDate' -d %Y%m%d_%H%M_%%f.%%e .
    
(use `-CreateDate` instead of `-FileName<CreateDate` to see preview)
