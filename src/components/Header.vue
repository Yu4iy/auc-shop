<template>
	<header class="header">
		<div class="header__container container">
			<a href="" class="header__logo"><img src="../assets/logo.png" alt=""></a>
			<div class="header__menu menu">
				<!-- BURGER -->
				<div class="menu__icon">
					<span></span>
					<span></span>
					<span></span>
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
				<a href="" class="actions-header__region"><img src="../assets/globe.png" alt=""> Choice Region</a>
				<div class="actions-header__user user-header">
					<div class="user-header__icon" @click="showHeaderModal = !showHeaderModal">
						<img src="../assets/Menu.png" alt="">
					</div>
					<transition name="fade" appear>
						<ul @mouseleave="showHeaderModal = false" v-show="showHeaderModal" class="user-header__menu ">
							<li> <a class="user-header__link-1" href="">Lorem ipsum1</a></li>
							<li> <a class="user-header__link-2" href="">Lorem dolor2</a></li>
							<li> <a class="user-header__link-3" href="">Lorem amet3</a></li>
							<li> <a class="user-header__link-4" href="">Lorem glory4</a></li>
						</ul>
					</transition>
				</div>
			</div>
		</div>
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
	}
}
}
</script>

<style lang="scss">
@import "@/styles/global.scss";
.header {
	background: #1c242a ;
	

		&__container {
			display: flex;
			align-items: center;
			position: relative;
			height: 75px ;


		}

		&__logo {
			
		}

		&__menu {
			
		}

		&__actions {
		}
}

.menu {
	// flex-grow flex-shrink flex-basis  
	flex:  1 1 auto;
	

		&__icon {

		}

		&__body {
			
		}

		&__list {
			display: flex;
			align-items: center;
			justify-content: center;
			li{
				margin: 15px ;
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
			top: 75px;
			right: 0;
			z-index: -2;
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
