<template>
 <!-- onload="HRELoadPrefecture('prefecture', 'line', 'station');" -->
    <body>
         <!-- id="prefecture" name="prefecture" @onchange="HREOnChangePrefecture" -->
        <select @change="HREOnChangeLine">
            <option value="都道府県を選択してください">都道府県を選択してください</option>
            <option v-for="(prefecture, index) in prefectures" :key="index">
                {{ prefectures[index] }}
            </option>
        </select>
        <select @change="HREOnChangeStation">
            <option value="路線を選択してください">路線を選択してください</option>
            <option v-for="(line, index) in lines" :key="index">
                {{ lines[index] }}
            </option>
        </select>
        <select>
            <option value="駅を選択してください">駅を選択してください</option>
            <option v-for="(staition, index) in stations" :key="index">
                {{ stations[index].name }}
            </option>
        </select>
    </body>
</template>

<script>
import axios from 'axios';

export default {
    component: axios,
    data () {
        return {
            prefectures: [],
            lines: [],
            stations: [],
        }
    },
    mounted () {
    axios
        .get('http://express.heartrails.com/api/json?method=getPrefectures')
        .then(response => (this.prefectures = response.data.response.prefecture))
    },
    methods: {
        HREOnChangeLine(e) {
            const ref = encodeURI(e.target.value)
            axios
                .get('http://express.heartrails.com/api/json?method=getLines&prefecture=' + ref)
                .then((response) => {
                    (this.lines = response.data.response.line)
                console.log(this.lines);
            })
        },
        HREOnChangeStation(e) {
            const ref = encodeURI(e.target.value)
            axios
                .get('http://express.heartrails.com/api/json?method=getStations&line=' + ref)
                .then((response) => {
                    console.log(response.data.response.station);
                    (this.stations = response.data.response.station)
            })
        }
    }
}
</script>
