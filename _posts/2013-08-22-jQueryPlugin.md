---
layout: default
title: jQuery plugin
---
#jquery plugin

####封装对象方法插件

写法1

	;(function(){
		$.fn.functionName = function(options){
			options = $.extend({}, options);
			//code
			return this;
		}
	})(jQuery);

写法2
	
	;(function(){
		$.fn.extend({
			"functionName" : function(options){
				options = $.extend({}, options);
				//code
				return this;
			}
		});
	})(jQuery);

####封装全局函数插件

像$.trim()就是这类插件

	;(function(){
		$.extend({
			ltrim : function(text){
				return (text || "").replace(/^\s+/g, "");
			},
			rtrim : function(text){
				return (text || "").replace(/\s+$/g, "");
			}
		});
	})(jQuery);

####选择器插件