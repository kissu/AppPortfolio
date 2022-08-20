<template>
  <div>
    <div v-for="accordion in accordions" :key="accordion.title">
      <Item>
        <template #title>
          {{ accordion.title }}
        </template>

        <template #content>
          <div>{{ accordion.text }}</div>
        </template>
      </Item>
    </div>
  </div>
</template>
<script>
import Item from '../components/List-item.vue'
export default {
  components: { Item },
  data () {
    return {
      accordions: [
        {
          title: 'Il écrit',
          text: 'Projects from il écrit'
        },
        {
          title: 'Il chante',
          text: 'Projects from il chante'
        },
        {
          title: 'Il danse',
          text: 'Projects from il danse !'
        }
      ]
    }
  }

}
</script>

<style>
body{
  font-family: 'Courier New', Courier, monospace;
  font-weight: normal;

}

h2{
  font-weight: normal;
  font-size: 1em;
  margin: 0;
}

.wrapper{
    overflow: hidden;
    max-height: 500px;
    transition: 0.3s;
        transition: all 1s linear;

  }
.content.active{
  background: red;
 max-height: 500px;
    transition: max-height 1s ease-in;
    }

.content{
  max-height: 0;
    transition: max-height 1s ease-out;

}

</style>
