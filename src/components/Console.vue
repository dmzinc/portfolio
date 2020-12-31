<template>
    <div id="console">
        <h1 style="color:white">Console Component</h1>
        <form @submit="classify" class="flex justify-center">
            <input type="text" class="form-control rounded-md w-3/4" v-model="sentence" placeholder="Input Sentence to be Classified" />
        </form>
    </div>
</template>
<script>
export default {
    name: 'Console',
    data(){
        return {
            sentence: ''
        }
    },
    methods:{
        classify(e){
            e.preventDefault();
            console.log(this.sentence);
            this.sentence = '';
        }
    }
}
</script>