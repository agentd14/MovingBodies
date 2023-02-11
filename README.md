# MovingBodies
<!DOCTYPE html>
<html>
<head>
	<title>Moving Bodies</title>
	<meta charset="utf-8">
	<link rel="preconnect" href="https://fonts.gstatic.com">
	<link href="https://fonts.googleapis.com/css2?family=Raleway:wght@900&display=swap" rel="stylesheet">
	<style type="text/css">
		*{
			margin: 0;
			padding: 0;
		}
		body{
			min-height: 100vh;
			background: #ccc;
			display: flex;
			justify-content: center;
			align-content: center;
		}
		/*.outer{
			overflow: hidden;
			position: relative;
		}*/
		.container{
		    position: relative;
		    width: 1366px;
		    height: auto;
		    /*background: #fff;*/
		    display: flex;
		    justify-content: center;
		    align-items: center;

		}
		#mainWrapper{
			position: absolute;
			width: 1366px;
			height: 768px;
			overflow: hidden;
			background-image: url("images/stageone.png");
			background-repeat: no-repeat;
			-webkit-filter: brightness(1);
			filter: brightness(1);
			transition: all 300ms;
		}
		#video{
			overflow: hidden;
			position: fixed;
			width: 1366px;
			height: 768px;
			overflow: hidden;
			left: 157px;
			top: 32px;
		}
		#message{
			z-index: 13;
			position: relative;
			width: max-content;
			top: -7px;
		    left: -371px;
		    font-size: 3.2em;
			font-family: 'Raleway', sans-serif;
			text-align: center;
			transform: rotate(-4deg) skewY(3deg);
			line-height: 60px;
		}
		#button{
			z-index: 14;
			position: relative;
		    width: 149px;
		    height: 414px;
		    top: 85px;
		    left: -70px;
		    z-index: 5;
		    background-image: url("images/standing.png");
		    /*background-size: 333px;*/
			background-repeat: no-repeat;
			transition: all 400ms;
			transform: translate(0px,0px);
			-webkit-filter: hue-rotate(0deg);
			filter: hue-rotate(0deg);
			transition-delay: 300ms;
		}
    	#light{
    		z-index: 12;
			position: fixed;
			width: 721px;
			height: 896px;
			top: 481px;
		    left: 795px;
		    margin: 0 auto;
		    -webkit-filter:blur(5px);
	        filter: blur(5px);
		    background-image: url("images/newlight.png");
		    background-size: 5%;
		    background-repeat: no-repeat;
		    transform: scale(1); 
		    /*transition: all 300ms;*/
		    transition-delay: 100ms;
    	}
    	.ani{
    		filter: hue-rotate();
    		animation: animate 5s infinite;
    	}
    	@keyframes animate{
		  0% {
		    filter: hue-rotate(10deg) saturate(2);
		  }
		  10% {
		    filter: hue-rotate(35deg) saturate(2);
		  }
		  20% {
		    filter: hue-rotate(58deg) saturate(2);
		  }
		  30% {
		    filter: hue-rotate(75deg) saturate(2);
		  }
		  40% {
		    filter: hue-rotate(80deg) saturate(2);
		  }
		  50% {
		    filter: hue-rotate(90deg) saturate(2);
		  }
		  60% {
		    filter: hue-rotate(100deg) saturate(2);
		  }
		  70% {
		    filter: hue-rotate(120deg) saturate(2);
		  }
		  80% {
		    filter: hue-rotate(180deg) saturate(2);
		  }
		  100% {
		    filter: hue-rotate(360deg) saturate(2);
		  }
		}
		
	</style>
</head>
<body>
	<!-- <div class="outer"> -->
	<!-- <div class="inner"id="mainWrapper"> -->
		<div class="container">
		<video  id="video">
		<source src="dancingmanoffice.mp4" type="video/mp4">
	</video>
	<div id="light"> </div>
		<div id="message">Step Out<br> of the <br>Monotony</div>
		<div id="button"></div>
		<div id="sticky"></div>
		
		<!-- <div id="mainWrapper_2"></div> -->
		<div id="mainWrapper"></div>
		<div class="ani"></div>
		<audio id="audio">
			<source src="dancingmusic.mp3" type="audio/mp3">
		</audio>
		
		</div>
	
<!-- </div> -->
	

	<script type="text/javascript">
		
		let state = "on";
		var count = 0;
		var myMsg = document.getElementById('message');
		var myBody = document.body;
		var myWrap = document.getElementById('mainWrapper');
		var myButton = document.getElementById('button');
		var myLight = document.getElementById('light');
		var mySticky = document.getElementById('sticky');
		var myColors3 =['hue-rotate(75deg)', 'hue-rotate(33deg)', 'hue-rotate(150deg)', 'hue-rotate(12deg)', 'hue-rotate(30deg)', 'hue-rotate(90deg)', 'hue-rotate(45deg)', 'hue-rotate(200deg)'];
		let videoElm = document.getElementById("video");
		let audioElm = document.getElementById("audio");
		
	
	myButton.onclick = function myFunction(){


	videoElm.play();
	audioElm.play();


		count = count + 1;
		console.log(count);

		if(count > 7){
		// console.log("true");
			count = 0;

			// playButton.addEventListener("click", handlePlayButton. false);
			// playVideo();
			
	}
		
		
		if(state=='on'){
			
			// console.log("true = "+state);
			// document.getElementById('mainWrapper').style.backgroundImage = "url('images/stage2.png')"; 
			document.getElementById('button').style.backgroundImage = "url('images/danceguy.png')";

			myWrap.style.opacity = "0";
			myWrap.style.transition = "opacity 800ms ease-in";

			myLight.classList.remove("ani");
			void myLight.offsetWidth;
			myLight.classList.add("ani");

			myMsg.classList.remove("ani");
			void myMsg.offsetWidth;
			myMsg.classList.add("ani");

			
			document.body.style.backgroundColor = "black";
			myBody.style.transition = "background-color 800ms linear";
			myMsg.innerHTML = "Step In <br> to the <br> <font style='color:red;'>   MUSIC</font>";
			myMsg.style.color = "white";
			myMsg.style.transform = "translate(0px, 0px) rotate(-3deg) skewY(2deg)";
			myLight.style.transform = "translate(-250px, -450px)";
			myLight.style.backgroundSize = "83%";
			
			state = "off";

		} else {
			// console.log("true = "+state); 
			document.body.style.backgroundColor = "black";
			
			myLight.style.filter = "saturate(2)";
			state = "on";
		}
// 		function playVideo(){
// 			console.log("play video");
// 	 	videoElm.play();
		
// 		}
// 		function handlePlayButton(){
// 		if(videoElm.paused){
// 			playVideo();
// 		}else{
// 			videoElm.pause();
// 			playButton.classlist.remove("playing");
// 		}

// }
		
		myMsg.style.filter = myColors3[count];

	}

		
	
	</script>


	

</body>
</html>
