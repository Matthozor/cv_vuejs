<template>
    <div class="element-infos-xp">
        <h3>{{ title }}</h3>
        <ul>
            <li v-for="todo in infos" :key="todo.name">
                <br>
                {{ todo.name }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  name: 'Info',
  props: [
      'infos',
      'title'
  ],
  mounted() {
      console.log(this.infos)
  }
}
</script>
