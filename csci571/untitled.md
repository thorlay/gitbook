# Untitled

## Some useful dom functions

* document is the root element

Example 1: Using DOM function to alter a page

```markup
<html><head>
<script language="JavaScript1.2">
hex=255 // Initial color value.
function fadetext(){
if(hex>0) { //If color is not black yet
hex-=11; // increase color darkness
document.getElementById("sample").style.color="rgb("+hex+"," +hex+","+hex+")";
setTimeout("fadetext()",20); }
else hex=255 //reset hex value }
</script></head><body>
<div id="sample" style="width:100%">
<h3>John slowly faded into view</h3></div>
<button onClick="fadetext()">Fade Text</button>
</body></html>
```

Example 2: Extracting Elementd by Tag Name\

```markup
<html><head>
<SCRIPT LANGUAGE="JavaScript"> function handleAllTags()
{ var arrayOfDocFonts;
if (document.all || document.getElementById){ 
arrayOfDocFonts = document.getElementsByTagName("font");
} else { 
 document.write("Unrecognized Browser Detected"); }
alert("Number of font tags in this document are " + arrayOfDocFonts.length + ".");
}
</SCRIPT> </head><body>
<h1><font COLOR="#0000cc">Font1</font></h1> 
<h2><font COLOR="#00cc00">Font2</font></h2> 
<h3><font COLOR="#cc0000">Font3</font></h3>
<h3><font COLOR="#cccccc">Font4</font></h4> 
<input type=button onclick="handleAllTags()" value="Count Font Tags"> 
</body></html>
```

### 

InnerHTML property​

