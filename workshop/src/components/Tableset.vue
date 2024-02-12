<template>
    <v-card class="pt-10">
        <v-data-table :headers="headers" :items="dataStudents" class="cs-pointer text-cente" hide-default-footer
            disable-pagination>
        </v-data-table>
    </v-card>
</template>

<script>
export default {
    props: { headers: Array, dataStudents: Array }
}
</script>

<style></style>