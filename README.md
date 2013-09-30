Simple-File-Upload-Class
========================

A simple file upload class made to validate and create thumbs for image files


require('class/kusipet_upload');<br />
$upload = new kusipet_upload();<br />


$config = array(<br />
    	//'new_name'=>'Minion',<br />
    'path' => 'public/uploads/', <br />
    'max_size' => 700000, //70kb<br />
    //for image<br />
    'allowed_ext' => array("doc", "docx", "txt", "xls"),<br />
    //'thumb_suf' => '_thumb',//default<br />
    //'thumb_path' => 'public/uploads/thumb/', //if not set, no thumbnail will be created<br />
    //'thumb_width' => '50',<br />
    //'thumb_height' => '50',<br />
    //'ratio' => 'true', //keeps the ration when resizing the image to thumbnails<br />
    //'max_height' => '700',<br />
    //'max_width' => '400',<br />
    //for naming<br />
    //'md5'=>true,<br />
    'auto_rename' => true,<br />
    //'name_add_pre' => 'prefix_',<br />
    //'name_add_suf' => '_suffix',<br />
    //'mime_types'=>array('text/plain', 'application/octet-stream') //strict to mime types<br />
);

<br /><br />
$handle = $upload->do_upload('image', $config);<br />
if ($handle) {<br />
    echo 'Success!';<br />
} else {<br />
    echo 'error:'.$upload->get_error();<br />
}
