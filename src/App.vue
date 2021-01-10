<template>
	<div id="app">
		<h1>Formulário Desafio</h1>
		<div class="conteudo">
			<form class="painel" v-if="!enviado">
				<div class="cabecalho">Formulário</div>
				<Rotulo />		
				<NomeCompleto v-model="nomeCompleto" />		
				<rotulo nome="email">
					<input type="text" v-model="email">
				</rotulo>
				<rotulo nome="senha">
					<input type="password" v-model="senha">
				</rotulo>
				<rotulo nome="armazenarDados">
					<input type="checkbox" v-model="armazenarDados">
				</rotulo>


				<button class="bnt" @click.prevent="enviar">Enviar</button>
				

			</form>
			<div class="painel" v-else>
				<div class="cabecalho">Resultado</div>
				<rotulo nome="nome">
				<span> {{ nomeCompleto.nome }}</span>
				</rotulo>
				<rotulo nome="sobrenome">
					<span> {{ nomeCompleto.sobrenome }}</span>
				</rotulo>
				<rotulo nome="email">
					<span> {{ email }}</span>
				</rotulo>
				<rotulo nome="senha">
					<span> {{ senha }}</span>
				</rotulo>
				<rotulo nome="armazenarDados">
					<span> {{ armazenarDados }}</span>
				</rotulo>

			</div>
		</div>
	</div>
</template>

<script>
import Rotulo from './components/Rotulo.vue'
import NomeCompleto from './components/NomeCompleto.vue'


export default {
	name: 'app',
	components: { Rotulo, NomeCompleto },
	data() {	
				return{				
					email: '',
					senha: '',
					armazenarDados: true,
					enviado: false,
					nomeCompleto:{
						nome: '',
						sobrenome: ''
					}
				}
	},
	methods: {
		enviar() {
			this.enviado = true
		}
	}
}
</script>

<style>

body {
	background-color: #ECECEC;
}

#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;

	display: flex;
	flex-direction: column;
}

.conteudo {
	display: flex;
}

.painel {
	flex: 1;
	background: #FFF;
	margin: 0px 10px;
	padding: 20px;
	border: 1px solid #AAA;
	border-radius: 5px;
}

.painel .cabecalho {
	width: 100%;
	background-color: #DDD;
	padding: 10px 0px;
	border-radius: 5px;
	font-size: 1.4rem;
}

#app form button {
	float: right;
	margin: 10px 0px;
	padding: 10px 20px;
	font-size: 1.4rem;
	border-radius: 5px;
	color: #FFF;
	background-color: #2196F3;
}

#app h1 {
	font-weight: 200;
	margin: 20px;
	padding: 0;
}

.mr-4 {
	margin-right: 40px;
}
</style>
