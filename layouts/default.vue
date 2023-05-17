<template>
    <div>
        <div>
            <nav class="nav bg-[#152856] w-[150px] text-white h-[100vh] flex flex-col items-center fixed">
                <ul class="w-full p-0 m-0 flex flex-col items-center h-full list-none">
                    <li class="text-[30px] font-medium p-[10px]">日曜日</li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center transition ease-in-out delay-30">
                        <NuxtLink to="/">
                            <div class="w-full h-full">
                                Home
                            </div>
                        </NuxtLink>
                    </li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center transition ease-in-out delay-30">
                        <NuxtLink to="/about">
                            <div class="w-full h-full">
                                About
                            </div>
                        </NuxtLink>
                    </li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center transition ease-in-out delay-30">
                        <NuxtLink to="/signin">
                            <div class="w-full h-full">
                                Sign-In
                            </div>
                        </NuxtLink>
                    </li>
                    <li
                        class="w-[100%] p-[10px] hover:bg-[#121d38] hover:font-medium text-center mt-auto transition ease-in-out delay-30">
                        <NuxtLink to="/settingu">
                            <div class="w-full h-full">
                                Settings
                            </div>
                        </NuxtLink>
                    </li>
                </ul>
            </nav>
        </div>

        <div>
            <slot></slot>
        </div>

        <footer class=" text-center text-slate-50 font-medium mt-full bottom-0 w-[100%] z-0">
            <div class="footer p-1 bg-[#162444]">
                <p>
                    Copyright 2023 © Ananda Arsya
                </p>
            </div>
        </footer>
</div></template>