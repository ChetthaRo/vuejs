<template>
    <div>
        <h1>{{ name }}</h1>
        <v-img v-if="show" height="200" width="200" :src="imgsave">
        </v-img>
        <v-btn color="succcess" @click="show = !show">
            switch
        </v-btn>
        <v-btn color="succcess" @click="alertMessage()">
            alert
        </v-btn>
        <h1>
            Loop zone
        </h1>
        <v-row>
            <v-col cols="3" v-for="(item, index) in items" :key="index">
                <v-card>

                    <v-img height="200px" :src="item.imgset">

                    </v-img>
                    <v-card-title>
                        {{ item.nickname }}
                    </v-card-title>
                    <v-card-actions>
                        <v-btn color="succcess" @click="alertParam(item.nickname)">
                            alertParam
                        </v-btn>

                    </v-card-actions>
                </v-card>
            </v-col>
            <v-col cols="4" class="ma-3">
                <v-text-field name="name" label="ชื่อ" v-model="name">

                </v-text-field>
                <v-btn color="success" @click="alertParam(name)">
                    alertName
                </v-btn>
            </v-col>
            <v-col cols="12">
                <IMGSET :name="name" @alertMessage="alertMessage" />
            </v-col>
        </v-row>
    </div>
</template>

<script>
import IMGSET from '../components/Imgset.vue'
import { EventBus } from '@/EventBus'
export default {
    components: {
        IMGSET
    },
    data() {
        return {
            name: 'Chettha',
            imgsave: require("../assets/rooney.jpg"),
            show: false,
            items: [{
                nickname: 'Pond',
                imgset: require("../assets/rooney.jpg"),
            },
            {
                nickname: 'Jor',
                imgset: require("../assets/manu1.jpg"),
            }
            ]
        }
    },
    mounted() {
        EventBus.$on('prakatt', this.alertParam)
    },
    methods: {
        alertMessage() {
            alert('โย่ว นี่คือเสียงของเด็กฮะ')
        },
        alertParam(itemz) {
            alert('โย่ว' + itemz)
        }
    }
}
</script>

<style></style>