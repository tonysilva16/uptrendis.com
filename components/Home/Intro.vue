<template>
	<section id="home" class="pt-32 sm:pt-40 md:pt-48">
		<div class="mx-auto px-4 sm:px-12 xl:max-w-6xl xl:px-0">
			<div class="relative">
				<h1
					class="text-center text-5xl font-bold text-blue-900 dark:text-white sm:text-6xl lg:text-left lg:text-7xl"
				>
					Go modern with us
					<span class="relative">
						<img href="./../assets/design.svg" />
						<span
							class="relative bg-gradient-to-r from-primary to-secondaryLight bg-clip-text text-transparent dark:from-primaryLight dark:to-secondaryLight"
						>
							Up-trend
						</span>
					</span>
				</h1>

				// https://player.vimeo.com/video/999438269?background=1
				<div class="relative items-center gap-12 lg:flex">
					<div
						class="text-center sm:mx-auto sm:w-11/12 md:mt-12 md:w-4/5 lg:mr-auto lg:mt-0 lg:w-6/12 lg:text-left"
					>
						<p class="mt-12 text-lg text-gray-600 dark:text-gray-300 sm:text-xl">
							Get in touch to have more information how you can improve your bowling
							experience
						</p>
						<form action="" class="mt-12">
							<div
								class="relative flex items-center rounded-full border border-primary/20 bg-white p-1 px-2 shadow-md focus-within:ring-2 dark:border-white/10 dark:bg-dark md:p-2 lg:pr-3"
							>
								<div class="py-3 pl-4 lg:pl-5">
									<svg
										xmlns="http://www.w3.org/2000/svg"
										class="m-auto h-6 w-6 fill-gray-500 dark:fill-gray-400"
										viewBox="0 0 20 20"
										fill="currentColor"
									>
										<path
											d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"
										/>
										<path
											d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"
										/>
									</svg>
								</div>
								<input
									aria-label="your email"
									autocomplete="email"
									placeholder="Your mail address"
									class="w-full rounded-full bg-transparent p-4 placeholder-gray-600 outline-none dark:text-white dark:placeholder-white"
									type="email"
								/>
								<div class="md:pr-1.5 lg:pr-0">
									<button
										type="button"
										title="Start buying"
										class="relative ml-auto h-12 w-16 before:absolute before:inset-0 before:rounded-full before:bg-primary before:transition before:duration-300 active:duration-75 active:before:scale-95 dark:before:bg-primaryLight sm:w-auto sm:px-6"
									>
										<span
											class="relative hidden w-max font-semibold text-white dark:text-gray-900 md:block"
										>
											Get Started
										</span>
										<svg
											xmlns="http://www.w3.org/2000/svg"
											viewBox="0 0 24 24"
											fill="currentColor"
											class="relative mx-auto h-6 w-6 text-white dark:text-gray-900 md:hidden"
										>
											<path
												d="M3.478 2.405a.75.75 0 00-.926.94l2.432 7.905H13.5a.75.75 0 010 1.5H4.984l-2.432 7.905a.75.75 0 00.926.94 60.519 60.519 0 0018.445-8.986.75.75 0 000-1.218A60.517 60.517 0 003.478 2.405z"
											/>
										</svg>
									</button>
								</div>
							</div>
						</form>
					</div>
					<div class="mt-12 w-full overflow-hidden sm:mt-20 lg:-mt-8 lg:w-6/12">
						<img
							class="w-full"
							src="https://placehold.co/562x466"
							alt="project illustration"
							height="600"
							width="800"
						/>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>
