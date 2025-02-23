<script setup lang="ts">
const setup = () => {
	let tabs = document.querySelectorAll<HTMLElement>('.tab')
	let indicator = document.querySelector<HTMLElement>('.tab-indicator')
	let panels = document.querySelectorAll<HTMLElement>('.panel')
	let previews = document.querySelectorAll<HTMLElement>('.panel-preview')
	if (!indicator || !panels || !tabs) {
		return
	}
	if (indicator !== null && tabs[0].parentElement) {
		indicator.style.width = tabs[0].getBoundingClientRect().width + 'px'
		indicator.style.left =
			tabs[0].getBoundingClientRect().left -
			tabs[0].parentElement.getBoundingClientRect().left +
			'px'
	}

	tabs.forEach((tab) => {
		tab.addEventListener('click', () => {
			if (!tab.parentElement) {
				return
			}

			let tabTarget = tab.getAttribute('aria-controls')

			indicator.style.width = tab.getBoundingClientRect().width + 'px'
			indicator.style.left =
				tab.getBoundingClientRect().left -
				tab.parentElement.getBoundingClientRect().left +
				'px'

			panels.forEach((panel) => {
				let panelId = panel.getAttribute('id')
				if (tabTarget === panelId) {
					panel.classList.remove('invisible', 'opacity-0', 'scale-90')
					panel.classList.add('visible', 'opacity-100', 'scale-100')
				} else {
					panel.classList.add('invisible', 'opacity-0', 'scale-90')
					panel.classList.remove('visible', 'opacity-100', 'scale-100')
				}

				previews.forEach((preview) => {
					let prevTarget = preview.getAttribute('data-target')

					if (tabTarget === prevTarget) {
						preview.classList.replace('translate-y-[100%]', 'translate-y-0')
						preview.classList.replace('scale-75', 'scale-100')
						preview.classList.replace('opacity-50', 'opacity-100')
						preview.classList.replace('z-0', 'z-10')
					} else {
						preview.classList.replace('scale-100', 'scale-75')
						preview.classList.replace('opacity-100', 'opacity-50')
						preview.classList.replace('z-10', 'z-0')

						setTimeout(() => {
							preview.classList.replace('translate-y-0', 'translate-y-[100%]')
						}, 300)
						clearTimeout(undefined)
					}
				})
			})
		})
	})
}

onMounted(() => {
	setup()
})
</script>
<template>
	<section id="solutions" class="pt-32">
		<div class="mx-auto px-4 sm:px-12 xl:max-w-6xl xl:px-0">
			<div class="text-center">
				<h2
					class="text-3xl font-bold text-gray-800 dark:text-white md:text-4xl xl:text-5xl"
				>
					Our solutions
				</h2>
				<p class="mx-auto mt-6 text-gray-700 dark:text-gray-300 md:w-3/4 lg:w-3/5">
					Lorem ipsum odor amet, consectetuer adipiscing elit. Nulla potenti egestas dui
					justo rhoncus nisi hendrerit litora! Rutrum rutrum bibendum nibh primis justo
					felis taciti platea
				</p>

				<div
					role="tablist"
					aria-label="tabs"
					class="relative mx-auto mt-12 grid h-12 w-auto grid-cols-3 items-center gap-x-1 overflow-hidden rounded-full border border-gray-200 bg-gray-100 px-[3px] text-gray-600 dark:border-gray-700 dark:border-opacity-60 dark:bg-darker dark:text-gray-300 dark:shadow-none sm:w-max"
				>
					<div
						class="tab-indicator absolute h-10 rounded-full bg-white shadow-md transition-[left] duration-500 dark:bg-gray-800"
						style="left: 4px"
					></div>
					<button
						role="tab"
						aria-selected="true"
						aria-controls="panel-0"
						tabindex="0"
						title="tab item"
						class="tab relative block rounded-full px-4 py-2.5 hover:text-primary dark:hover:text-primaryLight"
					>
						<span class="m-auto block w-max text-sm font-medium tracking-wider">
							Scoring
						</span>
					</button>
					<button
						role="tab"
						aria-selected="true"
						aria-controls="panel-0"
						tabindex="0"
						title="tab item"
						class="tab relative block rounded-full px-4 py-2.5 hover:text-primary dark:hover:text-primaryLight"
					>
						<span class="m-auto block w-max text-sm font-medium tracking-wider">
							Footbowl
						</span>
					</button>
					<button
						role="tab"
						aria-selected="false"
						aria-controls="panel-1"
						tabindex="-1"
						title="tab item"
						class="tab relative block rounded-full px-4 py-2.5 hover:text-primary dark:hover:text-primaryLight"
					>
						<span class="m-auto block w-max text-sm font-medium tracking-wider">
							Ledwall
						</span>
					</button>
					<button
						role="tab"
						aria-selected="false"
						aria-controls="panel-2"
						tabindex="-1"
						title="tab item"
						class="tab relative block rounded-full px-4 py-2.5 hover:text-primary dark:hover:text-primaryLight"
					>
						<span class="m-auto block w-max text-sm font-medium tracking-wider">
							Forniture
						</span>
					</button>
				</div>
			</div>
			<div class="mt-20">
				<div class="gap-6 space-y-12 md:flex md:space-y-0">
					<div class="relative md:w-1/2">
						<div
							class="panel visible inset-0 flex scale-100 flex-col justify-center opacity-100 transition duration-500 md:absolute"
							id="panel-0"
						>
							<div>
								<h3
									class="text-2xl font-bold text-gray-900 dark:text-white md:text-3xl"
								>
									Tab header 1
								</h3>
								<p class="mt-8 text-gray-600 dark:text-gray-300">
									Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eum
									omnis voluptatem accusantium nemo perspiciatis delectus atque
									autem! repellat expedita consequatur! Officiis id consequatur
									atque doloremque!
								</p>
							</div>
						</div>
						<div
							class="panel invisible absolute inset-0 flex scale-90 flex-col justify-center opacity-0 transition duration-500"
							id="panel-1"
						>
							<div>
								<h3
									class="text-2xl font-bold text-gray-900 dark:text-white md:text-3xl"
								>
									Tab header 2
								</h3>
								<p class="mt-8 text-gray-600 dark:text-gray-300">
									Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eum
									omnis voluptatem accusantium nemo perspiciatis delectus atque
									autem! repellat expedita consequatur! Officiis id consequatur
									atque doloremque!
								</p>
							</div>
						</div>
						<div
							class="panel invisible absolute inset-0 flex scale-90 flex-col justify-center opacity-0 transition duration-500"
							id="panel-2"
						>
							<div>
								<h3
									class="text-2xl font-bold text-gray-900 dark:text-white md:text-3xl"
								>
									Tab header 3
								</h3>
								<p class="mt-8 text-gray-600 dark:text-gray-300">
									Lorem ipsum dolor, sit amet consectetur adipisicing elit. Eum
									omnis voluptatem accusantium nemo perspiciatis delectus atque
									autem! repellat expedita consequatur! Officiis id consequatur
									atque doloremque!
								</p>
								<div class="mt-12 space-y-6">
									<div class="flex items-center gap-6">
										<div
											class="flex h-20 w-20 rounded-3xl border border-gray-200 bg-white p-4 dark:border-gray-600/60 dark:bg-gray-900/40"
										>
											<img
												class="m-auto h-8 w-auto"
												src="https://cdn-icons-png.flaticon.com/512/3340/3340200.png"
												alt="icon illustration"
												loading="lazy"
												width="512"
												height="512"
											/>
										</div>
										<div class="w-[calc(100%-7.5rem)]">
											<h4
												class="text-lg font-semibold text-gray-800 dark:text-white"
											>
												Together as one
											</h4>
											<p class="mt-1 text-gray-600 dark:text-gray-400">
												Accusantium nemo perspiciatis delectus atque autem!
											</p>
										</div>
									</div>

									<div class="flex items-center gap-6">
										<div
											class="flex h-20 w-20 rounded-3xl border border-gray-200 bg-white p-4 dark:border-gray-600/60 dark:bg-gray-900/40"
										>
											<img
												class="m-auto h-8 w-auto"
												src="https://cdn-icons-png.flaticon.com/512/5405/5405929.png"
												alt="icon illustration"
												loading="lazy"
												width="512"
												height="512"
											/>
										</div>
										<div class="w-[calc(100%-7.5rem)]">
											<h4
												class="text-lg font-semibold text-gray-800 dark:text-white"
											>
												Growth
											</h4>
											<p class="mt-1 text-gray-600 dark:text-gray-400">
												Accusalectus atque autem accusantium nemo
												perspiciatis delectus atque autem!
											</p>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
					<div
						class="-m-4 overflow-hidden p-4 sm:-mx-12 sm:px-12 md:mx-0 md:w-1/2 md:overflow-visible md:px-0"
					>
						<div
							class="relative bg-gray-100 before:absolute before:inset-0 before:scale-x-110 before:border-y before:border-gray-200 after:absolute after:inset-0 after:scale-y-110 after:border-x after:border-gray-200 dark:bg-gray-800 dark:before:border-gray-700 dark:after:border-gray-700"
						>
							<div class="relative h-96 overflow-clip py-10 sm:h-[32rem] lg:p-20">
								<div
									data-target="panel-0"
									class="panel-preview absolute inset-0 z-10 flex translate-y-0 scale-100 items-end overflow-hidden px-6 opacity-100 transition duration-500 sm:px-10"
								>
									<img
										src="https://placehold.co/850x1780"
										class="mx-auto h-80 w-96 rounded-t-3xl border object-cover object-top shadow-2xl dark:border-transparent sm:h-[28rem]"
										alt="tailus screenshot"
										width="850"
										height="1780"
									/>
								</div>
								<div
									data-target="panel-1"
									class="panel-preview absolute inset-0 z-0 flex translate-y-[100%] scale-100 items-end overflow-hidden px-6 opacity-50 transition duration-500 sm:px-10"
								>
									<img
										src="https://placehold.co/850x1780/black/white"
										class="mx-auto h-80 w-96 rounded-t-3xl border object-cover object-top shadow-2xl dark:border-transparent sm:h-[28rem]"
										alt="tailus screenshot dark-mode"
										width="850"
										height="1780"
									/>
								</div>
								<div
									data-target="panel-2"
									class="panel-preview absolute inset-0 z-0 flex translate-y-[100%] scale-100 items-end overflow-hidden px-6 opacity-50 transition duration-500 sm:px-10"
								>
									<img
										src="https://placehold.co/850x1780"
										class="mx-auto h-80 w-96 rounded-t-3xl border object-cover object-top shadow-2xl dark:border-transparent sm:h-[28rem]"
										alt="tailus contact screenshot"
										width="850"
										height="1780"
									/>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>
