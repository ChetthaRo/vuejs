<template>
    <div class="calculate-grade pt-10">
        <v-form ref="form" @submit.prevent="formValidate">
            <v-row justify="center">
                <v-col cols="12" align-self="center" class="test">
                    <v-card width="540px" height="400px">
                        <v-row>
                            <v-col>
                                <v-row>
                                    <v-col cols="6">
                                        <v-text-field v-model="firstName" label="ชื่อ" outlined class="ma-8">
                                        </v-text-field>
                                    </v-col>
                                    <v-col cols="6">
                                        <v-text-field v-model="lastName" label="นามสกุล" outlined class="ma-8">
                                        </v-text-field>
                                    </v-col>
                                </v-row>
                                <v-text-field v-model="score" :rules="ScoreRules" label="คะแนน" outlined class="ma-8">
                                </v-text-field>
                                <v-col align-self="center" class="text-center">
                                    <v-btn @click="formValidate(score)">
                                        Calculate
                                    </v-btn>
                                </v-col>
                            </v-col>

                        </v-row>

                    </v-card>
                </v-col>
                <v-col col="12">
                    <v-card class="pt-10">
                        <Tableset :headers="headers" :dataStudents="dataStudent" />
                        <!-- <v-data-table :loading="loading" :headers="headers" :items="dataStudent"
                            class="cs-pointer text-cente" hide-default-footer disable-pagination>
                            <template #[`item.description`]="{ value }">
                                <div style="max-width: 425px">
                                    <v-row class="justify-center box_limit">
                                        {{ value }}
                                    </v-row>
                                </div>
                            </template>
                            <template #[`item.status`]="{ item }">
                                <v-row class="justify-center">
                                    <v-switch v-model="item.status" readonly @click.stop.prevent="() => checkstatus(item)">
                                    </v-switch>
                                </v-row>
                            </template>
                            <template #[`item.price`]="{ item }">
                                {{ item.price }} บาท
                            </template>
                        </v-data-table> -->
                    </v-card>
                </v-col>
            </v-row>
        </v-form>
    </div>
</template>

<script>
import Swal from 'sweetalert2'
import Tableset from '../components/Tableset.vue'
export default {
    components: {
        Tableset
    },
    data() {
        return {
            score: 0,
            firstName: '',
            lastName: '',
            dataStudent: [],
            ScoreRules: [
                (v) => !!v || 'กรุณากรอกข้อมูล',
                (v) => /^[0-9]*$/.test(v) || 'กรุณากรอกข้อมูลให้ถูกต้อง',
            ],
            headers: [
                {
                    text: 'ชื่อ-นามสกุล',
                    value: 'name',
                    key: 'name',
                    align: 'center',
                    class: 'primary--text',
                    width: 180,
                },
                {
                    text: 'คะแนน',
                    value: 'score',
                    key: 'score',
                    align: 'center',
                    class: 'primary--text',
                    width: 180,
                },
                {
                    text: 'เกรด',
                    value: 'grade',
                    key: 'grade',
                    align: 'center',
                    class: 'primary--text',
                    width: 180,
                },

            ],
        }
    },

    methods: {
        formValidate(score) {
            console.log('in form')
            console.log(score)

            if (isNaN(score)) {
                return Swal.fire({
                    title: "Good job!",
                    text: "กรอกข้อมูลไม่ถูกต้อง",
                    icon: "error"
                });
            }
            else if (score < 0 || score > 100) {
                return Swal.fire({
                    title: "Good job!",
                    text: "กรุณากรอกคะแนน ให้อยู่ในช่วง 0-100",
                    icon: "error"
                });
            }
            else if (score >= 80 && score <= 100) {
                this.grade = "A"
            }
            else if (score >= 70 && score <= 79) {
                this.grade = "B"
            }
            else if (score >= 60 && score <= 69) {
                this.grade = "C"
            }
            else if (score >= 50 && score <= 59) {
                this.grade = "D"
            }
            else {
                this.grade = "F"
            }


            let newData = {
                name: `${this.firstName} ${this.lastName}`,
                score: this.score,
                grade: this.grade
            }
            this.dataStudent.push(newData)
            console.log('newData :', newData)
            console.log('dataStudent :', this.dataStudent)
            return Swal.fire({
                title: "Good job!",
                icon: "success",
                text: `${this.firstName} ${this.lastName} ได้เกรด ${this.grade}`,

            });
        }
    }
}

</script>

<style>
.calculate-grade {
    display: flex;
    justify-content: center;
    align-items: center;

}

.data-input {
    align-items: center;
}

.test {
    text-align: -webkit-center;
}
</style>