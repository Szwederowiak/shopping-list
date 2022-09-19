<template>
  <div class="container p-5 d-flex align-items-center justify-content-center">
      <div class="list-wrapper d-flex flex-column p-3 border rounded-4 text-center shadow">
          <h1 class="h3 mb-3">Shopping list</h1>
          <input type="text" v-model="inputValue" class="form-control mb-1">
          <input type="submit" value="Add" @click="addItem" class="mb-3 btn btn-primary">

          <ul class="d-flex flex-column m-0 p-0">
              <ListItem v-for="item in items" :key="item.id" :id="item.id" :content="item.content"
                  @delete-id="deleteItem"></ListItem>
          </ul>
      </div>
  </div>
</template>

<script>
import ListItem from './components/ListItem.vue';
export default {
  data() {
      return {
          inputValue: "",
          items: [
              { id: 0, content: "mleko" },
              { id: 1, content: "ser" },
              { id: 2, content: "chleb" },
              { id: 3, content: "piwo" }
          ]
      };
  },
  watch: {
      inputValue() {
          console.table(this.items);
      }
  },
  methods: {
      addItem() {
          if (this.inputValue !== '') {
              this.items.push({
                  id: this.items.length,
                  content: this.inputValue
              });

              this.inputValue = '';
          }
      },
      deleteItem(id) {
          // this.items.slice(this.items.indexOf(this.items.find(item => item.id === id)))
          this.items = this.items.filter(item => item.id !== id);
      }
  },
  components: { ListItem }
}
</script>

<style scoped>
.list-wrapper {width: 250px;}
</style>