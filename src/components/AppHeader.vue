<template>
    <header class="page-header">
			<nav class="container">
				<div class="row">
					<ul class="flex">
						<li v-for="(link,i) in menu" :key="i">{{ link.text }}</li>
					</ul>

					<a class="logo" href="#">
						<img src="/boolean-logo.png" alt="" />
					</a>

					<ul class="flex">
						<li>&hearts;</li>
						<li>&hearts;</li>
						<li>{{ ciao }}</li>
					</ul>
				</div>
			</nav>
		</header>
</template>

<script>

export default{
	data(){
		return {
			menu: [
				{
					text:'Donna',
					href: '#',
				},
				{
					text:'Uomo',
					href: '#',
				},
				{
					text:'Bambini',
					href: '#',
				},
				
			]
		}
	},
	props: ['ciao'],

}

</script>

<style lang="scss">
.page-header {
	background-color: #fe6900;
	color: white;
	padding: 16px 0;
	box-shadow: 0px 0px 20px 2px rgba(0, 0, 0.1);
}

.logo img {
	height: 32px;
}

.page-header .row {
	justify-content: space-between;
}

.page-header .row {
	align-items: center;
}

.page-header .row ul {
	gap: 20px;
}
</style>