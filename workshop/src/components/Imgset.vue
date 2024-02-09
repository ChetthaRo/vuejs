<template>
    <div class="img">
        <h1>{{ name }}</h1>
        <img src="../assets/profile.jpg" />
        <v-btn color="success" @click="callMain()">
            callMain
        </v-btn>
        <v-text-field name="childname" label="childname" id="childname" v-model="childname">
        </v-text-field>
        <v-btn color="success" @click="callEventParam()">
            callEventParam

        </v-btn>
    </div>
</template>

<script>
import { EventBus } from '@/EventBus';
export default {
    props: ['name'],
    data() {
        return {
            childname: ''
        }
    },
    methods: {
        callMain() {
            this.$emit('alertMessage')
        },
        callEventParam() {
            EventBus.$emit('prakatt', this.childname)
        }
    },
}
</script>

<style>
* {
    margin: 0px;
    padding: 0px;
    box-sizing: border-box;
}

/* .img {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #252d5d;
} */

.img img {
    height: 200px !important;
    width: 200px !important;
    border-radius: 50%;
    justify-content: center;
    align-content: center;
}
</style>