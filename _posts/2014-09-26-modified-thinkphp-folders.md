---
layout: post
title: 自定义ThinkPHP目录结构
category: 开发
tags: 开发
keywords: 开发 
description: 
---

# 入口文件
	' <?php
    // 应用入口文件
     
    // 检测PHP环境
    if(version_compare(PHP_VERSION,'5.3.0','<'))  die('require PHP > 5.3.0 !');
     
    // 网站文件入口位置
    define('ABSPATH', dirname(__FILE__) . '/');
     
    // 定义应用目录
    define('APP_NAME', 'WEBSITE');
    define('APP_PATH','./include/');
    define('CONF_PATH', ABSPATH . '/config/');
    define('RUNTIME_PATH', ABSPATH . '/cache/');
    define('TMPL_PATH', ABSPATH . '/templates/');
    define('UPLOAD_PATH', ABSPATH . '/uploads/');
    define('THINK_PATH', APP_PATH . '/ThinkPHP/');
     
    // 开启调试模式
    define('APP_DEBUG',True);
     
    // 引入ThinkPHP入口文件
    require THINK_PATH . 'ThinkPHP.php';'

# 配置文件
	<?php
	return array (
	  'DEFAULT_MODULE'   => 'APP',
	  'URL_MODEL'        => '2',
	  'TMPL_PARSE_STRING'=> array(
	    	'__PUBLIC__' => __ROOT__.'/static',
	    	'__UPLOAD__' => __ROOT__.'/uploads'
	  ),
	  'TMPL_FILE_DEPR'   => '_',
	);