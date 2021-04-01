<template>
  <div class="grid grid-cols-2">
    <input v-model="some"
    class="col-start-1 border-green-500 border-4 rounded p-5 mt-6" type="text" />
    <button 
    @click="addCoctail(some)"
    class="col-start-1 p-5 border-4 bg-green-300 border-black mt-10 text-xl font-semibold uppercase">add coctail</button>
    <ul>
      <li v-for="coctail in coctails" :key="coctail">
        {{ coctail.name }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "HelloWorld",
  data() {
    return {
      coctails: [
        { name: "Белый русский" },
        { name: "Blody Mary" },
        { name: "Vuex" },
      ],
      info: null,
    };
  },
  methods: {
    addCoctail(item: string) {
      this.coctails.push({ name: item});
    }
  },
  props: {
    msg: {
      type: String,
      required: true,
    },
  },
});
</script>
