<script setup>
import { ref } from 'vue'

const msg = ref("Hello World")
const rawHtml = ref("You See Me?")
const disabled = ref(false)

function warnDisabled() {
  disabled.value = true
  setTimeout(() => {
    disabled.value = false
  }, 1700)
}

const x = ref(0)

function onMousemove(e) {
  x.value = e.clientX
}

</script>

<template>
    <center>
    <div>
        <h1>{{ msg }}</h1>
        <p><span v-html="rawHtml"></span></p>
        <p><a v-nama:[eventName]="doSomething" style="color: red;">Jerry Satrio Wibowo</a></p>
        <a v-kelas:[attributeName]="url" style="color: red;">XI RPL 2</a>
        <form @submit.prevent="onSubmit">Rekayasa Perangkat Lunak</form>

        <div>Jenis Kelamin :</div>
        <input type="radio" value="Laki-Laki" v-model="picked">
        <label for="laki-laki">Laki-Laki</label>
        <input type="radio" value="Perempuan" v-model="picked">
        <label for="perempuan">Perempuan</label>

        <p><input v-email="message" placeholder="Email"></p>
        <p><input v-password="message" placeholder="Password"></p>

        <p><p><span>Kotak Saran :</span></p></p>
        <p style="white-space: pre-line;"></p>
        <textarea v-saran="message" placeholder="Saran Dan Masukan"></textarea>
        
        <p><button :disabled="isButtonDisabled" style="background-color: green;">Kirim</button></p>

        <div :class="{ shake: disabled }">
        <button @click="warnDisabled">Tekan</button>
        <span v-if="disabled">Ini Tombol Disable</span>
    </div>

    <div @mousemove="onMousemove" :style="{ backgroundColor: `hsl(${x}, 80%, 50%)` }" class="movearea">
    <p>Pindahin Cursor ...</p>
    <p>x : {{ x }}</p>
        </div>
    </div>
</center>
</template>