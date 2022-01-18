<template> 
	<section  class="hero">
		<div class="container">
			<div class="title">
				<div class="title__item">Only exclusive</div>
				<div class="title__main title__main-w">Lots under auction and free sale</div>
				<div class="title__text">We collect the exclusive audience and exhausted lots, give a convenient and automated service for buying and selling, as well as setting lots to auction, provide personal offices, and also provide accompanying services with rare and expensive things.</div>
				<a class="hero-button btn" href=""><span>Join</span></a>
			</div>

		</div>
	</section>
</template>

<script>


export default {
name: 'Header',
components: {	  
},
data(){
	return{

	}
},
computed:{
	
},
}
</script>

<style lang="scss">
@import "@/styles/global.scss";

.hero{
	background-image: url('../assets/bg-head.jpg');
	background-size: cover;
	background-position: center;
	

	.hero-button {
		display: inline-block;
		margin-top: 50px;
		color: #fff;
		text-decoration: none;
		font-size: 20px;
		padding: 10px 50px ;
		background: linear-gradient(180deg, rgba(185, 164, 126, 0.164) 37%, rgba(165, 138, 92, 0) 66%, rgba(208, 175, 117, 0) 100%);
		border-style: solid;
		border-width: 5px;
		border-image: linear-gradient(#c5a978, #8e652f) 1;
		text-transform: uppercase;
		transition: all 0.3s ease 0s;		
		
		@media(min-width: 992px){
			&:hover{
				background: #c5a97833;
			}
		}
	}
	.btn {
	}

}
</style>
