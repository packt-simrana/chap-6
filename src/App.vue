<template>
  <div id="app">
    <div class="grid">
      <component
        class="grid-item"
        v-for="item in items"
        :key="item.id"
      />
    </div>
  </div>
  <component
    :is="itemComponent"
    class="grid-item"
    v-for="item in items"
    :key="item.id"
  />
  Display mode:
  <input
    type="radio"
    name="style"
    value="Card"
    v-model="itemComponent"
    id="card-radio"
  />
  <label for="card-radio">Card</label>
  <input
    type="radio"
    name="style"
    value="ImageEntry"
    v-model="itemComponent"
    id="image-radio"
  />
  <label for="image-radio">Image</label>
  <component
    class="grid-item"
    v-for="item in items"
    :key="item.id"
    :is="itemComponent"
    :url="item.url"
    :title="item.title"
  />
</template>
<script>
import Card from './components/Card.vue';
import ImageEntry from './components/ImageEntry.vue';
export default {
  components: {
    Card,
    ImageEntry
  },
  data() {
    return {
          itemComponent: 'Card',
      items: [
        {
          id: '10',
          title: 'Forest Shot',
          url: 'https://picsum.photos/id/10/1000/750.jpg',
        },
        {
          id: '1000',
          title: 'Cold cross',
          url: 'https://picsum.photos/id/1000/1000/750.jpg',
        },
        {
          id: '1002',
          title: 'NASA shot',
          url: 'https://picsum.photos/id/1002/1000/750.jpg',
        },
        {
          id: '866',
          title: 'Peak',
          url: 'https://picsum.photos/id/866/1000/750.jpg'
        },
      ]
    }
  }
}
</script>
