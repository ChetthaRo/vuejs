<template>
    <v-container class="bg">

        <v-row>

            <v-col class="text-center" cols="6">
                <v-card color="#BBDEFB" class="pt-10">
                    <v-row>

                        <v-col cols="6">
                            <IMGSET />
                        </v-col>

                        <v-col class="mb-4 align-self-center " cols="6" style="color:#0D47A1;">
                            <div class="dataProfile">
                                <h2>
                                    ชื่อ-นามสกุล : เชษฐา รอดทอง
                                </h2>
                                <h2>
                                    ชื่อเล่น : ปอนด์
                                </h2>
                                <h2>
                                    อายุ : 24 </h2>
                            </div>
                        </v-col>
                        <v-col cols="6">
                            <div class="bg  ">
                                <img src="../assets/ku_color_big.png" />
                            </div>
                        </v-col>
                        <v-col cols="6" class="mb-4 align-self-center" style="color: #0D47A1;">
                            <div class="dataProfile">
                                <h2>
                                    2018-2022 :
                                </h2>
                                <h2>
                                    มหาวิทยาลัย เกษตรศาสตร์ วิทยาเขตกำแพงแสน
                                    สาขาวิทยาการคอมพิวเตอร์ คณะศิลปศาสตร์ และ
                                    วิทยาศาสตร์
                                </h2>
                                <h2>
                                </h2>
                            </div>
                        </v-col>
                    </v-row>

                </v-card>
            </v-col>

            <v-col cols="6" class="text-center">
                <v-card color="#FFF9C4" height="97.5%">
                    <v-row>

                        <v-col cols="6">
                            <div class="bg  ">
                                <img src="../assets/manu1.jpg" />
                            </div>
                        </v-col>
                        <v-col cols="6" class="mb-4 align-self-center" style="color: #D50000;">
                            <div class="dataProfile">
                                <h2>
                                    สโมสรฟุตบอลที่ชอบ :
                                </h2>
                                <h2>
                                    Manchester united
                                </h2>
                                <h2>
                                </h2>
                            </div>
                        </v-col>
                        <v-col cols="6">
                            <div class="bg  ">
                                <img src="../assets/rooney.jpg" />
                            </div>
                        </v-col>
                        <v-col cols="6" class="mb-4 align-self-center" style="color: #D50000;">
                            <div class="dataProfile">
                                <h2>
                                    นักฟุตบอลที่ชื่นชอบที่สุด :
                                </h2>
                                <h2>
                                    เวย์น มาร์ก รูนีย์ (อังกฤษ: Wayne Mark Rooney; เกิด 24 ตุลาคม ค.ศ. 1985)
                                    เป็นอดีตนักฟุตบอลชาวอังกฤษ โดยเล่นในตำแหน่งกองหน้า
                                </h2>
                                <h2>
                                </h2>
                            </div>
                        </v-col>
                    </v-row>
                </v-card>

            </v-col>

            <v-col cols="6">
                <v-card color="#E0F2F1">
                    <v-col class="mb-5" cols="12">
                        <h2 class="headline font-weight-bold mb-3">
                            สิ่งที่ชอบ
                        </h2>
                        <p class="subheading font-weight-regular">
                            <span class="mdi mdi-emoticon-excited-outline"></span>
                            ชอบดูการ์ตูน, ดูหนัง, ฟังเพลง
                        </p>
                        <p class="subheading font-weight-regular">
                            <span class="mdi mdi-emoticon-excited-outline"></span>
                            ชอบเตะบอล

                        </p>
                        <p class="subheading font-weight-regular">
                            <span class="mdi mdi-emoticon-excited-outline"></span>
                            ชอบเที่ยว

                        </p>

                    </v-col>
                </v-card>
            </v-col>

            <v-col cols="6">
                <v-card color="#FFCDD2">
                    <v-col class="mb-5" cols="12">
                        <h2 class="headline font-weight-bold mb-3">
                            สิ่งที่ไม่ชอบ
                        </h2>
                        <p class="subheading font-weight-regular">
                            <span class="mdi mdi-emoticon-frown-outline"></span>
                            สัตว์เลื่อยคลาน
                        </p>
                        <p class="subheading font-weight-regular">
                            <span class="mdi mdi-emoticon-frown-outline"></span>
                            เป็นคนกลัวความสูง

                        </p>
                        <p class="subheading font-weight-regular">
                            <span class="mdi mdi-emoticon-frown-outline"></span>
                            เป็นคนกลัวผี

                        </p>


                    </v-col>
                </v-card>
            </v-col>



        </v-row>
    </v-container>
</template>

<script>
import IMGSET from '../components/Imgset.vue'
export default {

    components: {
        IMGSET
    },
    variants: ['elevated', 'flat', 'tonal', 'outlined']

}

</script>


<style>
.img img {
    height: 300px;
    width: 300px;
    border-radius: 50%;
    justify-content: center;
    align-content: center;
}

.dataProfile {
    text-align: justify;
}

.bg img {
    height: 200px !important;
    width: 200px !important;
    border-radius: 50%;
    justify-content: center;
    align-content: center;
}
</style>