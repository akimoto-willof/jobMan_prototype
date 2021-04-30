<template>
  <div>
    <div id="box1" class="box">
      <div>
        <!-- 項目表示リスト -->
        <draggable tag="ul" class="main_title">
          <input
            type="checkbox"
            class="checkbox-main"
            :checked="checked"
            @click="selectAllChecked"
          />
          <li><div class="title">求人ID</div></li>
          <li><div class="title">クライアント名</div></li>
          <li><div class="title">ステータス</div></li>
          <li><div class="title">人選期日</div></li>
          <li><div class="title">開始日</div></li>
          <li><div class="title">求人タイトル</div></li>
          <li><div class="title">最寄駅</div></li>
          <li><div class="title">雇用期間</div></li>
          <li><div class="title">研修有無</div></li>
          <li><div class="title">給与形態</div></li>
        </draggable>

        <!-- 案件リスト -->
        <div
          class="list"
          v-for="(item, index) in items"
          :key="`first-${index}`"
        >
          <ul>
            <input
              type="checkbox"
              class="checkbox"
              v-model="checked_items"
              :value="item.id"
              @click="select"
            />
            <li class="details">
              <button @click="onActive(n)">⇓</button>
            </li>
            <li>
              <div class="list-nav">{{ item.id }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.name }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.status }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.date }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.startDate }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.title }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.station }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.period }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.training }}</div>
            </li>
            <li>
              <div class="list-nav">{{ item.salary }}</div>
            </li>
          </ul>
          <ul class="list-detail" :class="{'is-active': activeItem === n}">
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">求人ID</div>
              <div class="nav">{{ item.id }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">クライアント名</div>
              <div class="nav">{{ item.name }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">ステータス</div>
              <div class="nav">{{ item.status }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">人選期日</div>
              <div class="nav">{{ item.date }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">開始日</div>
              <div class="nav">{{ item.startDate }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">求人タイトル</div>
              <div class="nav">{{ item.title }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">最寄駅</div>
              <div class="nav">{{ item.station }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">雇用期間</div>
              <div class="nav">{{ item.period }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">研修有無</div>
              <div class="nav">{{ item.training }}</div>
            </li>
            <li class="list-nav-detail">
              <div class="list-nav-detail-title">給与形態</div>
              <div class="nav">{{ item.salary }}</div>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "Table",
  components: {
    draggable: draggable,
  },
  data() {
    return {
      items: [
        {
          number: 1,
          id: "0000000000",
          name: "株式会社ウィルグループ",
          status: "見込み",
          date: "2021/04/01",
          startDate: "2021/04/01",
          title: "求人タイトル求人タイトル",
          station: "丸の内線中野坂上駅",
          period: "有期雇用（長期）",
          training: "あり",
          salary: "月給",
        },
        {
          number: 2,
          id: "0000000001",
          name: "株式会社ウィルグループ",
          status: "見込み",
          date: "2021/04/02",
          startDate: "2021/04/01",
          title: "求人タイトル求人タイトル",
          station: "丸の内線中野坂上駅",
          period: "有期雇用（長期）",
          training: "あり",
          salary: "月給",
        },
        {
          number: 3,
          id: "0000000002",
          name: "株式会社ウィルグループ",
          status: "見込み",
          date: "2021/04/03",
          startDate: "2021/04/01",
          title: "求人タイトル求人タイトル",
          station: "丸の内線中野坂上駅",
          period: "有期雇用（長期）",
          training: "あり",
          salary: "月給",
        },
        {
          number: 4,
          id: "0000000003",
          name: "株式会社ウィルグループ",
          status: "見込み",
          date: "2021/04/01",
          startDate: "2021/04/01",
          title: "求人タイトル求人タイトル",
          station: "丸の内線中野坂上駅",
          period: "有期雇用（長期）",
          training: "あり",
          salary: "月給",
        },
      ],
      checked: false,
      checked_items: [],
      activeItem: null
    };
  },
  methods: {
    selectAllChecked() {
      if (this.checked) {
        this.checked_items = [];
        this.checked = false;
      } else {
        this.checked_items = [];
        for (let item in this.items) {
          this.checked_items.push(this.items[item].id);
        }
        this.checked = true;
      }
      console.log(this.checked_items);
    },
    select() {
      if (this.checked_items.length !== this.items.length) {
        this.checked = false;
      } else {
        this.checked = true;
      }
    },
    onActive(n) {
      if(this.activeItem === n) {
        this.activeItem = null;
      } else {
        this.activeItem = n;
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

.checkbox {
  margin: 20px;
}

.title {
  width: 70px;
}

ul {
  justify-content: space-between;
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
.list ul {
  display: flex;
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
.list-detail {
  justify-content: left;
  gap: 40px;
}
.list-nav-detail {
  text-align: left;
  color: #999999;
  display: none;
}
.list-nav-detail:first-child {
  padding-left: 100px;
}

.is-active{
  display: block;
}
</style>
