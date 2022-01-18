<template>
	<header class="header">
		<div class="header__container container">
			<a href="" class="header__logo"><img src="../assets/logo.png" alt=""></a>
			<div class="header__menu menu">
				<!-- BURGER -->
				<div  class="menu__icon" @click="burger = !burger">
					<div class="menu-burger-inner">
						<span :class="{ 'burger__top-open': burger, 'burger__top-close':!burger}"></span>
						<span :class="{ 'burger__midle-open': burger, 'burger__midle-close':!burger }"></span>
						<span :class="{ 'burger__bottom-open': burger, 'burger__bottom-close':!burger }"></span>
					</div>
				</div>


				<nav class="menu__body">
					<ul class="menu__list">
						<li><a class="menu__link" href="">Home</a></li>
						<li><a class="menu__link" href="">Auction</a></li>
						<li><a class="menu__link" href="">About Project</a></li>
						<li><a class="menu__link" href="">Partners</a></li>
						<li><a class="menu__link" href="">Contacts</a></li>
					</ul>
				</nav>

			</div>
			<div class="header__actions actions-header">
				<a href="" class="actions-header__region"><img src="../assets/globe.png" alt=""><span>Choice Region</span></a>
				<div class="actions-header__user user-header">
					<div class="user-header__icon" @click="showHeaderModal = !showHeaderModal">
						<img src="../assets/Menu.png" alt="">
					</div>
					<transition name="fade" appear>
						<ul  v-show="showHeaderModal" class="user-header__menu ">
							<li> <a class="user-header__link-1" href="">Lorem ipsum1</a></li>
							<li> <a class="user-header__link-2" href="">Lorem dolor2</a></li>
							<li> <a class="user-header__link-3" href="">Lorem amet3</a></li>
							<li> <a class="user-header__link-4" href="">Lorem glory4</a></li>
						</ul>
					</transition>
				</div>
			</div>
		</div>
		<transition name="fade" appear>
			<nav class="menu-mobile" v-show = burger >
				<ul class="menu-mobile__list">
					<li><a class="menu-mobile__link" href="">Home</a></li>
					<li><a class="menu-mobile__link" href="">Auction</a></li>
					<li><a class="menu-mobile__link" href="">About Project</a></li>
					<li><a class="menu-mobile__link" href="">Partners</a></li>
					<li><a class="menu-mobile__link" href="">Contacts</a></li>
					<li> <a href="" class="menu-mobile__link"><img src="../assets/globe.png" alt=""><span> Choice Region</span></a></li>

				</ul>
			</nav>
		</transition>

	</header>
</template>

<script>


export default {
name: 'Header',
components: {	  
},
data(){
	return{
		showHeaderModal:false,
		burger:false 
	}
},
computed:{
	
},
}
</script>

<style lang="scss">
@import "@/styles/global.scss";
.header {
	background: #1c242a ;
	position: relative;
	z-index: 2000;

		&__container {
			display: flex;
			align-items: center;
			position: relative;
			height: 75px ;


		}

		&__logo {
	
			@media( max-width: 770px){
			position: absolute;
			left: 50%;
			top: 50%;
			transform: translate(-50%, -50%);
				
			}
		}

		&__menu {

			}

		&__actions {
		
		}
}
.menu-mobile{
	position: fixed;
	background: #1c242ad2;
	top: 75px;
	width: 100vw;
	display: flex;
	justify-content: center;
	font-size: 25px;
	text-align: center;
	padding: 40px 0 ;
	overflow: scroll;
	li{
		margin: 0 0 30px  0 ;

	}

	.menu-mobile__link{
		color: #fff;
		text-decoration: none;
		font-weight: 700;

}

}

.menu {
	// flex-grow flex-shrink flex-basis  
	flex:  1 1 auto;
	

		&__icon {
			display: none;
			color: #fff;
			position: absolute;
			left:  10px;
			top: 50%;
			transform: translateY(-50%);
			.menu-burger-inner{
				cursor: pointer;
				width: 45px;
				height: 45px;
				position: relative;

			}
			span{
				background: #a58a5c;
				width: 30px;
				height: 3px;
				display: block;
				position: absolute;
				top: 50%;
				left: 50%;
				border-radius: 2px;
				transform: translate(-50%,-50%);
				&:first-child{
					top: 14px;
				}
				&:last-child{
					top: 30px;

				}
			}
				.burger__top-open{
					animation: burger_top 0.4s forwards;
				}
				.burger__top-close{
					animation: burger_top-close 0.4s forwards;
					
				}

				.burger__midle-open{
					animation: burger_midle 0.4s forwards;
				}
				
				.burger__midle-close{
					animation: burger_midle-close 0.2s forwards;
				}

				.burger__bottom-open{
					animation: burger_bottom 0.4s forwards;
				}
				.burger__bottom-close{
					animation: burger_bottom-close 0.4s forwards;
					
				}
			@keyframes burger_top {
			0%   {background-color: #d7c5a2;}

			100% {
				transform: rotate(45deg);
				transform-origin: left;
				left: 10px;
				top: 10px;

				}
			}

			@keyframes burger_top-close {
			0%   {
				transform: rotate(45deg);
				transform-origin: left;
				left: 10px;
				top: 10px;}

			100% {
				transform: rotate(0deg);
				transform-origin: left;
				left: 7px;
				top: 12px;

				}
			}

			@keyframes burger_bottom-close {
			0%   {
				transform: rotate(-45deg);
				transform-origin: left;
				left: 10px;
				top: 31px;}

			100% {
				transform: rotate(0deg);
				transform-origin: left;
				left: 7px;
				top: 30px;

				}
			}

			@keyframes burger_midle {
			0%   {opacity: 100;}
			100% {opacity: 0;}
			}
			@keyframes burger_midle-close {
			0%   {
				opacity: 0;
				}

			100% {
				opacity: 100;

				}
			}
			
			@keyframes burger_bottom {
			0%   {background-color: #d7c5a2;}

			100% {
				transform: rotate(-45deg);
				left: 10px;
				top: 31px;

				transform-origin: left;

				}
			}

			@media( max-width: 770px){
				display: inline-block;
				
			}

		}

		&__body {
			
		}

		&__list {
			display: flex;
			align-items: center;
			justify-content: center;
			li{
				margin: 0 15px ;
				@media( max-width: 840px){
					margin: 0 10px ;
					font-size: 14px;
					
				}
			}
			@media( max-width: 770px){
			display: none;
				
			}

		}

		&__link {
			text-transform: uppercase;
			letter-spacing: 1.4;
			color: #fff;
			text-decoration: none;
			@media( min-width: 992px){
				&:hover{
					text-decoration: underline 1px #fff;
				}
			} 

		}
}
.actions-header {
		display: flex;
		align-items: center;

		&__region {
			text-transform: uppercase;
			letter-spacing: 1.4;
			text-decoration: none;
			color: #fff;
			display: flex;
			align-items: center;
			img{
				margin: 0 10px 0 0;
			}
			@media (max-width: 980px) {
				span{
					display: none;
				}
			}
			@media( max-width: 700px){
			display: none;
			}
		
		}

		&__user {
		}
}
.user-header {

		&__icon {
			display: flex;
			align-items: center;
			margin: 0 0 0 15px;
			cursor: pointer;
		}

		&__menu {
			position: absolute;
			top: 78px;
			right: 0;
			background: #1c242a;
			padding: 20px;

			li{
				list-style: none;
				margin: 0 0 10px 0 ;
				&:last-child{
					margin: 0;
				}
				
				a{
					color: #fff;
					text-decoration: none;
				}
				@media( min-width: 992px){
				&:hover{
					text-decoration: underline 1px #fff;
				}
				}
			}
			

		}

		&__link-1 {
			background: url('../assets/globe.png') left center no-repeat;
			padding: 0 0 0 25px;
		}

		&__link-2 {
			background: url('../assets/key.png') left center no-repeat;
			padding: 0 0 0 25px;

		}

		&__link-3 {
			background: url('../assets/palm.png') 4px center no-repeat;
			padding: 0 0 0 25px;

		}

		&__link-4 {
			background: url('../assets/hammer.png') left center no-repeat;
			padding: 0 0 0 25px;

		}

}
.fade-enter-active,
.fade-leave-active{
	transition: all 0.4s ease-out;
}
.fade-enter,
.fade-leave-to{
	top: 0;
	opacity: 0;
}

</style>
