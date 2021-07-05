<template>
    <div class="hidden w-56 h-full p-4 bg-gray-200 lg:block">
        <div class="flex-col">
            <div class="flex items-center justify-center ">
                <img src=".././assets/g-logo.png" class="w-10 h-10 rounded-md lg:w-12 lg:h-12" alt="logo"> 
            </div>
            <div class="">
                <div class="text-sm">
                    <h2 class="font-bold">Menu 1</h2>
                    <ul class="flex flex-col mt-2 space-y-2 text-gray-600">
                        <!-- active:  text-gray-800, font-bold, bg-gray-400 -->
                        <a class="flex items-center px-2 py-1 space-x-2 font-medium text-gray-800 bg-gray-400 rounded"
                        href="">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>Dashboard</span>                        
                        </a>
                        <a class="flex items-center px-2 py-1 space-x-2 rounded hover:bg-gray-400 "
                        href="">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>About</span>                        
                        </a>
                        <a class="flex items-center px-2 py-1 space-x-2 hover:text-gray-700 "
                        href="">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>Contact Us</span>                        
                        </a>
                        <li class="px-2 py-1 hover:text-gray-700 "
                        >                        
                            <button @click="sidebarDropdown = !sidebarDropdown" class="items-center block w-full space-x-2 focus:outline-none">
                                <span class="flex items-center justify-between">
                                    <span class="flex space-x-2">
                                        <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                                        </svg>
                                        <span>Dropdown</span>
                                    </span>

                                    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5" viewBox="0 0 20 20" fill="currentColor">
                                        <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                                    </svg>
                                </span>
                            </button> 
                            <div class="mt-2 ml-5 border" v-show="sidebarDropdown">
                                <ul class="ml-1 space-y-1">
                                    <a href="" class="block p-px hover:bg-gray-300">Item 1</a>                                
                                    <a href="" class="block p-px hover:bg-gray-300">Item 2</a>                                
                                    <a href="" class="block p-px hover:bg-gray-300">Item 2 {{sidebarDropdown}}</a>                                
                                </ul>    
                            </div>          

                        </li>
                        
                    </ul>
                </div>

                <div class="mt-8 text-sm">
                    <h2 class="font-bold">Menu 2</h2>
                    <ul class="flex flex-col mt-2 space-y-2 text-gray-600">
                        <a class="flex items-center px-2 py-1 space-x-2 font-medium text-gray-800 bg-gray-300 rounded"
                        href="">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>Dashboard</span>                        
                        </a>
                        <a class="flex items-center px-2 py-1 space-x-2 hover:text-gray-700 "
                        href="">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>About</span>                        
                        </a>
                        <a class="flex items-center px-2 py-1 space-x-2 hover:text-gray-700 "
                        href="">
                            <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                            </svg>
                            <span>Contact Us</span>                        
                        </a>
                        
                    </ul>
                </div>
                
            </div>
        </div>
    </div>
</template>
<script>

export default({
    name: 'SideBar',
    data(){
        return{
            sidebarDropdown: false,
        }
    }
})
</script>
