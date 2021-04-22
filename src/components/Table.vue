<template>
<div>
    <div id="box1" class="box">    
        <draggable tag="ul" :options="{group:'ITEMS'}">
        <li>
            <div class="title">求人ID</div>
            <div class="list" v-for="item in items" :key="item.id">
                <div class="list-nav">{{item.id}}</div>
            </div>
        </li>
        <li>
            <div class="title">クライアント名</div>
            <div class="list" v-for="item in items" :key="item.name">
                <div class="list-nav">{{item.name}}</div>
            </div>
        </li>
        <li>
            <div class="title">ステータス</div>
            <div class="list" v-for="item in items" :key="item.status">
                <div class="list-nav">{{item.status}}</div>
            </div>
        </li>
        <li>
            <div class="title">人選期日</div>
            <div class="list" v-for="item in items" :key="item.date">
                <div class="list-nav">{{item.date}}</div>
            </div>
        </li>
        <li>
            <div class="title">開始日</div>
            <div class="list" v-for="item in items" :key="item.satrtDate">
                <div class="list-nav">{{item.satrtDate}}</div>
            </div>
        </li>
        <li>
            <div class="title">求人タイトル</div>
            <div class="list" v-for="item in items" :key="item.title">
                <div class="list-nav">{{item.title}}</div>
            </div>
        </li>
        <li>
            <div class="title">最寄駅</div>
            <div class="list" v-for="item in items" :key="item.station">
                <div class="list-nav">{{item.station}}</div>
            </div>
        </li>
        <li>
            <div class="title">雇用期間</div>
            <div class="list" v-for="item in items" :key="item.period">
                <div class="list-nav">{{item.period}}</div>
            </div>
        </li>
        <li>
            <div class="title">研修有無</div>
            <div class="list" v-for="item in items" :key="item.training">
                <div class="list-nav">{{item.training}}</div>
            </div>
        </li>
        <li>
            <div class="title">給与形態</div>
            <div class="list" v-for="item in items" :key="item.salary">
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
  data(){ 
      return {
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
        salary:"月給"},
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
        salary:"月給"},
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
        salary:"月給"},
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
        salary:"月給"},
    ]
    }
  }
}
</script>

<style>
template {
  padding : 15px;
}
ul {
    display: flex;
    font-size: 8px;
}

li {
  cursor:pointer;
  padding: 10px;
  list-style: none;
}

li .list-nav {
  border-bottom: solid #ddd 1px;
  text-overflow: ellipsis;
  width: 10vw;
  white-space: nowrap;
  overflow: hidden;
}

.del {
  color: #f00;
}
</style>