<template>
	<div class="intro">
		<div class="introHeader">
			<section id="home" class="tt-fullHeight" >
					<h1 class="title is-1">NEX</h1>
				<div class="description">
					<h1>The News <span>Express</span></h1>
					<p class="subtitle">All news available in single plateform<br> you just need to choose your news of source</p>
				</div>

				<div class="mouse-icon">
					<div class="wheel"></div>
				</div>
			</section>
		</div>
	</div>
</template>
<script type="text/javascript">
	export default{
		name:'intro'
	}
</script>
<style scoped>
	#home {
	background: url('../assets/news1.jpg') no-repeat center center;
	background-attachment: fixed;
	background-size: cover;
	position: relative;
	padding: 150px;
}
#home:before {
	content: "";
	background-color: rgba(30, 35, 40, 0.5);
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}

#home > h1{
	font-weight: bold;
	font-size: 80px;
	text-align: center;
}
.description {
	width: 100%;
	top: 50%;
	left: 0;
	text-align: center;
}

.description h1{
	font-size: 60px;
	line-height: 80px;
	font-weight:  bold;
	margin-bottom: 16px;
	color: #52b3d9;
}
.description h1 span{
	color: #68c3a3;
}
.description p{
	color: #fff;
	margin-bottom: 40px;
}

.mouse-icon {
	position: relative;
	left: 50%;
	top:110px;
	bottom: 40px;
	border: 2px solid #fff;
	border-radius: 16px;
	height: 50px;
	width: 30px;
	margin-left: -17px;
	display: block;
	z-index: 10;
}

.mouse-icon .wheel {
    -webkit-animation-name: drop;
    -webkit-animation-duration: 1s;
    -webkit-animation-timing-function: linear;
    -webkit-animation-delay: 0s;
    -webkit-animation-iteration-count: infinite;
    -webkit-animation-play-state: running;
    animation-name: drop;
    animation-duration: 1s;
    animation-timing-function: linear;
    animation-delay: 0s;
    animation-iteration-count: infinite;
    animation-play-state: running;
}

.mouse-icon .wheel {
	position: relative;
	border-radius: 10px;
	background: #fff;
	width: 4px;
	height: 10px;
	top: 4px;
	margin-left: auto;
	margin-right: auto;
}

@-webkit-keyframes drop {
    0%   { top:5px;  opacity: 0;}
    30%  { top:10px; opacity: 1;}
    100% { top:25px; opacity: 0;}
}


@keyframes drop	{
	0%   { top:5px;  opacity: 0;}
	30%  { top:10px; opacity: 1;}
	100% { top:25px; opacity: 0;}
}
</style>