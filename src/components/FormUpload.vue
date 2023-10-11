
<template>
    <div>
        <h2>Upload file</h2>
        <form @submit.prevent="submit">
            <input type="file" @change="setFile" />
            <button type="submit">Submit</button>
        </form>
        <div class="stt">{{ stt }}</div>
    </div>
</template>
<script lang="ts">
import e from 'express';
import { defineComponent, onMounted, reactive, toRef } from 'vue'

export default defineComponent({

    setup() {
        let file: any = {};
        const state = reactive({
            stt: '',
        })
        // let stt: any = '';
        const setFile = function (e: any) {
            file = e.target.files[0]
        }
        const submit = async function () {
            console.log(file)
            console.log(process.env.BE_URL)
            const form = new FormData();
            form.append('file', file);

            const res = await fetch(`${process.env.BE_URL}`, {
                method: 'post',
                body: form
            });

            if (!res.ok) {
                alert(state.stt = 'Error')
            } else {
                alert(state.stt = 'Success')
            }
            // reset value
            file = {}
            state.stt = ''
        }

        return {
            submit, setFile,
            ...toRef(state)
        }
    }

})
</script>
<style scoped>
.stt {
    color: rgb(32, 198, 57);
}
</style>
