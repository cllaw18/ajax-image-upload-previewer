ajax-upload-previewer
=====================

Dynamic show preview of the selected image before upload it, by jQuery.

1) demo.html     -> is the base version that is easy for edit.
2) no_image.gif  -> display if user haven't upload image.

We would use no_image.gif if user haven't upload any image.
Display what user have selected immediately. Must test in your localhost or server



##########################################################
                      HOW TO USE
##########################################################
Javascript part:
----------------
firstly, you must import a jquery file for this

<script class="jsbin" src="http://ajax.googleapis.com/ajax/libs/jquery/1/jquery.min.js"></script>
And there is the core Javascript part for the Ajax Image upload Previewer:

<script type="text/javascript">
function PreviewImage(no) {
var oFReader = new FileReader();
oFReader.readAsDataURL(document.getElementById("uploadImage"+no).files[0]);
oFReader.onload = function (oFREvent) {
document.getElementById("uploadPreview"+no).src = oFREvent.target.result;
};
} 
</script>

HTML part:
----------------
<!--[if IE]>   <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script> <![endif]-->
<table>
<tr>
    <td>
        <img id="uploadPreview1" src="no_image.jpg" /><br />
        <input id="uploadImage1" type="file" name="p1" onchange="PreviewImage(1);" />
    </td>
    <td>
        <img id="uploadPreview2" src="no_image.jpg" /><br />
        <input id="uploadImage2" type="file" name="p2" onchange="PreviewImage(2);" />
    </td>
    <td>
        <img id="uploadPreview3" src="no_image.jpg" /><br />
        <input id="uploadImage3" type="file" name="p3" onchange="PreviewImage(3);" />
    </td>
    <td>
        <img id="uploadPreview4" src="no_image.jpg" /><br />
        <input id="uploadImage4" type="file" name="p4" onchange="PreviewImage(4);" />
    </td>    
</tr>
</table>

##########################################################
                      HOW TO USE
##########################################################
For detail, please visit the website:
http://tool.soyosolution.com/ajax_upload_images/
