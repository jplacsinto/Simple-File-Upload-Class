Simple-File-Upload-Class
========================

A simple file upload class made to validate and create thumbs for image files


require('class/kusipet_upload');
$upload = new kusipet_upload();


$config = array(
    //'new_name'=>'Minion',
    'path' => 'public/uploads/',
    'max_size' => 700000, //70kb
    //for image
    'allowed_ext' => array("doc", "docx", "txt", "xls"),
    //'thumb_suf' => '_thumb',//default
    //'thumb_path' => 'public/uploads/thumb/', //if not set, no thumbnail will be created
    //'thumb_width' => '50',
    //'thumb_height' => '50',
    //'ratio' => 'true', //keeps the ration when resizing the image to thumbnails
    //'max_height' => '700',
    //'max_width' => '400',
    //for naming
    //'md5'=>true,
    'auto_rename' => true,
    //'name_add_pre' => 'prefix_',
    //'name_add_suf' => '_suffix',
    //'mime_types'=>array('text/plain', 'application/octet-stream') //strict to mime types
);


$handle = $upload->do_upload('image', $config);
if ($handle) {
    echo 'Success!';
} else {
    echo 'error:'.$upload->get_error();
}
