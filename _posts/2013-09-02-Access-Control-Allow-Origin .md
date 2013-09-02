---
layout: default
title: Access-Control-Allow-Origin 
---
#使用Access-Control-Allow-Origin实现ajax跨域请求

前端

	function createCORSRequest(method, url) {
	  var xhr = new XMLHttpRequest();
	  if ("withCredentials" in xhr) {
	    // 此时即支持CORS的情况
	    // 检查XMLHttpRequest对象是否有“withCredentials”属性
	    // “withCredentials”仅存在于XMLHTTPRequest2对象里
	    xhr.open(method, url, true);
	 
	  } else if (typeof!= "undefined") {
	 
	    // 否则检查是否支持XDomainRequest，IE8和IE9支持
	    // XDomainRequest仅存在于IE中，是IE用于支持CORS请求的方式
	    xhr = new XDomainRequest();
	    xhr.open(method, url);
	 
	  } else {
	 
	    // 否则，浏览器不支持CORS
	    xhr = null;
	 
	  }
	  return xhr;
	}
	 
	var xhr = createCORSRequest('GET', url);
	if (!xhr) {
	  throw new Error('CORS not supported');
	}

页面头部需设置Access-Control-Allow-Origin属性
