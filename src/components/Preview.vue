<template>
    <div class="border w-[80%] flex justify-between items-center rounded-t-lg bg-white text-black font-medium pr-">
        <p class="pl-2 font-medium flex items-center">Your terminal!</p>
        <div class="flex space-x-2 items-center pr-2">

            <svg class="w-3 h-3 text-gray-800 hover:rounded-full hover:bg-blue-500 hover:p-0.5 hover:text-white cursor-pointer" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 4H4m0 0v4m0-4 5 5m7-5h4m0 0v4m0-4-5 5M8 20H4m0 0v-4m0 4 5-5m7 5h4m0 0v-4m0 4-5-5"/>
            </svg>
            <svg class="w-4 h-4 text-gray-800 hover:rounded-full hover:bg-red-500 hover:p-1 hover:text-white cursor-pointer" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18 17.94 6M18 18 6.06 6"/>
            </svg>
        </div>
    </div>    
    
     <div class="p-5 w-[80%] h-[55%] text-center bg-[#282C34] border text-white rounded-b-lg font-mono">
        <div class="p-10 border-green-500 border-2 h-[70%]">
            <h1 class="text-lg font-medium"><span class="font-medium text-green-500">Your Name</span> / <span class="font-medium text-gray-300">@yourname</span></h1>
            <ul class="mt-8 space-y-1">
                <li>
                    <p><strong class="mr-2">npm:</strong>https://npmjs.com/<span class="text-red-500">~npmusername</span></p>
                </li>
                <li>
                    <p><strong class="mr-2">GitHub:</strong>https://github.com/<span class="text-green-400">githubtag</span></p>
                </li>
                <li>
                    <p><strong class="mr-2">LinkedIn:</strong>https://www.linkedin.com/in/<span class="text-blue-400">linkedinurl</span></p>
                </li>
                <li>
                    <p><strong class="mr-2">Wakatime:</strong> https://wakatime.com/<span class="text-gray-400">wakatimename</span></p>
                </li>
            </ul>

            <p class="mt-12"><strong class="m-2">Card:</strong><span class="text-red-600">npx</span><span class="ml-2 ">packagename</span></p>
        </div>

        <div class="flex mt-8 ml-20">
            <p class="font-bold text-blue-400 ">cmd/ctrl + click</p>
        </div>
        <div class="flex mt-5">
            <p class="font-bold text-gray-400 "><span class="font-bold text-green-500">?</span> What do you want to do? <span class="text-gray-200">(Use arrow keys)</span></p>
        </div>
        <div class="flex">
            <ul class="ml-8">
                <li>
                    <p class="text-gray-100 font-bold">Send me an email?</p>
                </li>
                <li>
                    <p class="text-left text-gray-200">Just quit.</p>
                </li>
            </ul>
        </div>

    </div>

</template>

<style scoped>

</style>