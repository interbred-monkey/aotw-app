<script>
	import 'bulma/css/bulma.css'
	import Form from './components/Form.svelte'
	export let name;

	let user = { submitForm: false };

	function submit() {
		user.submitForm = !user.submitForm;
	}
</script>

<main>
	{#if !user.submitForm}
		<section class="hero is-info">
			<div class="hero-body">
			<div class="container">
				<h1 class="title">
					Hello {name}!
				</h1>
				<h2 class="subtitle">
				Submit your Album of the week.
				</h2>
			</div>
			</div>
		</section>
		<Form />
	{/if}
	{#if user.submitForm}
		<section class="hero is-info">
			<div class="hero-body">
			<div class="container">
				<h1 class="title">
					Thank you {name}!
				</h1>
				<h2 class="subtitle">
				Keep on rocking.
				</h2>
			</div>
			</div>
		</section>
	{/if}
</main>

<style>
	main {
		text-align: center;
		/* padding: 1em; */
		margin: 0 auto;
	}

	h1 {
		color: #2980b9;
		text-transform: uppercase;
		font-size: 3em;
		font-weight: 100;
		font-family: sans-serif; 
	}

	.hero {
		margin-bottom: 20px;
	}
</style>