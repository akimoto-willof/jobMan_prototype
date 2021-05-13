<template>
  <div>
      <button @click="onAction">カレンダー</button>
      <div v-show="active">
            <datepicker
                :language="ja"
                :format="DatePickerFormat"></datepicker>
      </div>
  </div>

</template>
<script>
import Datepicker from "vuejs-datepicker";
import { ja } from 'vuejs-datepicker/dist/locale'

export default {
    name: 'calendar',
    components: {
        Datepicker
    },
    data() {
        return {
            active: true,
            ja: ja,
            DatePickerFormat: 'yyyy年MM月dd日'
        }
    },
    methods: {
        onAction(){
            if(this.active) {
                this.active = false
            } else {
                this.active = true
            }
        }
    }
}
</script>

<style>

</style>
