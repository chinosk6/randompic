<?php
function get_allfiles($path,&$files) {
    if(is_dir($path)){
        $dp = dir($path);
        while ($file = $dp ->read()){
            if($file !="." && $file !=".."){
                get_allfiles($path."/".$file, $files);
            }
        }
        $dp ->close();
    }
    if(is_file($path)){
        $files[] =  $path;
    }
}
   
function get_filenamesbydir($dir){
    $files =  array();
    get_allfiles($dir,$files);
    return $files;
}

//文件夹处
$img_array = get_filenamesbydir("./img");

$extentions = array("jpg", "png");

do{
    $img = array_rand($img_array);
}while(!in_array(strtolower(pathinfo($img_array[$img], PATHINFO_EXTENSION)), $extentions));
//302
header("location:$img_array[$img]"); 
?>
