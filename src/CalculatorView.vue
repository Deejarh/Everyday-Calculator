<template>
    <div class=" card">
        <div class=" displayArea"> <p>{{ inputedVal }}</p>
        </div>
        <div class="">
            <div class=" flex items-center justify-between">
                <button  @click="clear" class=" text-card">c</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('/')" class="text-card">÷</button>
            </div>
            <div class=" flex items-center justify-between mt-4">
                <button :disabled="inputedVal.length > 15" @click="clickedValue('7')" class=" text-card">7</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('8')" class="text-card">8</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('9')" class="text-card">9</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('*')" class="text-card">x</button>
            </div>
            <div class=" flex items-center justify-between mt-4">
                <button :disabled="inputedVal.length > 15" @click="clickedValue('4')" class="text-card">4</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('5')" class="text-card">5</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('6')" class="text-card">6</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('-')" class="text-card">-</button>
            </div>
            <div class=" flex items-center justify-between mt-4">
                <button :disabled="inputedVal.length > 15" @click="clickedValue('1')" class=" text-card">1</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('2')" class="text-card">2</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('3')" class="text-card">3</button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('+')" class="text-card">+</button>
            </div>
            <div class=" flex items-center justify-between mt-4">
                <button :disabled="inputedVal.length > 15" @click="clickedValue('0')" class=" text-card">0</button>
                <button  class="w-16 h-16 md:w-20 md:h-20 "></button>
                <button :disabled="inputedVal.length > 15" @click="clickedValue('.')" class="text-card ">.</button>
                <button  @click="calculate" class="text-card">=</button>
            </div>
        
        </div>

    </div>
</template>

<script setup>
import { ref } from "vue";
const inputedVal = ref('')


const clear = () => {
    inputedVal.value = ''
}
const clickedValue = (value) => {


    if (inputedVal.value === 0){
        inputedVal.value = arg
    } else {
    inputedVal.value += value
}

}
const calculate = () => {
    inputedVal.value = eval(inputedVal.value)
    
}

</script>

<style  scoped>
.card {
    @apply bg-gray-700 w-full  max-w-[450px] mx-2 md:mx-0  rounded-lg border border-gray-600 text-white p-8 shadow-xl overflow-hidden overscroll-none
}
.displayArea {
    @apply bg-green-800 p-5 rounded-md h-20 mb-10 font-light  flex items-center justify-end text-4xl
}
.text-card {
    @apply bg-gray-900 w-16 h-16 md:w-20 md:h-20 rounded-xl flex  items-center justify-center  font-normal text-4xl cursor-pointer  hover:opacity-90 hover:bg-green-600
}
</style>