<template>
	<main>
		<section class="login-container">
			<div class="container login">
				<Transition mode="out-in" name="fade-in">
					<p v-if="!input_name">Comece agora sua jornada no mundo <strong>dev</strong>, faça agora seu login e aproveite nosso curso <strong>gratuito!</strong></p>
					<p v-else>Muito bem <strong>{{ input_name }}</strong> agora é só partir para sua viagem pelo aprendizado!</p>
				</Transition>
				<div class="card">
					<img src="./assets/rockt_icon.svg" alt="Imagem de foguete">
					<div class="box-inputs">
						<input type="text" v-model="input_name" placeholder="username">
						<input type="password" placeholder="senha">
						<a href="https://byteseridojr.netlify.app">Esqueceu sua senha?</a>
					</div>
					<div class="box-buttons" @click="teste()">
						<button >
							Partir
						</button>
					</div>
					<div class="sign">
						Cadastre-se
					</div>
				</div>
			</div>
		</section>
	</main>
</template>

<script>
	export default{
		data(){
			return{
				input_name: ""
			}
		},

		methods: {
			submitForm(e){
				e.preventDefault();

			},

			teste(){
				alert(`Olá, ${this.input_name}, você fez login`)
			}
		}
	}

</script>

<style scoped>
	body{
		height: 100%;
	}

	main{
		height: 100%;
	}
	
	#app{
		min-height: 100%;
	}

	.login-container{
		height: 100%;
		background-image: url(./assets/image_background.svg);
		background-size: cover;
		font-family: 'Rubik', sans-serif;
	}

	.login{
		padding: 180px 79px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	strong{
        color: #C8A585;
    }

	p{
        color: white;
        max-width: 682px;
        font-weight: 700;
        font-size: 3.125rem;
        line-height: 59.25px;
    }

	.card{
		font-family: 'Exo', sans-serif;
		display: flex;
		flex-direction: column;
		padding: 54px 40px;
		background-color: #1F2635;
		border-radius: 10px;
		align-items: center;
		gap: 30px;
	}

	.box-inputs{
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 11px;
	}
	
	input{
		border: none;
		background-color: #2D3545;
		border-radius: 4px;
		min-width: 273px;
		padding: 15px 16px;
		color: #C8A585;
		font-weight: 600;
		font-size: 0.75rem;
	}

	input:focus{
		border:  2px solid #C8A585;
		outline: none;
	}

	a{
		font-weight: 600;
        font-size: 0.688rem;
        color:#C8A585;
		padding-top: 11px;
	}

	.box-buttons{
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.box-buttons button{
		border: none;
		border-radius: 4px;
		background-color: #2D3545;
		color: #C8A585;
		font-family: 'Exo', sans-serif;
		min-width: 176px;
		padding: 13px 69px;
		font-weight: 700;
		font-size: 0.875rem;
		cursor: pointer;
	}

	.sign{
		color: #C8A585;
		font-weight: 700;
		font-size: 0.75rem;
		cursor: pointer;
		align-self: flex-end;
	}

	.fade-in-enter-active {
		transition: opacity 350ms ;
	}

	.fade-in-leave-active {
		transition: opacity 350ms ;
	}

	.fade-in-enter,
	.fade-in-leave-to {
		opacity: 0;
	}
</style>
