<template>
  <div>
    <select v-model="current">
      <option v-for="topic in topics" :value="topic.value">
        {{ topic.name }}
      </option>
    </select>
    <div v-for="item in list">
      {{ item.full_name }}
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      list: [],
      current: '',
      topics: [
        { value: 'vue', name: 'Vue.js' },
        { value: 'react', name: 'React.js' },
        { value: 'jquery', name: 'jQuery' }
      ]
    };
  },
  watch: {
    current: function(val) {
      axios.get('https://api.github.com/search/repositories', {
        params: {q: 'topic:' + val }
      }).then(function(response) {
        this.list = response.data.items
      }.bind(this))
    }
  }
};
</script>