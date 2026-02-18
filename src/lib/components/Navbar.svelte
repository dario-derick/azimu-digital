<script>
	let isOpen = false;

	const toggleMenu = () => {
		isOpen = !isOpen;
	};


</script>

<header>
	<div class="logo">
		<i class="fa-solid fa-rocket"></i>
		<h4>Azimu Digital</h4>
	</div>
	<nav class:active={isOpen}>
		<ul>
			<li class="nav-item">
				<a href="..">Home</a>
			</li>
			<li class="nav-item">
				<a href="..">About Us <i class="fas fa-caret-down"></i></a>

				<div class="menu">
					<ul>
						<li>Our Mission</li>
						<li>Our Vision</li>
						<li>Our Motto</li>
					</ul>
				</div>
			</li>
			<li class="nav-item">
				<a href="..">Solutions</a>
			</li>
			<li class="nav-item">
				<a href="..">Blogs</a>
			</li>
		</ul>
		<button class="nav-btn">Contact Us</button>
	</nav>
	<!-- svelte-ignore a11y_consider_explicit_label -->
	<button class="hamburger"  on:click={toggleMenu}>
		<i class="fa-solid fa-bars"></i>
	</button>
</header>
<style>
	header {
		background-color: #1C2B39;
		padding: 0 4%;
		width: 100%;
		height: 70px; /* Define consistent height */
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-family: 'Trebuchet MS', Arial, sans-serif;
		position: fixed;
	}

	header .logo {
		color: white;
		font-size: 30px;
		display: flex;
		align-items: center;
	}
	header .logo i {
		color: rgb(255, 102, 0);
		margin-right: 4px auto;
		border-radius: 50px;
		padding: 11px;
		font-size: 30px;
	}
	nav {
		display: flex;
		align-items: center;
		margin-right: 40px;
		gap: 20px;
	}
	nav ul {
		display: flex;
		list-style-type: none;
	}
	nav .nav-item {
		padding: 10px 20px;
		position: relative;
	}
	nav .nav-item a {
		text-decoration: none;
		color: white;
		&:hover{
			color: #A66F1C;
			text-decoration: underline;
		}
	}

	.nav-item .menu {
		display: none;
		width: 150px;
		color: black;
		top: 100%;
		left: 0;
		position: absolute;
		padding: 10px 0;
		z-index: 999;
		border-radius: 5px;
		background-color: aliceblue;
	}
	.menu ul {
		display: block;
		padding: 0;
		margin: 0;
	}

	.menu ul li {
		padding: 10px 12px;
	}

	.nav-item:hover .menu {
		display: block;
	}

	header .nav-btn {
		padding: 10px 15px;
		border-radius: 10px;
		border: none;
		color: white;
		background: var(--btn-primary-bg);
		font-size: 16px;
		font-family:
			'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana,
			sans-serif;
		cursor: pointer;
	}

	header .hamburger {
		color: white;
		font-size: 28px;
		cursor: pointer;
		display: none;
	}

	@media (max-width: 768px) {
		nav {
			position: absolute;
			top: 70px;
			left: 0;
			width: 100%;
			background: rgb(10, 10, 30);
			display: none;
			flex-direction: column;
		}
		nav ul {
			flex-direction: column;
			gap: 20px;
		}
		header i {
			display: block;
		}
		nav.active {
			display: block;
		}
	}
</style>
