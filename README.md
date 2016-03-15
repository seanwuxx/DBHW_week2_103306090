# DBHW_week2_103306090
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Countdown Timer</title>
<link rel="stylesheet" href="css/bootstrap.min.css">
<link rel="shortcut icon" href="images/titleimage.png">
<style>
body {
	background-color: black;
}
.container{
	position:relative;
	margin-top: 100px;
	margin-left: 133px;
}
	
.whirl,
.whirl::before,
.whirl::after {
	position: absolute;
	top: 50%;
	left: 50%;
	border: 4px solid rgb(204,204,204);
	border-left-color: rgb(0,0,0);
	border-radius: 3996px;
		-o-border-radius: 3996px;
		-ms-border-radius: 3996px;
		-webkit-border-radius: 3996px;
		-moz-border-radius: 3996px;
}
.whirl {
	margin: -100px 0 0 -100px;
	height: 200px;
	width: 200px;
	animation: cssload-rotate 1900ms linear infinite;
		-o-animation: cssload-rotate 1900ms linear infinite;
		-ms-animation: cssload-rotate 1900ms linear infinite;
		-webkit-animation: cssload-rotate 1900ms linear infinite;
		-moz-animation: cssload-rotate 1900ms linear infinite;
}
.whirl::before {
	content: "";
	margin: -92px 0 0 -92px;
	height: 176px;
	width: 176px;
	animation: cssload-rotate 1900ms linear infinite;
		-o-animation: cssload-rotate 1900ms linear infinite;
		-ms-animation: cssload-rotate 1900ms linear infinite;
		-webkit-animation: cssload-rotate 1900ms linear infinite;
		-moz-animation: cssload-rotate 1900ms linear infinite;
}
.whirl::after {
	content: "";
	margin: -116px 0 0 -116px;
	height: 224px;
	width: 224px;
	animation: cssload-rotate 3800ms linear infinite;
		-o-animation: cssload-rotate 3800ms linear infinite;
		-ms-animation: cssload-rotate 3800ms linear infinite;
		-webkit-animation: cssload-rotate 3800ms linear infinite;
		-moz-animation: cssload-rotate 3800ms linear infinite;
}
@keyframes cssload-rotate {
	100% {
		transform: rotate(360deg);
	}
}
@-o-keyframes cssload-rotate {
	100% {
		-o-transform: rotate(360deg);
	}
}
@-ms-keyframes cssload-rotate {
	100% {
		-ms-transform: rotate(360deg);
	}
}
@-webkit-keyframes cssload-rotate {
	100% {
		-webkit-transform: rotate(360deg);
	}
}
@-moz-keyframes cssload-rotate {
	100% {
		-moz-transform: rotate(360deg);
	}
}
</style>
<script src="js/bootstrap.min.js"></script>
<script>
var ST;
function start() {
	var inputnum = document.getElementById("num").value;
	document.getElementById("shownum").innerHTML= inputnum;
	clearTimeout(ST);
	minus();
}
function minus() {
	var inputnum = document.getElementById("num").value;
	var curr = parseInt(document.getElementById("shownum").innerHTML);
	if (curr && curr <= inputnum) {
		if(curr <= 10) {
			document.getElementById("shownum").innerHTML = "0" + (curr - 1);
		} else {
			document.getElementById("shownum").innerHTML = curr - 1;
		}
	} else {
		document.getElementById("shownum").innerHTML = inputnum;
	}
	ST = setTimeout(function() { minus(); }, 1000);
}
</script>
</head>
<body>
	<div class="container">
		<h1 id="shownum" style="color:white; margin-left:535px; margin-top:10px; font-size:70px;">60</h1>
		<div class="whirl"></div>
	</div>
	<h1 style="margin-left:575px; margin-top:70px">Countdown Timer</h1>
     <input id="num" type="text" class="form-control" placeholder="Please input a number">
     <button class="btn btn-default" type="button" style="margin-left:695px; margin-top:10px;" onclick="start()">Start</button>
</body>
</html>
