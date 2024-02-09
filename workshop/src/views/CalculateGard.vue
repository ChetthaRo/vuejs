<template>
    <v-container>
        <v-row justify="center">
            <v-col align-self="center">
                <v-card width="350px" height="350px">
                    <v-row justify="center">
                        <v-col>
                            <v-text-field v-model="score" :rules="[rules.required, rules.rulesScore]" label="คะแนน" outlined
                                class="ma-8">

                            </v-text-field>
                            <v-col align-self="center" class="text-center">
                                <v-btn @click="Callculate(score)">
                                    Calculate
                                </v-btn>
                            </v-col>
                        </v-col>
                    </v-row>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            score: 0,

            rules: {
                required: value => !!value || 'Required.',
                rulesScore: v => /^[0-9]+$/.test(v) || 'Only numbers are allowed'
            }
        }
    },

    methods: {
        Callculate(score) {
            console.log(score)

        }
    }
}

</script>

<style></style>