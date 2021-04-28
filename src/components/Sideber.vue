<template>
<div id="sideber">
    <button @click="trrigerBtn">>></button>

    <transition>
        <div v-show="button">
            <div class="top">
                <h2>複数条件検索</h2>
                <h3>条件クリア</h3>
            </div>
            <ul>
                <li>
                    <div>求人ID（10桁数字）</div>
                    <input type="text">
                </li>
                <li>
                    <div>事業部</div>
                </li>
                <li>
                    <div>所課</div>
                </li>
                <li>
                    <div>事業担当</div>
                </li>
                <li>
                    <div>雇用形態</div>
                </li>
                <li>
                    <div>案件種別</div>
                </li>
                <li>
                    <div>ステータス</div>
                </li>
                <li>
                    <div>掲載可否</div>
                </li>
                <li>
                    <div>人選期日</div>
                </li>
                <li>
                    <div>開始日</div>
                </li>
                <li>
                    <div>性別</div>
                </li>        
            </ul>
        </div>
    </transition>

</div>
</template>

<script>
export default {
    name: 'Sideber',
    data() {
        return{
            button: false
        }
    },
    methods:{
        trrigerBtn (){
            this.button == true ? this.button = false : this.button =true
        }
    }

}
</script>

<style scoped>
#sideber {
    margin: 20px;
    padding-left: 20px;
}
.top

ul {
    list-style: none;
}

/* ＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝ */
/* アニメーション実装 */

.v-enter {
  opacity: 0;
}

.v-enter-to {
  opacity: 1;
}

.v-enter-active {
  transition: all 1000ms;
}
/* ＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝ */

</style>