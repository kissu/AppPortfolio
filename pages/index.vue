<template>
  <div class="container">
    <div v-for="accordion in accordions" :key="accordion.title" class="l">
      <Item>
        <template #title>
          {{ accordion.title }}
        </template>

        <template #content>
          <div>{{ accordion.text }}</div>
        </template>
      </Item>
    </div>
    <!-- here goes R -->
    <div class="r">
      <p> contenu pour R</p>
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
  font-family:sans-serif;
  font-weight: normal;
  color: rgb(189, 183, 107);
  background-color:rgb(240, 240, 240);
  font-size: 1.25rem;
line-height: 1.25rem;

}

a{
  font-weight: normal;
  font-size: 1em;
  margin: 0;
}

.active>a{
  color:brown;
}

p{
  margin:0;
}
.container{
  display: grid;
  grid-template-columns: repeat(10,auto);
  grid-gap: 0 1em;
}

.l{
  grid-column: 1;
}

.r{
  grid-column: 2/4;
  grid-row: 1;
}

a:hover{
  cursor: pointer;
}

.wrapper{
    overflow: hidden;
    max-height: 500px;

  }
.content.active{
  max-height: 500px;
   transition-property: width, max-height;
  transition-duration: 1s, 2s;
  transition-timing-function: cubic-bezier(0.305, 0.000, 0.000, 1.015);
  transition-delay: 0, 3s;
  /* transition: width 700ms cubic-bezier(0.305, 0.000, 0.000, 1.015), height 2s; custom */
  width: 70vw;
}

.content{
  width: 0px;
  max-height: 0;
  transition-property: width, max-height;
  transition-timing-function: cubic-bezier(0.305, 0.000, 0.000, 1.015);
  transition-duration: 2s, 1s;
  transition-delay: 1s, 0;
  /* transition: width 700ms cubic-bezier(0.305, 0.000, 0.000, 1.015), height 2s; custom */

}

</style>
