Ajax-upload-previewer
=====================

<p>Dynamic show preview of the selected image before upload it, by jQuery.</p>

<ol>
<li> demo.html     -&gt; is the base version that is easy for edit.</li>
<li> no_image.gif  -&gt; display if user haven't upload image.</li>
</ol>

<p>We would use no_image.gif if user haven't upload any image. Display what user have selected immediately. Must test in your localhost or server.</p>
<p>Demo link is here: <br />
http://tool.soyosolution.com/ajax_upload_images/demo.html</p>

<h1>Javascript part:</h1>
<p>firstly, you must import a jquery file for this:</p>
<pre>&lt;script class="jsbin" src="http://ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"&gt;&lt;/script&gt;</pre>
<p>And there is the core Javascript part for the Ajax Image upload Previewer:</p>

<pre>&lt;script type="text/javascript"&gt;<br />
function PreviewImage(no) {<br />
var oFReader = new FileReader();<br />
oFReader.readAsDataURL(document.getElementById("uploadImage"+no).files[0]);<br />
oFReader.onload = function (oFREvent) {<br />
document.getElementById("uploadPreview"+no).src = oFREvent.target.result;<br />
};<br />
} <br />
&lt;/script&gt;</pre>

<h1>HTML part:</h1>
<pre>
&lt;!--[if IE]&gt;   &lt;script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"&gt;&lt;/script&gt; &lt;![endif]--&gt;
&lt;table&gt;
&lt;tr&gt;
    &lt;td&gt;
        &lt;img id="uploadPreview1" src="no_image.jpg" /&gt;&lt;br /&gt;
        &lt;input id="uploadImage1" type="file" name="p1" onchange="PreviewImage(1);" /&gt;
    &lt;/td&gt;
    &lt;td&gt;
        &lt;img id="uploadPreview2" src="no_image.jpg" /&gt;&lt;br /&gt;
        &lt;input id="uploadImage2" type="file" name="p2" onchange="PreviewImage(2);" /&gt;
    &lt;/td&gt;
    &lt;td&gt;
        &lt;img id="uploadPreview3" src="no_image.jpg" /&gt;&lt;br /&gt;
        &lt;input id="uploadImage3" type="file" name="p3" onchange="PreviewImage(3);" /&gt;
    &lt;/td&gt;
    &lt;td&gt;
        &lt;img id="uploadPreview4" src="no_image.jpg" /&gt;&lt;br /&gt;
        &lt;input id="uploadImage4" type="file" name="p4" onchange="PreviewImage(4);" /&gt;
    &lt;/td&gt;    
&lt;/tr&gt;
&lt;/table&gt;
</pre>

<p>For detail, please visit the website:<br />
http://tool.soyosolution.com/ajax_upload_images/</p>
