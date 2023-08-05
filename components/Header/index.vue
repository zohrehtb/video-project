<template>
  <header id="main-header">
    <nav class="bg-black border-gray-200 ">
        <div class="container mx-auto flex flex-wrap items-center justify-between lg:justify-start p-4">
            <a href="https://x.com/" class="flex items-center">
                <img 
                    src="~/assets/images/logo.png" 
                    class="h-8 mr-3" 
                    alt="vod Logo" 
                />
                
                <h1 class="overflow-hidden">{{ 'SiteName' }}</h1>
            </a>
            <div class="flex lg:order-2">
                <button 
                    type="button" 
                    data-collapse-toggle="navbar-search" 
                    aria-controls="navbar-search" 
                    aria-expanded="false" 
                    class="lg:hidden text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-4 focus:ring-gray-200 rounded-lg text-sm p-2.5 mr-1" 
                >
                    <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z"/>
                    </svg>
                </button>

                <div class="relative hidden lg:block">
                    <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                        <svg class="w-4 h-4 text-gray-500" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z"/>
                        </svg>
                    </div>

                    <input 
                        type="text" 
                        id="search-navbar" 
                        class="xl:w-[403px] block w-full p-2 pl-10 text-sm text-[#7B748A] border border-[#7B748A] rounded-lg bg-black focus:ring-blue-500 focus:border-blue-500" 
                        placeholder="جستجو کنید"
                    >
                </div>
                <button 
                    data-collapse-toggle="navbar-search" 
                    type="button" 
                    class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-gray-500 rounded-lg lg:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200" 
                    aria-controls="navbar-search" 
                    aria-expanded="false"
                >
                    <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15"/>
                    </svg>
                </button>

                <button 
                    type="button" 
                    class="text-white bg-[#FF4E7B] font-medium rounded-lg text-sm px-4 py-2 text-center mr-3"
                > 
                    <font-awesome-icon :icon="['fas', 'user']" />
                </button>
            </div>

            <div 
                class="items-center justify-start hidden w-full lg:flex lg:w-auto lg:order-1 lg:grow" 
                id="navbar-search"
            >
                <div class="relative mt-3 lg:hidden">
                    <div class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none">
                        <svg class="w-4 h-4 text-gray-500" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 20 20">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z"/>
                        </svg>
                    </div>

                    <input 
                        type="text" 
                        id="search-navbar" 
                        class="block w-full p-2 pl-10 text-sm text-[#7B748A] border border-[#7B748A] rounded-lg bg-black focus:ring-blue-500 focus:border-blue-500" 
                        placeholder="جستجو کنید"
                    >
                </div>

                <ul class="main-menu flex flex-col p-4 lg:p-0 mt-4 font-medium border border-gray-100 rounded-lg lg:flex-row lg:space-x-8 lg:mt-0 lg:border-0">
                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-white bg-blue-700 lg:bg-transparent lg:text-white" 
                            aria-current="page"
                        >
                            {{ 'فیلم' }}
                        </a>
                    </li>

                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-[#7B748A] hover:bg-gray-100 lg:hover:bg-transparent lg:hover:text-white"
                            >
                            {{ 'مینی سریال' }}
                        </a>
                    </li>

                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-[#7B748A] hover:bg-gray-100 lg:hover:bg-transparent lg:hover:text-white "
                        >
                            {{ 'تئاتر' }}
                        </a>
                    </li>

                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-[#7B748A] hover:bg-gray-100 lg:hover:bg-transparent lg:hover:text-white"
                        >
                            {{ 'انیمیشن' }}
                        </a>
                    </li>

                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-[#7B748A] hover:bg-gray-100 lg:hover:bg-transparent lg:hover:text-white"
                        >
                            {{ 'مستند' }}
                        </a>
                    </li>

                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-[#7B748A] hover:bg-gray-100 lg:hover:bg-transparent lg:hover:text-white"
                        >
                            {{ 'کودک' }}
                        </a>
                    </li>

                    <li class="m-0 py-2">
                        <a 
                            href="#" 
                            class="block border-l border-[#332D41] pl-4 pr-4 text-[#7B748A] hover:bg-gray-100 lg:hover:bg-transparent lg:hover:text-white"
                        >
                            {{ 'خبرنامه' }}
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
  </header>
</template>

<script>
export default {
    name:'headerComponent',

}
</script>

<style lang="scss" src="./index.scss" />
