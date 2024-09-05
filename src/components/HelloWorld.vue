<script setup lang="ts">
import { ref } from "vue";
type list = {
  name: string;
  age: number;
  gender: string;
};

const myfriend: list[] = [
  {
    name: "Subaru",
    age: 22,
    gender: "man",
  },
  {
    name: "Rem",
    age: 22,
    gender: "woman",
  },
  {
    name: "Pack",
    age: 22,
    gender: "man",
  },
];

defineProps<{ msg: string }>();
const count = ref<number>(0);
const increase = () => {
  count.value++;
};
const decrease = () => {
  if (count.value === 0) {
    count.value = 0;
  } else {
    count.value--;
  }
};
</script>

<template>
  <div class="temp">
    <h1 class="hello-h1">{{ msg }}</h1>
    <div class="card">
      <p>count is {{ count }}</p>
      <div>
        <button type="button" @click="increase">+</button>
        <button type="button" @click="decrease">-</button>
      </div>
    </div>
  </div>
  <div class="temp">
    <h1>フレンドリスト</h1>
    <div>
      <table border="1" class="table">
        <tr>
          <th>名前</th>
          <th>年齢</th>
          <th>性別</th>
        </tr>
        <tr v-for="friend in myfriend">
          <td>{{ friend.name }}</td>
          <td>{{ friend.age }}</td>
          <td>{{ friend.gender }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
