<template>
  <q-card-section>
    <div>
      <h6 class="q-pa-sm">
        QQ Example of component using Class (Interface) Item
      </h6>
    </div>
    <div class="q-pa-sm">
      This div element is a Quasar Card component; the Do item Action button is
      associated with each item.
    </div>
    <button @click="clickAction1">Do Action 1</button>
    <div>
      <div v-for="(item, index) in items" :key="index">
        <code>{{ item }}</code>
        <button @click="clickItemAction(item.id)">Do Item Action</button>
      </div>
    </div>
  </q-card-section>
</template>

<script lang="ts">
// note no setup above
import { defineComponent, onMounted, ref } from 'vue';
// Example TS Interface for Item with properties
import { Item } from '../models/item.model';

const it: Item = {
  id: 'abc',
  name: 'def',
  quantity: 3,
  description: 'nothing',
  createdAt: new Date(),
};
console.log('it = ' + it);
// get today's date in ISO format yyyy-mm-dd
const today = new Date().toISOString().substring(0, 10);
export default defineComponent({
  name: 'myComp',

  // note that setup() is here and NOT in < script >
  setup() {
    const items = ref<Item[]>([
      {
        id: 'a',
        name: 'Item A',
        description: 'First item',
        quantity: 3,
        createAt: today,
      },
      {
        id: 'b',
        name: 'Item B',
        description: 'First item',
        quantity: 5,
        createAt: today,
      },
    ]);
    // *** think:  const groceryStore = useGroceryStore();
    onMounted(() => {
      alert('onMounted event is triggered!');
    });
    function clickAction1() {
      alert('Action 1 event');
    }
    function clickItemAction(id: string) {
      alert('You have clicked Item Id: ' + id);
    }
    return {
      items,
      clickAction1,
      clickItemAction,
    };
  },
});
</script>
