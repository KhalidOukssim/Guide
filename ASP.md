# 01 - WebPage

### a.Razor

```asp
@{
int a=12;
}
<p>OUR NUMBER IS @a</p>
```

### b.Layout

```asp
<html>
    <body>
      @RenderPage("header.cshtml");//add a Header to the page
        <p>Layout paragraphe</p>
    </body>
</html>
```

```asp
<html>
    <body>
        @RenderBody();
    </body>
</html>

@{Layout="Layout.cshtml";}
<p>this is a body to add</p>

```

if a name start with _ it means that its a hidden file that can not thr user access to.

### c.folders

```asp
var myImageFodler="~/images/img.jpg"; //~ is an operator To specify the virtual root in programming code
```

we use the href method to let the browser understund "~".

```asp
@{var mySteel="~/images/img.jpg"}
<link rel="stylsheet" href="@Href(mySteel)"/>
```

### d.global

_AppStart is startup code and initialization of global values like counters and global names.

Just like _AppStart runs before your site starts, you can write code that runs before any page in each folder in _PageStart.

![](C:\Users\hp\Desktop\MyTutorials\Images\pic_webpages_pagestart.jpg)

### e.Forms

```asp
if(Request["name"] != null)//we use Request to have the value of name;
```

### f.Files

#### Server.MapPath finds the exact text file path.

#### File.ReadAllLines opens the text file and reads all lines from the file into an array.

### g.DataBases