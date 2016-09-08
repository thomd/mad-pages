
# youtube-dl(1)

Download videos and songs

## Installation

Homebrew installation

    brew install youtube-dl

UNIX installation with curl

    sudo curl https://yt-dl.org/downloads/2014.09.06/youtube-dl -o /usr/local/bin/youtube-dl
    sudo chmod a+x /usr/local/bin/youtube-dl

## Supported Sites

List all available sites

    youtube-dl --extractor-descriptions

## Download

    youtube-dl https://soundcloud.com/jayelectronica/act-1-eternal-sunshine-the-pledge

List available formats

    youtube-dl -F https://vimeo.com/48858289

and download a specific format with

    youtube-dl -f http\_mp3\_128\_url https://vimeo.com/48858289

## Templates

    youtube-dl --cookies COOKIES.txt -o 'eventedmind/%(playlist_title)s/%(title)s.%(ext)s' https://www.eventedmind.com/classes/ansible-a0b2c69d
