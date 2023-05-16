<template>
    <div>
        <div>
            <nav class="nav bg-[#152856] w-[150px] text-white h-[100vh] flex flex-col items-center fixed ">
                <ul class="w-full p-0 m-0 flex flex-col items-center h-full list-none">
                    <li class="text-[30px] font-medium p-[10px]">日曜日</li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center transition ease-in-out delay-30">
                        <a href="#">Home</a>
                    </li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center transition ease-in-out delay-30">
                        About</li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center transition ease-in-out delay-30">
                        Sign In</li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center mt-auto transition ease-in-out delay-30">
                        Setting</li>
                </ul>
            </nav>
        </div>

        <div>
            <slot />
        </div>

        <footer class="ml-[150px] text-center text-slate-50 font-medium mt-full">
            <div class="footer p-1 bg-[#162444]">
                <p>
                   Copyright 2023 © Ananda Arsya Sabili 
                </p>
            </div>
        </footer>
    </div>
</template>