<template>
    <form id="app" @submit="checkForm" novalidate="true">
        <p v-if="errors.length">
            <ul>
                <li v-for="(error, index) in errors" :key="index">{{ error }}</li>
            </ul>
        </p>
        <p>バリデーションテスト</p>
        <p>
            <input v-model="weapons" type="text" name="weapons">
                備考 <br/>
            <textarea v-model="shields" type="text" name="shields">備考</textarea>                
        </p>
        <p>
            <input type="submit" value="Submit">
        </p>
    </form>
</template>

<script>

export default {
    data(){
        return {
            errors: [],
            weapons: [],
            shields: [],
        }
    },
    methods:{
        checkForm(e) {
            e.preventDefault();
            this.errors = [];
            console.log('Method呼び出し')

            if (!/^\d{3}-?\d{4}$/.test(this.weapons)) {
                this.errors.push('入力不可の文字が含まれています');
            }
            if (!this.errors.length) {
                return true;
            }
        }
    }
}
</script>