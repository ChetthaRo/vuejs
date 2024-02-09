<template>
    <v-container class="bg-text">

        <v-row>


            <v-row>
                <v-col class="mb-4 " cols="6">
                    <v-col cols="12">
                        <IMGSET />
                    </v-col>
                    <h1 class="display-1 font-weight-bold mb-3  ">
                        เชษฐา รอดทอง
                    </h1>
                    <h1 class="display-1 font-weight-bold mb-3">
                        ปอนด์
                    </h1>

                    <p class="display-1 font-weight-regular">
                        มหาวิทยาลัยเกษตรศาสตร์ วิทยาเขตกำแพงแสน สาขาวิทยาการคอมพิวเตอร์

                    </p>
                </v-col>

                <v-col cols="6" align-self="center">
                    <v-col class="mb-5">
                        <h2 class="display-1 font-weight-bold mb-3">
                            ทีมฟุตบอลที่เชียร์
                        </h2>


                        <div class="img text-center">
                            <img src="../assets/manu1.jpg" />
                        </div>
                        <p class="display-1 font-weight-bold mb-3 img text-center pt-5">
                            Manchester united

                        </p>



                    </v-col>

                </v-col>

                <v-col cols="6">
                    <v-col class="mb-5" cols="12">
                        <h2 class="display-1  font-weight-bold mb-3">
                            สิ่งที่ชอบ
                        </h2>
                        <v-chip class="ma-2" color="green" text-color="white" large width=160px>
                            ดูหนัง
                            <v-icon right>
                                mdi mdi-emoticon-excited-outline
                            </v-icon>
                        </v-chip>

                        <v-chip class="ma-2" color="green" text-color="white" large>
                            ฟังเพลง
                            <v-icon right>
                                mdi mdi-emoticon-excited-outline
                            </v-icon>
                        </v-chip>
                        <v-chip class="ma-2" color="green" text-color="white" large>
                            เล่นเกม
                            <v-icon right>
                                mdi mdi-emoticon-excited-outline
                            </v-icon>
                        </v-chip>
                        <v-chip class="ma-2" color="green" text-color="white" large>
                            เตะบอล
                            <v-icon right>
                                mdi mdi-emoticon-excited-outline
                            </v-icon>
                        </v-chip>
                        <v-chip class="ma-2" color="green" text-color="white" large>
                            ชอบกินโกโก้ปั่น
                            <v-icon right>
                                mdi mdi-emoticon-excited-outline
                            </v-icon>
                        </v-chip>


                    </v-col>
                </v-col>

                <v-col cols="6">
                    <v-col class="mb-5" cols="12">
                        <h2 class="display-1 font-weight-bold mb-3">
                            สิ่งที่ไม่ชอบ
                        </h2>

                        <v-chip class="ma-2" color="red" text-color="white" large width=160px>
                            ไม่ชอบความสูงเป็นคนกลัวความสูง
                            <v-icon right>
                                mdi mdi-emoticon-frown-outline
                            </v-icon>
                        </v-chip>
                        <v-chip class="ma-2" color="red" text-color="white" large>
                            สัวต์เลื้อยคลาน
                            <v-icon right>
                                mdi mdi-emoticon-frown-outline
                            </v-icon>
                        </v-chip>
                        <v-chip class="ma-2" color="red" text-color="white" large>
                            แมลงสาบ
                            <v-icon right>
                                mdi mdi-emoticon-frown-outline
                            </v-icon>
                        </v-chip>



                    </v-col>
                </v-col>

            </v-row>





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
.bg-text {
    background-color: rgb(0, 0, 0);
    /* Fallback color */
    background-color: rgba(0, 0, 0, 0.4);
    /* Black w/opacity/see-through */
    color: white;
    font-weight: bold;
    border: 3px solid #f1f1f1;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
    width: 80%;
    padding: 20px;
    text-align: center;
}
</style>