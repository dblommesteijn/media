### Overview
The jQuery Media Plugin supports unobtrusive conversion of standard markup into rich media content. It can be used to embed virtually any media type, including Flash, Quicktime, Windows Media Player, Real Player, MP3, Silverlight, PDF and more, into a web page. The plugin converts an element (usually an `<a>`) into a `<div>` which holds the object, embed or iframe tags neccessary to render the media content.

[http://jquery.malsup.com/media/]

**For example, running this script:**

`$('.media').media();`

**For this markup:**
```html
<a class="media" href="sample.mov">My Quicktime Movie</a>
<a class="media" href="sample.swf">My Flash Movie</a>
<a class="media" href="sample.wma">My Audio File</a>
```

*will result in this1:*
```html
<div class="media">
    <object codebase="http://www.apple.com/qtactivex/qtplugin.cab"
        classid="clsid:02BF25D5-8C17-4B23-BC80-D3488ABDDC6B">
        <param name="src" value="sample.mov">
        <embed src="sample.mov"
            pluginspage="http://www.apple.com/quicktime/download/"></embed>
    </object>
    <div>My Quicktime Movie</div>
</div>

<div class="media">
    <object codebase="http://fpdownload.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=7"
        classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000"
        type="application/x-oleobject">
        <param name="src" value="sample.swf">
        <embed src="sample.swf"
            type="application/x-shockwave-flash"
            pluginspage="http://www.adobe.com/go/getflashplayer"></embed>
    </object>
    <div>My Flash Movie</div>
</div>

<div class="media">
    <object codebase="http://www.apple.com/qtactivex/qtplugin.cab"
        classid="clsid:6BF52A52-394A-11d3-B153-00C04F79FAA6"
        type="application/x-oleobject">
        <param name="url" value="sample.wma">
        <embed src="sample.wma"
            type="application/x-mplayer2"
            pluginspage="http://www.microsoft.com/Windows/MediaPlayer/"></embed>
    </object>
    <div>My Audio File</div>
</div>
```

*[1] Note that the plugin generates either `<object>` or `<embed>` tags as necessary for the platform; not both.*