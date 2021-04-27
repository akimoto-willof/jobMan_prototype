<template>
<div>
    <div id="box1" class="box">
        <ul class="check">
            <li>
                <input type="checkbox" class="checkbox-main" :checked="checked" @click="selectAllChecked">
            </li>
            <li>
                <input
                type="checkbox"
                class="checkbox"
                v-for="(item, index) in items"
                :key="`${index}`"
                v-model="checked_items"
                :value="item.id"
                @click="select"
                >
            </li>
        </ul>
        <draggable tag="ul" :options="{group:'ITEMS'}">
            <li>
                <div class="title">求人ID</div>
                <div class="list" v-for="(item, index) in items" :key="`first-${index}`">
                    <div class="list-nav">{{item.id}}</div>
                </div>
            </li>
            <li>
                <div class="title">クライアント名</div>
                <div class="list" v-for="(item, index) in items" :key="`second-${index}`">
                    <div class="list-nav">{{item.name}}</div>
                </div>
            </li>
            <li>
                <div class="title">ステータス</div>
                <div class="list" v-for="(item, index) in items" :key="`thrid-${index}`">
                    <div class="list-nav">{{item.status}}</div>
                </div>
            </li>
            <li>
                <div class="title">人選期日</div>
                <div class="list" v-for="(item, index) in items" :key="`fourth-${index}`">
                    <div class="list-nav">{{item.date}}</div>
                </div>
            </li>
            <li>
                <div class="title">開始日</div>
                <div class="list" v-for="(item, index) in items" :key="`fifth-${index}`">
                    <div class="list-nav">{{item.satrtDate}}</div>
                </div>
            </li>
            <li>
                <div class="title">求人タイトル</div>
                <div class="list" v-for="(item, index) in items" :key="`sixth-${index}`">
                    <div class="list-nav">{{item.title}}</div>
                </div>
            </li>
            <li>
                <div class="title">最寄駅</div>
                <div class="list" v-for="(item, index) in items" :key="`seventh-${index}`">
                    <div class="list-nav">{{item.station}}</div>
                </div>
            </li>
            <li>
                <div class="title">雇用期間</div>
                <div class="list" v-for="(item, index) in items" :key="`eighth-${index}`">
                    <div class="list-nav">{{item.period}}</div>
                </div>
            </li>
            <li>
                <div class="title">研修有無</div>
                <div class="list" v-for="(item, index) in items" :key="`ninth-${index}`">
                    <div class="list-nav">{{item.training}}</div>
                </div>
            </li>
            <li>
                <div class="title">給与形態</div>
                <div class="list" v-for="(item, index) in items" :key="`tenth-${index}`">
                    <div class="list-nav">{{item.salary}}</div>
                </div>
            </li>
        </draggable>
    </div>
</div>
</template>

<script>
import draggable from 'vuedraggable';

export default {
    name: 'Table',
    components: {
        'draggable': draggable,
    },
    data() { 
        return{
            items:[
                {
                id:"0000000000", 
                name:"株式会社ウィルグループ",
                status:"見込み",
                date:"2021/04/01",
                satrtDate:"2021/04/01",
                title:"求人タイトル求人タイトル",
                station:"丸の内線中野坂上駅",
                period:"有期雇用（長期）",
                training:"あり",
                salary:"月給"
                },
                {
                id:"0000000001", 
                name:"株式会社ウィルグループ", 
                status:"見込み", 
                date:"2021/04/02",
                satrtDate:"2021/04/01",
                title:"求人タイトル求人タイトル",
                station:"丸の内線中野坂上駅",
                period:"有期雇用（長期）",
                training:"あり",
                salary:"月給"
                },
                {
                id:"0000000002", 
                name:"株式会社ウィルグループ", 
                status:"見込み", 
                date:"2021/04/03",
                satrtDate:"2021/04/01",
                title:"求人タイトル求人タイトル",
                station:"丸の内線中野坂上駅",
                period:"有期雇用（長期）",
                training:"あり",
                salary:"月給"
                },
                {
                id:"0000000003", 
                name:"株式会社ウィルグループ", 
                status:"見込み", 
                date:"2021/04/01",
                satrtDate:"2021/04/01",
                title:"求人タイトル求人タイトル",
                station:"丸の内線中野坂上駅",
                period:"有期雇用（長期）",
                training:"あり",
                salary:"月給"
                },
            ],
            checked: false,
            checked_items: [], 
        }
    },
    methods: {
        selectAllChecked (){
            if(this.checked) {
                this.checked_items = []
                this.checked = false
            } else {
                this.checked_items = []
                for (let item in this.items) {
                    this.checked_items.push(this.items[item].id)
                }
                this.checked = true
            }
            console.log(this.checked_items);
        },
        select (){
            if(this.checked_items.length !== this.items.length) {
                this.checked = false
            } else {
                this.checked =true
            }
        }
    }
}
</script>

<style scoped>
#box1 {
    display: flex;
    text-align: center;
}
.check {
    position: relative;
}

.checkbox-main {
    position: absolute;
    top: 10%;
    left: 60%;
}

.checkbox {
    margin: 20px;
}

.checkbox:first-child {
    margin-top: 65px;
}

.title {
    margin: 10px 0;
    padding: 10px;
    height: 10px;
}

ul {
    display: flex;
    align-items: center;
    font-size: 8px;
}

li {
    cursor: pointer;
    list-style: none;

}
li .button {
    margin: 0;
    padding: 0;
    border: none;
    background-color: #ffffff;
}

li .list-nav {
  border-bottom: solid #ddd 1px;
  text-overflow: ellipsis;
  width: 10vw;
  height: 10px;
  white-space: nowrap;
  overflow: hidden;
  padding: 20px 0;
}
</style>