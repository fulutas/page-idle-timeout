<template>
  <button @click="increment">Count is: {{ count }}</button>
</template>

<script setup>
import { ref, watch } from "vue";
import useUserActive from "./useUserActive";

const count = ref(0);

const increment = () => {
  count.value++;
};

const { isExpire } = useUserActive();

watch(isExpire, (newValue, oldValue) => {
  console.log('isExpireNewValue : ', newValue);
  console.log('isExpireOldValue : ', oldValue);
}, { deep: true  });

</script>
