<template>
    <div class="min-h-screen bg-fixed flex items-center justify-center">
        <div class="container">
            <div class="mx-auto box-content p-5">
                <h1 class="text-center text-4xl font-sans text-white animate__animated animate__bounce">REAL TIME SENTIMENT ANALYSIS</h1>
                <div class="flex justify-center m-3 p-2">
                    <b-button @click="showComponent=true" class="animate-bounce" variant="dark">
                        <b-icon icon="arrow-down-circle-fill" aria-hidden="true"></b-icon>
                    </b-button>
                </div>
                <div v-show="showComponent" class="flex justify-center m-3 p-2 space-x-10">
                    <b-button v-show="!showConsole" v-b-popover.hover.left="'Handling Real Time Twitter Data'" @click="toggleStream" class="">
                        <b-icon icon="twitter" aria-hidden="true"></b-icon>
                    </b-button>
                    <b-button v-show="!showStream" v-b-popover.hover.right="'Classify a sentence using pretrained model'" @click="toggleConsole" class="">
                        <b-icon icon="terminal-fill" aria-hidden="true"></b-icon>
                    </b-button>
                </div>
            </div>
            <div class="container">
                <Stream v-show="showStream" />
                <Console v-show="showConsole" />
            </div>
        </div>
    </div>
</template>
<script>
import Stream from '@/components/Stream';
import Console from '@/components/Console';

export default {
    name: 'Main',
    data(){
        return{
            showStream: false,
            showConsole: false,
            showComponent: false
        }
    },
    methods:{
        toggleStream(){
            this.showStream = !this.showStream;
            this.showConsole = false;
        },
        toggleConsole(){
            this.showConsole = !this.showConsole;
            this.showStream = false
        },
    },
    components:{
        Stream,
        Console
    }
}
</script>
<style scoped>
.bg-fixed{
    background-image: url('~@/assets/images/bg.jpg');
    background-size: cover;
}
.container{
    transition: height 2s;
}
</style>