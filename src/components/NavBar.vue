<template>
    <nav class="w-full">
        <div class="flex items-center justify-between w-full px-6 py-2 bg-gray-200">         
             <div class="flex items-center justify-center ">
                <img src=".././assets/g-logo.png" class="w-10 h-10 rounded-md lg:w-12 lg:h-12" alt="logo"> 
            </div>
            <!-- search -->
            <div class="flex items-center space-x-4">
                <button @click="searchBar = ! searchBar" class="font-medium focus:outline-none">
                    <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                    </svg>
                </button> 
                <!-- show only on small screens -->
                <button @click="navbarOpen = !navbarOpen" class="font-medium focus:outline-none lg:hidden"> 
                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                </svg>
                </button>

                <!-- show this nav on large screen -->
                <div class="relative items-center hidden space-x-6 text-gray-700 lg:flex">
                    <div class="">
                        <button @click="settingsOpen = ! settingsOpen" class="flex items-center focus:outline-none">
                           <span>Settings</span> 
                        <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                        </svg> 
                        </button>                          
                    </div>
                    <div>
                        <button @click="projectsOpen = ! projectsOpen" class="flex items-center focus:outline-none">
                           <span>Projects</span> 
                        <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
                            <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
                        </svg> 
                        </button>  
                    </div>
                    <div>
                        <button class="relative flex items-center focus:outline-none">
                           <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                            </svg> 
                            <span class="absolute top-0 px-1 text-xs text-white bg-red-500 rounded-full -right-1">3</span>
                        </button>     
                    </div>
                    <div class="">
                        <button @click="profileIconOpen = ! profileIconOpen" class=" focus:outline-none">
                            <img src=".././assets/g-logo.png" alt="profile picture" 
                            class="object-cover w-10 h-10 rounded-full"
                            >
                        </button>
                    </div>

                    <!-- settins dropdown  -->
                    <div v-show="settingsOpen" class="absolute z-20 w-64 bg-gray-100 border rounded-lg shadow-lg -left-4 top-14">
                        <div class="px-4 py-5 space-y-2 text-center bg-gray-700 rounded-t-lg">
                            <h2 class="text-xl font-bold text-gray-100">Overview</h2>
                            <p class="text-sm text-gray-300">Dropdown menus for everyone</p>
                        </div>
                      

                        <div class="flex-col py-4">
                            <h2 class="px-4 text-sm font-semibold text-blue-600 uppercase">Key Figure</h2>
                            <a href="" class="block px-4 mt-4 text-sm hover:bg-gray-300">Service Calender</a>
                            <a href="" class="block px-4 mt-4 text-sm hover:bg-gray-300">Knowledge base</a>
                            <a href="" class="block px-4 mt-4 text-sm hover:bg-gray-300">Accounts</a>
                            
                        </div>
                            <div class="p-4 mt-4 border-t border-gray-300">
                                <button class="px-4 py-1 text-sm tracking-tight text-red-100 bg-red-600 rounded-md shadow hover:bg-red-700">Cancel</button>
                            </div>
                    </div>
                    <!-- projects dropdown  -->
                    <div v-show="projectsOpen" class="absolute right-0 z-20 border rounded-lg shadow-lg bg-green-50 w-80 top-14">
                        <div class="px-4 py-5 space-y-3 bg-green-500 rounded-t-lg">
                            <h2 class="text-xl font-bold text-green-100">Overview</h2>
                            <p class="text-sm text-green-100">Dropdown menus for everyone</p>
                            <div class="flex items-center space-x-4">
                                <button class="inline-block px-2 py-1 text-sm tracking-tight text-gray-100 bg-gray-800 rounded focus:outline-none">
                                    Settings
                                </button>
                                <button class="inline-block px-2 py-1 text-sm tracking-tight bg-yellow-400 rounded focus:outline-none">
                                    <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-yellow-700" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                                    </svg>
                                </button>
                            </div>
                        </div>
                      

                        <div class="flex-col px-2 py-4 space-y-2">
                            <div class="flex items-center px-2 py-1 space-x-2 rounded-md hover:bg-gray-300">
                                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M11.49 3.17c-.38-1.56-2.6-1.56-2.98 0a1.532 1.532 0 01-2.286.948c-1.372-.836-2.942.734-2.106 2.106.54.886.061 2.042-.947 2.287-1.561.379-1.561 2.6 0 2.978a1.532 1.532 0 01.947 2.287c-.836 1.372.734 2.942 2.106 2.106a1.532 1.532 0 012.287.947c.379 1.561 2.6 1.561 2.978 0a1.533 1.533 0 012.287-.947c1.372.836 2.942-.734 2.106-2.106a1.533 1.533 0 01.947-2.287c1.561-.379 1.561-2.6 0-2.978a1.532 1.532 0 01-.947-2.287c.836-1.372-.734-2.942-2.106-2.106a1.532 1.532 0 01-2.287-.947zM10 13a3 3 0 100-6 3 3 0 000 6z" clip-rule="evenodd" />
                                </svg>
                                <a href="" class="inline-block text-sm ">Service Calender</a>
                            </div>
                            <div class="flex items-center px-2 py-1 space-x-2 rounded-md hover:bg-gray-300">
                                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M11.49 3.17c-.38-1.56-2.6-1.56-2.98 0a1.532 1.532 0 01-2.286.948c-1.372-.836-2.942.734-2.106 2.106.54.886.061 2.042-.947 2.287-1.561.379-1.561 2.6 0 2.978a1.532 1.532 0 01.947 2.287c-.836 1.372.734 2.942 2.106 2.106a1.532 1.532 0 012.287.947c.379 1.561 2.6 1.561 2.978 0a1.533 1.533 0 012.287-.947c1.372.836 2.942-.734 2.106-2.106a1.533 1.533 0 01.947-2.287c1.561-.379 1.561-2.6 0-2.978a1.532 1.532 0 01-.947-2.287c.836-1.372-.734-2.942-2.106-2.106a1.532 1.532 0 01-2.287-.947zM10 13a3 3 0 100-6 3 3 0 000 6z" clip-rule="evenodd" />
                                </svg>
                                <a href="" class="inline-block text-sm ">App development</a>
                            </div>
                            <div class="flex items-center px-2 py-1 space-x-2 rounded-md hover:bg-gray-300">
                                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M11.49 3.17c-.38-1.56-2.6-1.56-2.98 0a1.532 1.532 0 01-2.286.948c-1.372-.836-2.942.734-2.106 2.106.54.886.061 2.042-.947 2.287-1.561.379-1.561 2.6 0 2.978a1.532 1.532 0 01.947 2.287c-.836 1.372.734 2.942 2.106 2.106a1.532 1.532 0 012.287.947c.379 1.561 2.6 1.561 2.978 0a1.533 1.533 0 012.287-.947c1.372.836 2.942-.734 2.106-2.106a1.533 1.533 0 01.947-2.287c1.561-.379 1.561-2.6 0-2.978a1.532 1.532 0 01-.947-2.287c.836-1.372-.734-2.942-2.106-2.106a1.532 1.532 0 01-2.287-.947zM10 13a3 3 0 100-6 3 3 0 000 6z" clip-rule="evenodd" />
                                </svg>
                                <a href="" class="inline-block text-sm ">Icon Design</a>
                            </div>
                            <div class="flex items-center px-2 py-1 space-x-2 rounded-md hover:bg-gray-300">
                                <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" viewBox="0 0 20 20" fill="currentColor">
                                <path fill-rule="evenodd" d="M11.49 3.17c-.38-1.56-2.6-1.56-2.98 0a1.532 1.532 0 01-2.286.948c-1.372-.836-2.942.734-2.106 2.106.54.886.061 2.042-.947 2.287-1.561.379-1.561 2.6 0 2.978a1.532 1.532 0 01.947 2.287c-.836 1.372.734 2.942 2.106 2.106a1.532 1.532 0 012.287.947c.379 1.561 2.6 1.561 2.978 0a1.533 1.533 0 012.287-.947c1.372.836 2.942-.734 2.106-2.106a1.533 1.533 0 01.947-2.287c1.561-.379 1.561-2.6 0-2.978a1.532 1.532 0 01-.947-2.287c.836-1.372-.734-2.942-2.106-2.106a1.532 1.532 0 01-2.287-.947zM10 13a3 3 0 100-6 3 3 0 000 6z" clip-rule="evenodd" />
                                </svg>
                                <a href="" class="inline-block text-sm ">Service Calender</a>
                            </div>
                            
                        </div>
                            
                    </div>
                    <!-- profile dropdown -->
                    <div v-show="profileIconOpen" class="absolute right-0 z-20 bg-gray-100 border border-gray-700 rounded-lg w-96 top-14">
                        <div class="flex items-center justify-between px-4 py-5 space-x-4 border-b border-gray-500">
                            <img class="object-cover object-center w-10 h-10 border border-gray-500 rounded-full" src=".././assets/g-logo.png" alt="profile pic">
                            <div>
                                <h3 class="font-bold">My Fullname</h3>
                                <p class="mt-1 text-sm text-gray-600">A short profile description</p>
                            </div>
                            <button class="px-4 py-2 text-sm text-gray-100 bg-gray-800 rounded-full hover:bg-gray-900">Logout</button>
                        </div>
                        <div class="p-4">
                            <h2 class="font-medium text-gray-500">Activity</h2>
                            <div class="flex items-center justify-between mt-6 text-sm">
                                <p >Chat</p>
                                <span class="px-2 py-px text-xs font-semibold text-gray-100 bg-gray-800 rounded-full">5</span>
                            </div>
                            <div class="mt-4">
                                <p>Recover Password</p>
                            </div>
                            <h2 class="mt-4 font-medium text-gray-500">My Account</h2>
                        </div>

                        <div class="flex py-4">
                            <div class="flex-col flex-1 p-2 space-y-4 border border-gray-300">
                                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                                </svg>
                                <p class="text-center">Message Inbox</p>
                            </div>
                            <div class="flex-col flex-1 p-2 space-y-4 border border-gray-300">
                                <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                                </svg>
                                <p class="text-center">Message Inbox</p>
                            </div>
                        </div>
                            <div class="flex items-center justify-center p-4 mt-4">
                                <button class="px-6 py-2 tracking-tight text-gray-100 bg-gray-800 rounded-md hover:bg-gray-900">Open Message</button>
                            </div>
                    </div>
                    
                </div>
            </div>
        </div>

        <!-- searchbar here -->
        <div v-show="searchBar" class="absolute z-20 w-screen p-6 mx-auto bg-gray-300 rounded-md shadow-md">
            <!-- <button class="fixed inset-0 w-full h-full bg-gray-400 "></button> -->
            <div class="flex space-x-2">
                <input type="text" name="" id=""
                class="w-full px-4 py-2 text-sm placeholder-gray-400 rounded-md absolu focus:outline-none focus:ring-1 focus:ring-gray-500"
                placeholder="Search"
                >   
                <button class="px-2 text-sm font-medium text-gray-100 bg-gray-800 rounded-md">Search</button>     
            </div>
            <ul class="hidden mt-4 space-y-2 font-medium">
                <li class="px-4 py-1 rounded-lg hover:text-gray-100 hover:bg-blue-500">Item 1</li>
               
            </ul>
        </div>

        <div v-show="navbarOpen" class="absolute z-20 w-3/5 px-2 py-2 mt-2 space-y-4 border border-gray-300 rounded-r-lg shadow bg-gray-50 lg:hidden">
            
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

            <div class="text-sm">
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

                <!-- at the buttom -->
            <div class="flex items-baseline pt-8 space-x-1">
                <button class="w-full py-1 text-sm text-gray-100 bg-gray-800 rounded hover:bg-gray-900">Login</button>
                <button class="w-full py-1 text-sm bg-gray-300 rounded hover:bg-gray-400">Sign Up</button>
            </div>
        </div>
    </nav>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'

export default {
    name: 'NavBar',
   data(){
       return{
        sidebarDropdown: false,
        navbarOpen: false,
        profileIconOpen:false,
        settingsOpen:false,
        projectsOpen:false, 
        searchBar:false
       }
   }
}
</script>
