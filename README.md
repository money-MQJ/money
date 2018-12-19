
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		*{margin:0;padding:0;}
		#box{
			width: 100px;
			height: 100px;
			background: red;
			position: absolute;
			left: 0;
			top: 0;
		}
	</style>
</head>
<body>
	<div id="box"></div>
</body>
</html>
<script>
	/*
		1、按下   
		2、移动
		3、抬起
	 */
	
	var oBox = document.getElementById("box");
	oBox.onmousedown = function (e) {
		var e = e||event;
		var disX = e.offsetX;
		var disY = e.offsetY;
		var iWidth = document.documentElement.clientWidth - this.offsetWidth;
		var iHeight = document.documentElement.clientHeight - this.offsetHeight;
		
		document.onmousemove = function(e){
		
			var l = e.clientX - disX;
			var t = e.clientY - disY;
			l = l>iWidth?iWidth:(l<0?0:l);
			t = t>iHeight?iHeight:(t<0?0:t);
		
			oBox.style.left = l + "px";
			oBox.style.top = t + "px";
		}
		document.onmouseup = function(){
			document.onmousemove = null;
		}
	}
	// oBox.onmousedown = function (e) {
	// 	var e = e||event;
	// 	var disX = e.clientX;
	// 	var disY = e.clientY;
		
	// 	oBox.onmousemove = function(e){
	// 		var l = e.clientX - disX;
	// 		var t = e.clientY - disY;
		
	// 		oBox.style.left = l + "px";
	// 		oBox.style.top = t + "px";
	// 	}
	// 	oBox.onmouseup = function(){
	// 		oBox.onmousemove = null;
	// 	}
	// }
	
</script>
