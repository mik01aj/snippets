

Rename all photos in a folder, based on their dates:
    
    exiftool -CreateDate -d %Y-%m-%d/%H%M_%%f.%%e .
    
And then:
    
    exiftool '-FileName<CreateDate' -d %Y%m%d_%H%M_%%f.%%e .
    
to rename them.
