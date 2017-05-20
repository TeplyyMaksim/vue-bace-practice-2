<template>
  <div id="app">
    <img src="./assets/logo.png">
    <p v-if="show">If statement</p>
    <p v-else>Else statement</p>
    <h1 v-show="!show">Grand heading</h1>
    <template v-if="show">
      <h2>Side</h2>
      <h2>Effects</h2>
    </template>
    <p>I'll be here forever</p>
    <button @click="show = !show">Toggle showing</button>
    <hr>

    <ul class="hu-members">
      <li v-for="(groupMember, i) in groupMembers">{{groupMember}} ({{i}})</li>
    </ul>
    <button type="button" @click="groupMembers.push('Deuse')">Add member</button>
    <template v-for="(groupMember, i) in groupMembers">
      <p>Member name: <b>{{groupMember}}</b> Member index <b>{{i}}</b></p>
    </template>
    <hr>

    <ul>
      <li v-for="person in persons">
        <span v-for="(value, key) in person">{{key}} : {{value}} </span>
      </li>
    </ul>
    |<span v-for="n in 10">{{n}}|</span>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      show: false,
      groupMembers: ['Charlie Scene', 'Funny Man', 'J-Dog', 'Johnny 3 Tears', 'Da Kurlz', 'Danny'],
      persons: [
        { name: 'Maksim', age: 20, sex: 'male' },
        { name: 'Vife', age: 19, sex: 'female' },
        { name: 'Doomsday', age: 'unknown', sex: 'unknown' },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul {
  text-align: left;
}
</style>
