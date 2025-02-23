<script setup lang="ts">
const setupFaq = () => {
    let faqs = document.querySelectorAll<HTMLElement>(".faq");

    for (let i = 0; i < faqs.length; i++) {
        let answer = faqs[i].querySelector<HTMLElement>(".faq-answer");
        let icon = faqs[i].querySelector<HTMLElement>(".arrow-down");

        if (!icon || !answer) {
            continue;
        }

        faqs[i].addEventListener("click", () => {
            for (let j = 0; j < faqs.length; j++) {
                let answer2 = faqs[j].querySelector<HTMLElement>(".faq-answer");
                let icon2 = faqs[j].querySelector<HTMLElement>(".arrow-down");

                if (!icon2 || !answer2) {
                    continue;
                }

                if (faqs[i] != faqs[j]) {
                    answer2.style.maxHeight = "0px";
                    icon2.classList.replace("rotate-180", "rotate-0");
                }
            }

            if (icon.classList.contains("rotate-180")) {
                answer.style.maxHeight = 0 + "px";
                icon.classList.replace("rotate-180", "rotate-0");
            } else {
                answer.style.maxHeight = answer.scrollHeight + "px";
                icon.classList.replace("rotate-0", "rotate-180");
            }
        });
    }
};

// Wait for mounted component, in order to setup faq javascript
onMounted(() => {
    setupFaq();
});
</script>

<template>
    <section id="faqs" class="my-32">
        <div class="mx-auto px-4 sm:px-12 xl:max-w-5xl xl:px-0">
            <h2 class="mb-12 text-center text-3xl font-bold text-gray-800 dark:text-white md:text-4xl xl:text-5xl">Frequently Asqued Questions</h2>

            <div class="divide-y divide-gray-200 border-y border-gray-200 dark:divide-gray-800 dark:border-gray-800">
                <div>
                    <dl class="faq mx-auto max-w-2xl">
                        <dt class="text-lg">
                            <button type="button" class="flex w-full items-start justify-between py-6 text-left text-gray-400" aria-controls="faq-0" data-active="false">
                                <span class="font-medium text-gray-900 dark:text-white">What included in the pack ?</span>
                                <span class="ml-6 flex h-7 items-center">
                                    <svg class="arrow-down h-6 w-6 rotate-0 transform duration-300" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </span>
                            </button>
                        </dt>
                        <dd class="faq-answer block max-h-0 overflow-hidden pr-12 duration-300 ease-in-out" id="faq-0">
                            <p class="pb-6 text-base text-gray-600 dark:text-gray-400">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laborum quod pariatur possimus at fugit natus aspernatur molestiae. Velit, odio modi provident necessitatibus molestias qui voluptatibus similique magnam a nam rem!</p>
                        </dd>
                    </dl>
                </div>
                <div>
                    <dl class="faq mx-auto max-w-2xl">
                        <dt class="text-lg">
                            <button type="button" class="flex w-full items-start justify-between py-6 text-left text-gray-400" aria-controls="faq-1" data-active="false">
                                <span class="font-medium text-gray-900 dark:text-white">What included in the pack ?</span>
                                <span class="ml-6 flex h-7 items-center">
                                    <svg class="arrow-down h-6 w-6 rotate-0 transform duration-300" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </span>
                            </button>
                        </dt>
                        <dd class="faq-answer block max-h-0 overflow-hidden pr-12 duration-300 ease-in-out" id="faq-1">
                            <p class="pb-6 text-base text-gray-600 dark:text-gray-400">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laborum quod pariatur possimus at fugit natus aspernatur molestiae. Velit, odio modi provident necessitatibus molestias qui voluptatibus similique magnam a nam rem!</p>
                        </dd>
                    </dl>
                </div>
                <div>
                    <dl class="faq mx-auto max-w-2xl">
                        <dt class="text-lg">
                            <button type="button" class="flex w-full items-start justify-between py-6 text-left text-gray-400" aria-controls="faq-2" data-active="false">
                                <span class="font-medium text-gray-900 dark:text-white">What included in the pack ?</span>
                                <span class="ml-6 flex h-7 items-center">
                                    <svg class="arrow-down h-6 w-6 rotate-0 transform duration-300" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </span>
                            </button>
                        </dt>
                        <dd class="faq-answer block max-h-0 overflow-hidden pr-12 duration-300 ease-in-out" id="faq-2">
                            <p class="pb-6 text-base text-gray-600 dark:text-gray-400">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laborum quod pariatur possimus at fugit natus aspernatur molestiae. Velit, odio modi provident necessitatibus molestias qui voluptatibus similique magnam a nam rem!</p>
                        </dd>
                    </dl>
                </div>
                <div>
                    <dl class="faq mx-auto max-w-2xl">
                        <dt class="text-lg">
                            <button type="button" class="flex w-full items-start justify-between py-6 text-left text-gray-400" aria-controls="faq-4" data-active="false">
                                <span class="font-medium text-gray-900 dark:text-white">Are updates included in this pack ?</span>
                                <span class="ml-6 flex h-7 items-center">
                                    <svg class="arrow-down h-6 w-6 rotate-0 transform duration-300" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </span>
                            </button>
                        </dt>
                        <dd class="faq-answer block max-h-0 overflow-hidden pr-12 duration-300 ease-in-out" id="faq-4">
                            <p class="pb-6 text-base text-gray-600 dark:text-gray-400">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laborum quod pariatur possimus at fugit natus aspernatur molestiae. Velit, odio modi provident necessitatibus molestias qui voluptatibus similique magnam a nam rem!</p>
                        </dd>
                    </dl>
                </div>
                <div>
                    <dl class="faq mx-auto max-w-2xl">
                        <dt class="text-lg">
                            <button type="button" class="flex w-full items-start justify-between py-6 text-left text-gray-400" aria-controls="faq-5" data-active="false">
                                <span class="font-medium text-gray-900 dark:text-white">What included in the pack ?</span>
                                <span class="ml-6 flex h-7 items-center">
                                    <svg class="arrow-down h-6 w-6 rotate-0 transform duration-300" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" aria-hidden="true">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </span>
                            </button>
                        </dt>
                        <dd class="faq-answer block max-h-0 overflow-hidden pr-12 duration-300 ease-in-out" id="faq-5">
                            <p class="pb-6 text-base text-gray-600 dark:text-gray-400">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Laborum quod pariatur possimus at fugit natus aspernatur molestiae. Velit, odio modi provident necessitatibus molestias qui voluptatibus similique magnam a nam rem!</p>
                        </dd>
                    </dl>
                </div>
            </div>
        </div>
    </section>
</template>
