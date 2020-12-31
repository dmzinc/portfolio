<template>
    <div id="stream">
        <section class="controller">
            <ul class="space-y-6">
                <li>
                    <a @click="initStream=true" class="btn btn-primary">Create New Stream</a>
                </li>
                <li>
                    <a @click="viewPrevious" class="btn btn-primary">View Previous Stream</a>
                </li>
            </ul>
        </section>
        <section v-show="initStream">
            <form class="flex justify-center" @submit="createStream">
                <input type="text" v-model="keyword" class="form-control rounded-md w-50" placeholder="Stream Keyword" />
            </form>
        </section>
        <section v-show="showDirectory">
            
        </section>
    </div>
</template>
<script>
export default {
    name: 'Stream',
    data(){
        return {
            keyword:'',
            initStream: false,
            showDirectory: false
        }
    },
    methods:{
        createStream(event){
            event.preventDefault();
            console.log(this.keyword)
            this.keyword = '';
        },
        async viewPrevious(){
            this.initStream = false;
          const data = await fetch('https://jsonplaceholder.typicode.com/todos?_limit=5')
            .then(res => res.json())
            .catch(err => console.error(err));
            console.log(data)
        }
    }
}
</script>