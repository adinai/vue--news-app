<template>
<div>
    <h5> Additional links </h5>
    <div class="link-container">
    <p v-for="link in links" :key="link.id">
        <a v-bind:href="link.url">{{ link.name }}</a>
    </p>
    </div>
</div>

</template>


<script>
export default{
    name: "LinkHolder",

    data(){
        return{
            links:[
                {url:'/sport', name: 'Sport News'},
                {url:'/economy', name: 'Economy'},
                {url:'/latest', name: 'Latest News'}],
        }
    },

}

</script>