---
layout:     post
title:      Upload-labs 20
subtitle:   Upload-labs 20 通关笔记
date:       2019-06-01
author:     yu
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    -
---

upload_labs

代码：


```
if (isset($_POST['submit'])) {
    if (file_exists(UPLOAD_PATH)) {

        $is_upload = false;
        $msg = null;
        if(!empty($_FILES['upload_file'])){
            //mime check
            $allow_type = array('image/jpeg','image/png','image/gif');
            if(!in_array($_FILES['upload_file']['type'],$allow_type)){
                $msg = "禁止上传该类型文件!";
            }else{
                //check filename
                $file = empty($_POST['save_name']) ? $_FILES['upload_file']['name'] : $_POST['save_name'];
                if (!is_array($file)) {
                    $file = explode('.', strtolower($file));
                }

                $ext = end($file);
                $allow_suffix = array('jpg','png','gif');
                if (!in_array($ext, $allow_suffix)) {
                    $msg = "禁止上传该后缀文件!";
                }else{
                    $file_name = reset($file) . '.' . $file[count($file) - 1];
                    $temp_file = $_FILES['upload_file']['tmp_name'];
                    $img_path = UPLOAD_PATH . '/' .$file_name;
                    if (move_uploaded_file($temp_file, $img_path)) {
                        $msg = "文件上传成功！";
                        $is_upload = true;
                    } else {
                        $msg = "文件上传失败！";
                    }
                }
            }
        }else{
            $msg = "请选择要上传的文件！";
        }
        
    } else {
        $msg = UPLOAD_PATH . '文件夹不存在,请手工创建！';
    }
}

```


###代码的重点在于:
`$file_name = reset($file) . '.' . $file[count($file) - 1];`

注解：以" . "为分隔符，截取第一个字段，加 . 加后缀





