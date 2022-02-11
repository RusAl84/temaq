<template>
  <q-page class="flex flex-center">
    <q-img
      src="http://localhost:5000/static/wc.png"
      spinner-color="white"
      style="height: 600px; max-width: 600px"
    />
  </q-page>
</template>

<script>
import { computed, defineComponent } from "vue";
import { useStore } from "vuex";

export default defineComponent({
  name: "VisIndex",

  setup() {
    const $store = useStore();
    const opti = computed({
      get: () => $store.state.mes.opti,
      set: (val) => {
        $store.commit("mes/updateOpti", val);
      },
    });
    return {
      $store,
      opti,
    };
  },
});
</script>
<style scoped>
.field-label {
  vertical-align: middle;
}
</style>
