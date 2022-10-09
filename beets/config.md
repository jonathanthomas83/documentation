# Beets installation and config

1. Create a virtual environment

2. Install beets

3. Config for use on remote server:

```yaml
# Beets configuration --------------------------------------------------------

# important to use the tilda when on shared servers
library: ~/music/library.db
directory: ~/music/

import:
    # write metadata to music files
    write: yes
    
    # move imported files from source to the music directory
    copy: yes
    move: no
    
    # do not require confirmation on strong matches
    timid: no
    
    resume: ask
    log: beetslog.txt
    
# files matching these patterns are deleted from source after import
clutter: ["Thumbs.DB", ".DS_Store", "*.txt", ".pls", "*.jpg", "*.pdf"]

# use the release-date of the original (first) release of an album?
original_date: yes

# on multi-disk releases, assign track numbers for the whole album.
# If "per disk", make sure tracknames do not collide ("paths" setting).
per_disc_numbering: no
    

# Paths ----------------------------------------------------------------------

asciify_paths: yes
original_date: yes

# Paths and filenames for music files
# relative to music directory

paths:
    default: artists/$albumartist_sort/$original_year $album%aunique{}/$track $title
    albumtype:ep: artists/$albumartist_sort/$original_year $album%aunique{} - EP/$track $title
    albumtype:single: artists/$albumartist_sort/$original_year $album%aunique{} - Single/$track $title
    albumartist:Various Artists: compilations/$album%aunique{} $original_year/$track $artist - $title
    
# replace special characters in generated filenames
replace:
    '[\\/]': _
    '^\.': _
    '[\x00-\x1f]': _
    '[<>:"\?\*\|]': _
    '\.$': _
    '\s+$': ''
    '^\s+': ''
    
    
# General --------------------------------------------------------------------

# use mutliple threads during import
threaded: yes
timeout: 5.0
verbose: no
   
   
# User Interface -------------------------------------------------------------

color: yes
list_format_item: %upper{$artist} - $album - $track. $title
list_format_album: %upper{$albumartist} - $album
time_format: '%Y-%m-%d %H:%M:%S'
terminal_encoding: utf8

ui:
    terminal_width: 80
    length_diff_thresh: 10.0
```