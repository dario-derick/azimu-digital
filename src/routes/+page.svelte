<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';
	import { onMount } from 'svelte';

	// Set your launch date here
	const launchDate = new Date('2026-04-01T00:00:00');

	type TimeLeft = {
		days: number;
		hours: number;
		minutes: number;
		seconds: number;
	};

	let timeLeft: TimeLeft | null = null;
	let interval: ReturnType<typeof setInterval> | undefined;
	let email = '';

	function calculateTimeLeft() {
		const difference = Number(launchDate) - Date.now();

		if (difference <= 0) {
			timeLeft = null;
			if (interval !== undefined) {
				clearInterval(interval);
				interval = undefined;
			}
			return;
		}

		timeLeft = {
			days: Math.floor(difference / (1000 * 60 * 60 * 24)),
			hours: Math.floor((difference / (1000 * 60 * 60)) % 24),
			minutes: Math.floor((difference / (1000 * 60)) % 60),
			seconds: Math.floor((difference / 1000) % 60)
		};
	}

	async function handleSubmit() {
		if (email) {
			console.log('Email submitted:', email);
			// TODO: Add your email submission logic here
			// Example: await fetch('/api/notify', { method: 'POST', body: JSON.stringify({ email }) });
			alert(`Thanks! We'll notify you at ${email}`);
			email = '';
		}
	}

	onMount(() => {
		calculateTimeLeft();
		interval = setInterval(calculateTimeLeft, 1000);

		return () => {
			if (interval !== undefined) {
				clearInterval(interval);
			}
		};
	});
</script>

<Navbar />

<section class="container">
	<div class="content">
		<h1>Coming Soon</h1>
		<p>We're building something impactful at <strong>Azimu Digital</strong>.</p>

		{#if timeLeft}
			<div class="countdown">
				<div><span>{timeLeft.days}</span><small>Days</small></div>
				<div><span>{timeLeft.hours}</span><small>Hours</small></div>
				<div><span>{timeLeft.minutes}</span><small>Minutes</small></div>
				<div><span>{timeLeft.seconds}</span><small>Seconds</small></div>
			</div>
		{:else}
			<p class="launched">We are live!</p>
		{/if}

		<form class="notify-form" on:submit|preventDefault={handleSubmit}>
			<input type="email" placeholder="Enter your email" bind:value={email} required />
			<button type="submit">Notify Me</button>
		</form>
	</div>
</section>

<style>
	.container {
		min-height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		background: linear-gradient(135deg, #0a0a1e, #14143a);
		color: white;
		text-align: center;
		padding: 2rem;
	}

	.content {
		max-width: 600px;
	}

	h1 {
		font-size: 3rem;
		margin-bottom: 1rem;
	}

	p {
		font-size: 1.1rem;
		margin-bottom: 2rem;
		color: #ccc;
	}

	.countdown {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 1rem;
		margin-bottom: 2rem;
	}

	.countdown div {
		background: rgba(255, 255, 255, 0.08);
		padding: 1rem;
		border-radius: 8px;
	}

	.countdown span {
		display: block;
		font-size: 1.8rem;
		font-weight: bold;
	}

	small {
		color: #aaa;
	}

	.notify-form {
		display: flex;
		gap: 0.5rem;
		justify-content: center;
	}

	input {
		padding: 0.6rem;
		border-radius: 5px;
		border: none;
		outline: none;
		min-width: 250px;
	}

	button {
		padding: 0.6rem 1rem;
		border-radius: 5px;
		border: none;
		cursor: pointer;
		background: #ff6600;
		color: white;
		font-weight: 600;
	}

	button:hover {
		background: #e65c00;
	}

	.launched {
		color: #4caf50;
		font-weight: bold;
	}

	@media (max-width: 600px) {
		.notify-form {
			flex-direction: column;
		}

		input {
			width: 100%;
		}

		.countdown {
			grid-template-columns: repeat(2, 1fr);
		}

		h1 {
			font-size: 2rem;
		}
	}
</style>