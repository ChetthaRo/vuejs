<template>
    <div>
        <v-row>
            <v-col cols="12">
                <v-btn color="success" @click="newItem()">newItem</v-btn>
            </v-col>
            <v-col cols="3" v-for="(item, index) in dataUsers" :key="index">
                <v-card>
                    <v-img height="250" src="../assets/rooney.jpg" />
                    <v-card-title>
                        <span>User Name: </span>{{ item.username }}
                    </v-card-title>
                    <v-card-subtitle>
                        <span>Email User: </span>{{ item.email }}
                    </v-card-subtitle>
                    <v-card-title>
                        <span>Role User: </span>{{ item.role }}
                    </v-card-title>
                    <v-card-actions>
                        <v-btn color="success" @click="editItem(item)">Edit</v-btn>
                    </v-card-actions>
                    <v-card-actions>
                        <v-btn color="error" @click="deleteData(item)">Delete</v-btn>
                    </v-card-actions>
                </v-card>
            </v-col>
        </v-row>
        <v-dialog v-model="dialogEdit" max-width="500px">
            <v-card>
                <v-card-title>
                    {{ savemode }}
                </v-card-title>
                <v-card-text>
                    <v-row>
                        <v-col cols="6">
                            <v-text-field name="username" label="Username" v-model="postData.username">
                            </v-text-field>
                        </v-col>
                        <v-col cols="6">
                            <v-text-field name="password" label="password" v-model="postData.password">
                            </v-text-field>
                        </v-col>
                        <v-col cols="6">
                            <v-text-field name="email" label="Email" v-model="postData.email">
                            </v-text-field>
                        </v-col>
                        <v-col cols="6">
                            <v-text-field name="role" label="Role" v-model="postData.role">
                            </v-text-field>
                        </v-col>
                    </v-row>
                </v-card-text>
                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn text color="error" @click="closeItem()">cancel</v-btn>
                    <v-btn text color="info" @click="saveSelect()">save</v-btn>
                </v-card-actions>
            </v-card>
        </v-dialog>

    </div>
</template>

<script>
export default {
    data() {
        return {
            dataUsers: [],
            id: '',
            dialogEdit: false,
            postData: {
                username: '',
                password: '',
                email: '',
                role: '',
            },
            postDataDefault: {
                username: '',
                email: '',
                role: '',
                password: '',
            },
        }
    },
    computed: {
        savemode() {
            console.log(this.id)
            return this.id == '' ? 'New Item' : 'Edit Item'
        }
    },
    created() {
        this.getData()
    },
    methods: {
        newItem() {
            this.id = ''
            this.postData = { ...this.postDataDefault }
            this.dialogEdit = true
        },
        editItem(item) {
            this.id = item._id
            this.postData = item
            this.dialogEdit = true
        },
        closeItem() {
            this.id = ''
            this.postData = { ...this.postDataDefault }
            this.dialogEdit = false
        },
        saveSelect() {
            if (this.id != '') {
                console.log(this.id)
                this.savePutData()
            } else this.savePostData()

        },  

        getData() {
            this.axios.get('http://localhost:3000/api/users').then((res) => {
                console.log(res.data)
                this.dataUsers = res.data.data;

            })
        },
        async savePostData() {
            try {
                const { data } = await this.axios.post('http://localhost:3000/api/register', this.postData)
                alert(data.message)
                this.getData()
                this.closeItem()
            } catch (error) {
                alert('พัง')

            }
        },
        async savePutData() {
            try {
                const { data } = await this.axios.put('http://localhost:3000/api/update/' + this.id, this.postData)
                console.log(this.id)
                alert(data.message)
                this.getData()
                this.closeItem()
            } catch (error) {
                alert('พัง')

            }
        },
        async deleteData(item) {
            if (confirm('ยืนยันการลบ')) {

                try {
                    const { data } = await this.axios.delete('http://localhost:3000/api/delete/' + item._id,)
                    alert(data.message)
                    this.getData()
                    this.closeItem()
                } catch (error) {
                    alert('พัง')

                }
            } else console.log('cancel')
        }
    }

}
</script>

<style></style>