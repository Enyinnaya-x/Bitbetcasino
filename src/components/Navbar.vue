<script setup>
import { Coins, CircleUserRound, AlignRight, X } from 'lucide-vue-next';
    const openMenu=()=>{
        const hamMenu = document.getElementById("hamMenu");
        const hamBtn = document.getElementById("hamBtn");
        const bitLogo = document.getElementById("bitLogo");
        const coinlogo = document.getElementById("coinlogo");
        hamBtn.classList.add("invisible")
        bitLogo.classList.add("invisible")
        coinlogo.classList.add("invisible")
        hamMenu.classList.remove("hidden");
        hamMenu.classList.add("flex");
        hamMenu.classList.remove("-right-full");
        hamMenu.classList.add("right-0");
    }
    const removeMenu=()=>{
        const hamMenu = document.getElementById("hamMenu");
        const hamBtn = document.getElementById("hamBtn");
        const bitLogo = document.getElementById("bitLogo");
        const coinlogo = document.getElementById("coinlogo");
        hamMenu.classList.add("hidden");
        hamMenu.classList.remove("flex");
        hamMenu.classList.add("-right-full");
        hamMenu.classList.remove("right-0");
        hamBtn.classList.remove("invisible")
        bitLogo.classList.remove("invisible")
        coinlogo.classList.remove("invisible")
    }
</script>

<template>
    <nav class="px-5 text-white justify-between py-1 items-center hidden lg:flex">
        <div class="logodiv flex">
            <Coins />
            <span class="ms-2 font-bold text-xl">Bitbet</span>
        </div>
        <div class="navlinks flex gap-24">
            <p class="font-ligth text-white hover:text-bitGold cursor-pointer">Home</p>
            <p class="font-ligth text-white hover:text-bitGold cursor-pointer">Wallet</p>
            <p class="font-ligth text-white hover:text-bitGold cursor-pointer">Help</p>
            <p class="font-ligth text-white hover:text-bitGold cursor-pointer">Leaderboard</p>
        </div>
        <div class="userdiv h-8 w-8 rounded-full flex bg-white items-center justify-center">
            <CircleUserRound class="text-bitPurple stroke-[2.5] "/>
        </div>
    </nav>
    <!-- Ham Nav  -->
    <nav class="px-5 text-white justify-between py-1 items-center flex lg:hidden">
        <div class="logodiv flex">
            <Coins  id="coinlogo"/>
            <span class="ms-2 font-bold text-xl" id="bitLogo">Bitbet</span>
        </div>
        <AlignRight @click="openMenu()" class="cursor-pointer" id="hamBtn"/>
        <div class="newholder hidden flex-col absolute z-50 top-0 bg-bitGold rounded-lg p-5 items-center gap-3 w-11/12 -right-full mt-3 h-2/4" id="hamMenu">
            <div class="navlinks w-full flex flex-col gap-3 h-full">
                <div class="xbutton flex justify-between">
                    <div class="logodiv flex">
                    <Coins class="text-bitPurple  hover:text-bitRed" />
                    <span class="ms-2 font-bold text-xl text-bitPurple  hover:text-bitRed">Bitbet</span>
                    </div>
                    <X class="text-bitPurple stroke-[2.5]  hover:text-bitRed cursor-pointer" @click="removeMenu"/>
                </div>
                <p class="font-ligth text-bitPurple font-semibold hover:text-bitRed cursor-pointer">Home</p>
                <p class="font-ligth text-bitPurple font-semibold hover:text-bitRed cursor-pointer">Wallet</p>
                <p class="font-ligth text-bitPurple font-semibold hover:text-bitRed cursor-pointer">Help</p>
                <p class="font-ligth text-bitPurple font-semibold hover:text-bitRed cursor-pointer">Leaderboard</p>
            </div>
            <div class="userdiv h-8 w-8 rounded-full flex bg-white items-center justify-center">
                <CircleUserRound class="text-bitPurple stroke-[2.5] "/>
            </div>
        </div>
    </nav>
    <hr>
</template>