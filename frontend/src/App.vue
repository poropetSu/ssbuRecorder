<script setup>
import { ref } from 'vue'

const result = ref('win')

const fighters = [
  {id:'mario', name:'マリオ'},
  {id:'link', name:'リンク'},
  {id:'carby', name:'カービィ'},
]

const myFighterId = ref('');
const opponentFighterId = ref('');
</script>

<template>
  <main><!--勝敗-->
    <h1>ssbuRecorder</h1>
    <p>スマブラの対戦結果を記録するアプリ</p>
    <label>
      自分のファイター
      <select v-model="myFighterId">
        <option disabled value="">選んでください</option>
        <option v-for="fighter in fighters" :key="fighter.id" :value="fighter.id">{{ fighter.name }}</option>
        </select>
    </label>
    <label>
      相手のファイター
      <select v-model="opponentFighterId">
        <option disabled value="">選んでください</option>
        <option v-for="opponentFighter in fighters" :key="opponentFighter.id" :value="opponentFighter.id">{{ opponentFighter.name }}</option>
        </select>
    </label>
  <fieldset>
    <legend>勝敗</legend>
    <label><input type="radio" v-model="result" value="win">勝ち</label>
    <label><input type="radio" v-model="result" value="lose">負け</label>
  </fieldset>
  <p>選択した値：{{ result }}</p>
  </main>
</template>

<style scoped>
main {
  padding:24px;
}</style>
