<template>
    <div class="about">
        <h1>{{ title}}</h1>
        <h1>Application desctiption : {{ msg }}</h1>
        <h1>Web-version : {{ web_version}}</h1>
        <h1>BackEnd API Version : {{backendData}}</h1>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue';
    import axios from "axios";
    export default  Vue.extend({
        name: "AboutComponent",
        props: {
            msg: String,
            ip : String,
            backend: String,
        },
        data() {
            return {
                title: process.env.VUE_APP_TITLE,
                web_version: process.env.VUE_APP_VERSION,
                backendData: this.backend,
            }
        },
        mounted() {
            axios({ method: "GET", "url": "http://bootapp-spring-boot-docker.172.27.220.195.nip.io/info" }).then(result => {
                this.backendData = result.data.app.version;
                console.log(result.data.app.version);
            }, error => {

                console.error(error);
            });
    }});
</script>


<style scoped>

</style>
