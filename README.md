YouTube Video Downloader :fa-download:

###### This EXE App Is Writte In Python And You Get The Source And the Softwere Itself Up In My Github 

------------

Is It Safe? :fa-search-plus:
####Yes, You Pc is 100% Safe You Can Check The Code Your Self 

------------

The Raw Code Or The EXE? :fa-exclamation-circle:
####The EXE Coz It Is Easy To Setup+Fast

------------

Where is my downloads? :fa-tasks:
They Are In Your `Videos` Folder 

------------

Google Drive Link For EXE - https://drive.google.com/file/d/19ZT7u1FoFEWoZUmtyBlWlAVBJP8VfZUR/view?usp=sharing

------------


RawCode
```python
import pytube
from pytube.cli import on_progress
from os.path import expanduser
 
def download():
    url = input('Enter YouTube video link: ')
 
    try:
        video = pytube.YouTube(url, on_progress_callback = on_progress)
        print('\nTitle: ' + video.title + '\n')
 
        for i in video.streams:
            print(str(video.streams.index(i)+1) + '\tType: ' + str(i.mime_type) + ' | Res: ' + str(i.resolution) + ' | FPS: ' + str(i.fps))
 
        ii = int(input('\nEnter index of needed video options: '))
        stream = video.streams.filter(mime_type = video.streams[ii-1].mime_type, resolution = video.streams[ii-1].resolution)
        stream.first().download(expanduser('~/Videos'))
 
    except EOFError as err:
        print(err)
 
    else:
        print('Done!')
 
    one_more()
 
def one_more():
    print('\n')
    download()
 
download()
```
