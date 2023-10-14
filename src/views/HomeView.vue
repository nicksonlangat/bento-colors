<template>
<div :style="bodyStyle">

    <div class="mx-auto container pb-5 lg:pb-0">
        <button :style="bgStyle" @click="changeColors" class="fixed flex items-center rounded-full max-w-xs p-4 space-x-4 text-stone-300 shadow bottom-8 right-5">
            <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-palette" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                <path d="M12 21a9 9 0 0 1 0 -18c4.97 0 9 3.582 9 8c0 1.06 -.474 2.078 -1.318 2.828c-.844 .75 -1.989 1.172 -3.182 1.172h-2.5a2 2 0 0 0 -1 3.75a1.3 1.3 0 0 1 -1 2.25"></path>
                <path d="M8.5 10.5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                <path d="M12.5 7.5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                <path d="M16.5 10.5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
            </svg>
        </button>
        <nav :style="bgStyle" class="lg:w-full mx-3 lg:mx-0 text-sm text-stone-300 h-16 mt-2 flex items-center justify-between rounded-md">
           <div class="hidden lg:flex gap-5 text-stone-400 ml-3">
            <a href="">About us</a>
            <a href="" class="text-white">Features</a>
            <a href="">Integrations</a>
           </div>
            <div class="ml-5 lg:ml-0 relative">
                <input :style="bodyStyle" type="text" class="py-2 rounded-md lg:w-96 w-80 focus:outline-none focus:ring-0 placeholder:text-stone-400 pl-10" placeholder="Search or quick actions">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 absolute top-1.5 mx-2">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M21 21l-5.197-5.197m0 0A7.5 7.5 0 105.196 5.196a7.5 7.5 0 0010.607 10.607z" />
                </svg>
                <span :style="bgStyle" class="px-1 py-1 absolute top-1 right-10 mr-4 rounded">
                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler  icon-tabler-command" width="20" height="20" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                    <path d="M7 9a2 2 0 1 1 2 -2v10a2 2 0 1 1 -2 -2h10a2 2 0 1 1 -2 2v-10a2 2 0 1 1 2 2h-10"></path>
                </svg>
                </span>
                <span :style="bgStyle" class="px-1 py-1 absolute top-1 right-2 rounded">
                <svg xmlns="http://www.w3.org/2000/svg" class="icon  icon-tabler icon-tabler-letter-k" width="20" height="20" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                    <path d="M7 4l0 16"></path>
                    <path d="M7 12h2l8 -8"></path>
                    <path d="M9 12l8 8"></path>
                </svg>
                </span>
            </div>

            <div class="lg:flex hidden text-stone-300 cursor-pointer gap-3 mr-5">
                <span :style="bodyStyle" class="px-2 py-2 rounded-full">
                    <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-bell" width="20" height="20" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                        <path d="M10 5a2 2 0 1 1 4 0a7 7 0 0 1 4 6v3a4 4 0 0 0 2 3h-16a4 4 0 0 0 2 -3v-3a7 7 0 0 1 4 -6"></path>
                        <path d="M9 17v1a3 3 0 0 0 6 0v-1"></path>
                    </svg>
                </span>
                <span :style="bodyStyle" class="px-2 py-2 rounded-full">
                    <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-message-2" width="20" height="20" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                        <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                        <path d="M8 9h8"></path>
                        <path d="M8 13h6"></path>
                        <path d="M9 18h-3a3 3 0 0 1 -3 -3v-8a3 3 0 0 1 3 -3h12a3 3 0 0 1 3 3v8a3 3 0 0 1 -3 3h-3l-3 3l-3 -3z"></path>
                    </svg>
                </span>
            </div>
        </nav>

        <div class="flex flex-col mx-3 lg:mx-0 lg:flex-row gap-5 mt-3">
            <div :style="bgStyle" class="lg:w-2/3 lg:h-96 rounded-md">
                <div class="p-3  lg:h-[400px]">
                    <Bar id="my-chart-id" :options="chartOptions" :data="chartData" />
                </div>
            </div>
            <div :style="bgStyle" class="lg:w-1/3 text-stone-300 h-96 text-sm rounded-md">
                <ul class="p-3 flex-col gap-3 flex">
                    <li :style="bodyStyle" class="flex rounded-md">
                        <div class="w-1/6">
                            <img src="../assets/khaid.jpeg" class="rounded-l h-12 w-12 object-cover" alt="">
                        </div>
                        <div class="w-5/6 flex items-center justify-between">
                            <div class="ml-5">
                                <h3>Khaid</h3>
                                <p>No time</p>
                            </div>
                            <div class="flex gap-5">
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-heart-filled text-[#29f908]" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M6.979 3.074a6 6 0 0 1 4.988 1.425l.037 .033l.034 -.03a6 6 0 0 1 4.733 -1.44l.246 .036a6 6 0 0 1 3.364 10.008l-.18 .185l-.048 .041l-7.45 7.379a1 1 0 0 1 -1.313 .082l-.094 -.082l-7.493 -7.422a6 6 0 0 1 3.176 -10.215z" stroke-width="0" fill="currentColor"></path>
                                </svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-dots-vertical" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                    <li :style="bodyStyle" class="flex rounded-md">
                        <div class="w-1/6">
                            <img src="../assets/magixx.jpeg" class="rounded-l h-12 w-12 object-cover" alt="">
                        </div>
                        <div class="w-5/6 flex items-center justify-between">
                            <div class="ml-5">
                                <h3>Magixx</h3>
                                <p>Love don't cost a dime</p>
                            </div>
                            <div class="flex gap-5">
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-heart-filled text-[#29f908]" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M6.979 3.074a6 6 0 0 1 4.988 1.425l.037 .033l.034 -.03a6 6 0 0 1 4.733 -1.44l.246 .036a6 6 0 0 1 3.364 10.008l-.18 .185l-.048 .041l-7.45 7.379a1 1 0 0 1 -1.313 .082l-.094 -.082l-7.493 -7.422a6 6 0 0 1 3.176 -10.215z" stroke-width="0" fill="currentColor"></path>
                                </svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-dots-vertical" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                    <li :style="bodyStyle" class="flex rounded-md">
                        <div class="w-1/6">
                            <img src="../assets/ykb.jpeg" class="rounded-l h-12 w-12 object-cover" alt="">
                        </div>
                        <div class="w-5/6 flex items-center justify-between">
                            <div class="ml-5">
                                <h3>YKB</h3>
                                <p>Sansiro</p>
                            </div>
                            <div class="flex gap-5">
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-heart-filled text-[#29f908]" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M6.979 3.074a6 6 0 0 1 4.988 1.425l.037 .033l.034 -.03a6 6 0 0 1 4.733 -1.44l.246 .036a6 6 0 0 1 3.364 10.008l-.18 .185l-.048 .041l-7.45 7.379a1 1 0 0 1 -1.313 .082l-.094 -.082l-7.493 -7.422a6 6 0 0 1 3.176 -10.215z" stroke-width="0" fill="currentColor"></path>
                                </svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler  icon-tabler-dots-vertical" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                    <li :style="bodyStyle" class="flex rounded-md">
                        <div class="w-1/6">
                            <img src="../assets/vic.jpeg" class="rounded-l h-12 w-12 object-cover" alt="">
                        </div>
                        <div class="w-5/6 flex items-center justify-between">
                            <div class="ml-5">
                                <h3>Victony</h3>
                                <p>Belle full</p>
                            </div>
                            <div class="flex gap-5">
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-heart-filled text-[#29f908]" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M6.979 3.074a6 6 0 0 1 4.988 1.425l.037 .033l.034 -.03a6 6 0 0 1 4.733 -1.44l.246 .036a6 6 0 0 1 3.364 10.008l-.18 .185l-.048 .041l-7.45 7.379a1 1 0 0 1 -1.313 .082l-.094 -.082l-7.493 -7.422a6 6 0 0 1 3.176 -10.215z" stroke-width="0" fill="currentColor"></path>
                                </svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-dots-vertical" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                    <li :style="bodyStyle" class="flex  rounded-md">
                        <div class="w-1/6">
                            <img src="../assets/tekno.jpeg" class="rounded-l h-12 w-12" alt="">
                        </div>
                        <div class="w-5/6 flex items-center justify-between">
                            <div class="ml-5">
                                <h3>Tekno</h3>
                                <p>Peace of mind</p>
                            </div>
                            <div class="flex gap-5">
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-heart-filled text-[#29f908]" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M6.979 3.074a6 6 0 0 1 4.988 1.425l.037 .033l.034 -.03a6 6 0 0 1 4.733 -1.44l.246 .036a6 6 0 0 1 3.364 10.008l-.18 .185l-.048 .041l-7.45 7.379a1 1 0 0 1 -1.313 .082l-.094 -.082l-7.493 -7.422a6 6 0 0 1 3.176 -10.215z" stroke-width="0" fill="currentColor"></path>
                                </svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-dots-vertical" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                    <li :style="bodyStyle" class="flex rounded-md">
                        <div class="w-1/6">
                            <img src="../assets/burna.webp" class="rounded-l h-12 w-12" alt="">
                        </div>
                        <div class="w-5/6 flex items-center justify-between">
                            <div class="ml-5">
                                <h3>Burnaboy</h3>
                                <p>Rollercoaster</p>
                            </div>
                            <div class="flex gap-5">
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-heart-filled text-[#29f908]" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M6.979 3.074a6 6 0 0 1 4.988 1.425l.037 .033l.034 -.03a6 6 0 0 1 4.733 -1.44l.246 .036a6 6 0 0 1 3.364 10.008l-.18 .185l-.048 .041l-7.45 7.379a1 1 0 0 1 -1.313 .082l-.094 -.082l-7.493 -7.422a6 6 0 0 1 3.176 -10.215z" stroke-width="0" fill="currentColor"></path>
                                </svg>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-dots-vertical" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 12m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 19m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                    <path d="M12 5m-1 0a1 1 0 1 0 2 0a1 1 0 1 0 -2 0"></path>
                                </svg>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
        <div class="mt-3 grid gap-5 mx-3 lg:mx-0 lg:grid-cols-3">
            <div :style="bgStyle" class="h-80 text-stone-200 rounded-md">
                <div class="p-3">
                    <h3 class="text-4xl font-bold text-stone-300">299$ <span class="text-xs">/month</span></h3>
                    <div class="flex gap-3 mt-3 items-center">
                        <h3>Pro</h3> <span :style="bodyStyle" class="text-xs text-[#29f908] py-2 px-4 rounded-full">recommended</span>
                    </div>
                    <ul class="flex text-sm flex-col gap-3 mt-3">
                        <li class="inline-flex gap-2 items-center">
                            <svg xmlns="http://www.w3.org/2000/svg" class="" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                <path d="M17 3.34a10 10 0 1 1 -14.995 8.984l-.005 -.324l.005 -.324a10 10 0 0 1 14.995 -8.336zm-1.293 5.953a1 1 0 0 0 -1.32 -.083l-.094 .083l-3.293 3.292l-1.293 -1.292l-.094 -.083a1 1 0 0 0 -1.403 1.403l.083 .094l2 2l.094 .083a1 1 0 0 0 1.226 0l.094 -.083l4 -4l.083 -.094a1 1 0 0 0 -.083 -1.32z" stroke-width="0" fill="currentColor"></path>
                            </svg>
                            Unlimited projects
                        </li>
                        <li class="inline-flex gap-2 items-center">
                            <svg xmlns="http://www.w3.org/2000/svg" class="" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                <path d="M17 3.34a10 10 0 1 1 -14.995 8.984l-.005 -.324l.005 -.324a10 10 0 0 1 14.995 -8.336zm-1.293 5.953a1 1 0 0 0 -1.32 -.083l-.094 .083l-3.293 3.292l-1.293 -1.292l-.094 -.083a1 1 0 0 0 -1.403 1.403l.083 .094l2 2l.094 .083a1 1 0 0 0 1.226 0l.094 -.083l4 -4l.083 -.094a1 1 0 0 0 -.083 -1.32z" stroke-width="0" fill="currentColor"></path>
                            </svg>
                            Custom contracts
                        </li>
                        <li class="inline-flex gap-2 items-center">
                            <svg xmlns="http://www.w3.org/2000/svg" class="" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                <path d="M17 3.34a10 10 0 1 1 -14.995 8.984l-.005 -.324l.005 -.324a10 10 0 0 1 14.995 -8.336zm-1.293 5.953a1 1 0 0 0 -1.32 -.083l-.094 .083l-3.293 3.292l-1.293 -1.292l-.094 -.083a1 1 0 0 0 -1.403 1.403l.083 .094l2 2l.094 .083a1 1 0 0 0 1.226 0l.094 -.083l4 -4l.083 -.094a1 1 0 0 0 -.083 -1.32z" stroke-width="0" fill="currentColor"></path>
                            </svg>
                            Single sign-on (SSO)
                        </li>
                        <li class="inline-flex gap-2 items-center">
                            <svg xmlns="http://www.w3.org/2000/svg" class="" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                <path d="M17 3.34a10 10 0 1 1 -14.995 8.984l-.005 -.324l.005 -.324a10 10 0 0 1 14.995 -8.336zm-1.293 5.953a1 1 0 0 0 -1.32 -.083l-.094 .083l-3.293 3.292l-1.293 -1.292l-.094 -.083a1 1 0 0 0 -1.403 1.403l.083 .094l2 2l.094 .083a1 1 0 0 0 1.226 0l.094 -.083l4 -4l.083 -.094a1 1 0 0 0 -.083 -1.32z" stroke-width="0" fill="currentColor"></path>
                            </svg>
                            Invoice payments
                        </li>
                    </ul>
                    <button class="bg-[#29f908] text-stone-900 py-2 w-full rounded-md mt-5">Subscribe to pro</button>

                </div>
            </div>
            <div class="lg:col-span-2 flex flex-col gap-2 h-80 rounded-md">
                <div class="grid lg:grid-cols-2 gap-5">
                    <div :style="bgStyle" class="h-64 text-stone-200 rounded-md">
                        <div class="p-2">
                            <div class="flex justify-between items-center">
                                <h3 class="uppercase text-sm text-stone-300">Money plan</h3>
                                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-plus" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                    <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                    <path d="M12 5l0 14"></path>
                                    <path d="M5 12l14 0"></path>
                                </svg>
                            </div>
                            <ul class="flex mt-5 flex-col gap-5">
                                <li class="flex gap-4 items-center">
                                    <span :style="bodyStyle" class="px-3 py-3 rounded-md">
                                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-car-garage" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                            <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                            <path d="M5 20a2 2 0 1 0 4 0a2 2 0 0 0 -4 0"></path>
                                            <path d="M15 20a2 2 0 1 0 4 0a2 2 0 0 0 -4 0"></path>
                                            <path d="M5 20h-2v-6l2 -5h9l4 5h1a2 2 0 0 1 2 2v4h-2m-4 0h-6m-6 -6h15m-6 0v-5"></path>
                                            <path d="M3 6l9 -4l9 4"></path>
                                        </svg>
                                    </span>
                                    <div>
                                        <p class="text-sm">Garage Maintenance</p>
                                        <small class="text-stone-300 text-xs">$2500.00</small>
                                    </div>
                                </li>
                                <li class="flex  gap-4 items-center">
                                    <span :style="bodyStyle" class="px-3 py-3 rounded-md">
                                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-shopping-cart" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                            <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                            <path d="M6 19m-2 0a2 2 0 1 0 4 0a2 2 0 1 0 -4 0"></path>
                                            <path d="M17 19m-2 0a2 2 0 1 0 4 0a2 2 0 1 0 -4 0"></path>
                                            <path d="M17 17h-11v-14h-2"></path>
                                            <path d="M6 5l14 1l-1 7h-13"></path>
                                        </svg>
                                    </span>
                                    <div>
                                        <p class="text-sm">Monthly groceries</p>
                                        <small class="text-stone-300 text-xs">$1500.00</small>
                                    </div>
                                </li>
                                <li class="flex gap-4 items-center">
                                    <span :style="bodyStyle" class="px-3 py-3 rounded-md">
                                        <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-router" width="24" height="24" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">
                                            <path stroke="none" d="M0 0h24v24H0z" fill="none"></path>
                                            <path d="M3 13m0 2a2 2 0 0 1 2 -2h14a2 2 0 0 1 2 2v4a2 2 0 0 1 -2 2h-14a2 2 0 0 1 -2 -2z"></path>
                                            <path d="M17 17l0 .01"></path>
                                            <path d="M13 17l0 .01"></path>
                                            <path d="M15 13l0 -2"></path>
                                            <path d="M11.75 8.75a4 4 0 0 1 6.5 0"></path>
                                            <path d="M8.5 6.5a8 8 0 0 1 13 0"></path>
                                        </svg>
                                    </span>
                                    <div>
                                        <p class="text-sm">Internet subscription</p>
                                        <small class="text-stone-300 text-xs">$699.00</small>
                                    </div>
                                </li>
                            </ul>
                        </div>

                    </div>
                    <div :style="bgStyle" class="h-64 text-sm text-stone-300 rounded-md">
                        <div class="p-3">
                            <h3>Share your link</h3>
                            <div class="border flex justify-between border-stone-600 rounded-full w-full py-1.5 mt-2">
                                <h3 class="ml-5">share/638e5c4ec2a44f4dbae48f75</h3><span :style="bodyStyle" class="text-xs text-[#29f908] py-1 px-2 mr-5 rounded-full">copy</span>
                            </div>

                            <div class="flex justify-between items-center mt-2">
                                <div class="lg:w-80 w-64 bg-gray-200 rounded-full h-1.5">
                                    <div class="bg-[#29f908] h-1.5 rounded-full" style="width: 75%"></div>
                                </div>
                                75%
                            </div>
                            <ul class="flex text-xs flex-col gap-3 mt-2">
                                <li class="flex justify-between items-center">
                                    <span class="inline-flex gap-2 items-center"><img class="w-8 h-8 rounded-full" src="https:flowbite.com/docs/images/people/profile-picture-4.jpg" alt="Rounded avatar">
                                        <h3>Mary Lopez</h3>
                                    </span>
                                    <h3>07.06.2023</h3>

                                </li>
                                <li class="flex justify-between items-center">
                                    <span class="inline-flex gap-2 items-center"><img class="w-8 h-8 rounded-full" src="https:flowbite.com/docs/images/people/profile-picture-3.jpg" alt="Rounded avatar">
                                        <h3>Jecintah Mueni</h3>
                                    </span>
                                    <h3>23.04.2023</h3>

                                </li>
                                <li class="flex justify-between items-center">
                                    <span class="inline-flex gap-2 items-center"><img class="w-8 h-8 rounded-full" src="https:flowbite.com/docs/images/people/profile-picture-2.jpg" alt="Rounded avatar">
                                        <h3>Nick Van Otto</h3>
                                    </span>
                                    <h3>01.02.2023</h3>

                                </li>
                            </ul>

                        </div>
                    </div>
                </div>
                <div :style="bgStyle" class="lg:h-24 pb-2 lg:pb-0 lg:mx-0 w-full text-xs flex justify-end items-center rounded-md">
                    <div class="mr-6 flex gap-5 mt-3 lg:mt-0">
                        <input type="text" class="bg-inherit py-2 border rounded-md border-stone-400 placeholder:text-stone-400 focus:outline-none focus:ring-0 text-stone-300 lg:w-64 pl-4" placeholder="Email address...">
                        <button class="py-1 rounded-md px-6 bg-[#29f908] text-stone-800">Join waitlist</button>
                    </div>
                </div>
            </div>

        </div>
    </div>
</div>
</template>

<script>
import {
    Bar
} from 'vue-chartjs'
import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    BarElement,
    CategoryScale,
    LinearScale
} from 'chart.js'

ChartJS.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

export default {
    name: 'Home',
    components: {
        Bar
    },
    data() {
        return {
            chartData: {
                labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
                datasets: [{
                        data: [40, 20, 12, 70, 98, 54, 12, 67, 120, 100, 80, 65],
                        backgroundColor: ['#29f908', ], //AFFC00
                        label: 'Money in',
                    },

                    {
                        data: [80, 40, 18, 40, 98, 84, 22, 37, 70, 120, 20, 165],
                        backgroundColor: ['#ededf3'],
                        label: 'Money out',
                    }

                ]
            },
            chartOptions: {
                responsive: true
            },
            index: 0,
            bgStyle: {
                backgroundColor: "#252629f2"
            },
            bodyStyle: {
                backgroundColor: "#1a1b1e"
            },
            backgroundColors: ["#252629f2", "#252830", "#282A36", "#242424", "#181D27", "#37373E", "#0b0b0f"],
            bodyColors: ["#1a1b1e", "#1D1E22", "#161B22", "#1A1A1A", "#0E1117", "#080809", "#000000"],
        }
    },
    methods: {
        changeColors() {
            this.index++
            if (this.backgroundColors.length > this.index) {
                this.bgStyle.backgroundColor = this.backgroundColors[this.index]
                this.bodyStyle.backgroundColor = this.bodyColors[this.index]
                document.body.style.backgroundColor = this.bodyColors[this.index]
            }

        }
    },
    created: function () {
        document.body.style.backgroundColor = this.bodyStyle.backgroundColor
    },
    destroyed: function () {
        document.body.style.backgroundColor = null;
    },
}
</script>
