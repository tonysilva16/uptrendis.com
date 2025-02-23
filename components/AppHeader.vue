<script setup lang="ts">
const setupNavbar = () => {
	const hamburger = document.querySelector('#hamburger')
	const navbar = document.querySelector('#navbar')

	if (!navbar || !hamburger) {
		return
	}

	const links = navbar.querySelectorAll('a')

	hamburger.addEventListener('click', () => {
		navbar.classList.toggle('navbar-active')
	})

	links.forEach((link) => {
		link.addEventListener('click', () => {
			navbar.classList.toggle('navbar-active')
		})
	})
}

onMounted(() => {
	setupNavbar()
})
</script>
<template>
	<header>
		<nav
			id="navbar"
			class="fixed inset-x-0 z-20 w-full border-b border-gray-100 bg-white/80 backdrop-blur dark:border-gray-700/30 dark:bg-gray-900/80"
		>
			<div class="mx-auto px-4 sm:px-12 xl:max-w-6xl xl:px-0">
				<div
					class="relative flex flex-wrap items-center justify-between gap-6 lg:gap-0 lg:py-4"
				>
					<div class="relative z-20 flex w-full justify-between md:px-0 lg:w-max">
						<a
							href="./../#home"
							aria-label="ampire logo"
							class="nav-link flex items-center space-x-2 text-white"
						>
							Logo
						</a>

						<button
							aria-label="humburger"
							id="hamburger"
							class="relative -mr-6 p-6 lg:hidden"
						>
							<div
								aria-hidden="true"
								id="line"
								class="m-auto h-0.5 w-5 rounded bg-sky-900 transition duration-300 dark:bg-gray-300"
							></div>
							<div
								aria-hidden="true"
								id="line2"
								class="m-auto mt-2 h-0.5 w-5 rounded bg-sky-900 transition duration-300 dark:bg-gray-300"
							></div>
						</button>
					</div>
					<div
						aria-hidden="true"
						id="layer"
						class="fixed inset-0 z-10 h-screen w-screen origin-bottom scale-y-0 bg-white/70 backdrop-blur-2xl transition duration-500 dark:bg-gray-900/70 lg:hidden"
					></div>
					<div
						id="navlinks"
						class="invisible absolute left-0 top-full z-20 w-full origin-top-right translate-y-1 scale-90 flex-col flex-wrap justify-end gap-6 rounded-3xl border border-gray-100 bg-white p-8 opacity-0 shadow-2xl shadow-gray-600/10 transition-all duration-300 dark:border-gray-700 dark:bg-gray-800 dark:shadow-none lg:visible lg:relative lg:flex lg:w-auto lg:translate-y-0 lg:scale-100 lg:flex-row lg:items-center lg:gap-0 lg:border-none lg:bg-transparent lg:p-0 lg:opacity-100 lg:shadow-none dark:lg:bg-transparent"
					>
						<div v-if="false" class="text-gray-600 dark:text-gray-300 lg:pr-4">
							<ul
								class="space-y-6 text-base font-medium tracking-wide lg:flex lg:space-y-0 lg:text-sm"
							>
								<li>
									<a
										href="./../#solutions"
										class="nav-link block transition hover:text-primary dark:hover:text-primaryLight md:px-4"
									>
										<span>Solutions</span>
									</a>
								</li>
								<li>
									<a
										href="./../#company"
										class="nav-link block transition hover:text-primary dark:hover:text-primaryLight md:px-4"
									>
										<span>Company</span>
									</a>
								</li>
								<li>
									<a
										href="./../#features"
										class="nav-link block transition hover:text-primary dark:hover:text-primaryLight md:px-4"
									>
										<span>Features</span>
									</a>
								</li>
								<li>
									<a
										href="./../#testimonials"
										class="nav-link block transition hover:text-primary dark:hover:text-primaryLight md:px-4"
									>
										<span>Testimonials</span>
									</a>
								</li>
								<li>
									<a
										href="./../#pricing"
										class="nav-link block transition hover:text-primary dark:hover:text-primaryLight md:px-4"
									>
										<span>Pricing</span>
									</a>
								</li>
							</ul>
						</div>

						<div
							class="-ml-1 mt-12 flex w-full flex-col space-y-2 !border-0 border-primary/10 dark:border-gray-700 sm:flex-row md:w-max lg:mr-6 lg:mt-0 lg:space-y-0 lg:border-l lg:pl-6"
						>
							<a
								href="./contact.html"
								class="relative ml-auto flex h-9 w-full items-center justify-center before:absolute before:inset-0 before:rounded-full before:bg-primary before:transition-transform before:duration-300 hover:before:scale-105 active:duration-75 active:before:scale-95 dark:before:border-gray-700 dark:before:bg-primaryLight sm:px-4 lg:before:border lg:before:border-gray-200 lg:before:bg-gray-100 lg:dark:before:bg-gray-800"
							>
								<span
									class="relative text-sm font-semibold text-white dark:text-gray-900 lg:text-primary lg:dark:text-white"
									>Contact us</span
								>
							</a>
						</div>
						<button
							aria-label="switch theme"
							class="switcher group relative hidden h-9 w-9 rounded-full before:absolute before:inset-0 before:rounded-full before:border before:border-gray-200 before:bg-gray-50 before:bg-gradient-to-b before:transition-transform before:duration-300 hover:before:scale-105 active:duration-75 active:before:scale-95 dark:before:border-gray-700 dark:before:bg-gray-800 lg:flex"
						>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="transistion relative m-auto hidden h-5 w-5 fill-gray-500 duration-300 group-hover:rotate-180 group-hover:fill-yellow-400 dark:block dark:fill-gray-300"
								viewBox="0 0 20 20"
								fill="currentColor"
							>
								<path
									fill-rule="evenodd"
									d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z"
									clip-rule="evenodd"
								></path>
							</svg>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="transistion relative m-auto h-5 w-5 fill-gray-500 duration-300 group-hover:-rotate-90 group-hover:fill-blue-900 dark:hidden"
								viewBox="0 0 20 20"
								fill="currentColor"
							>
								<path
									d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"
								></path>
							</svg>
						</button>
					</div>
					<div class="fixed right-14 top-3 z-20 sm:right-24 lg:hidden">
						<button
							aria-label="switche theme"
							class="switcher group relative flex h-9 w-9 rounded-full before:absolute before:inset-0 before:rounded-full before:border before:border-gray-200 before:bg-gray-50 before:bg-gradient-to-b before:transition-transform before:duration-300 hover:before:scale-105 active:duration-75 active:before:scale-95 dark:before:border-gray-700 dark:before:bg-gray-800"
						>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="transistion relative m-auto hidden h-5 w-5 fill-gray-500 duration-300 group-hover:rotate-180 group-hover:fill-yellow-400 dark:block dark:fill-gray-300"
								viewBox="0 0 20 20"
								fill="currentColor"
							>
								<path
									fill-rule="evenodd"
									d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z"
									clip-rule="evenodd"
								></path>
							</svg>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="transistion relative m-auto h-5 w-5 fill-gray-500 duration-300 group-hover:-rotate-90 group-hover:fill-blue-900 dark:hidden"
								viewBox="0 0 20 20"
								fill="currentColor"
							>
								<path
									d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z"
								></path>
							</svg>
						</button>
					</div>
				</div>
			</div>
		</nav>
	</header>
</template>
