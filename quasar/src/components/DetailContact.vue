<template>
  <q-dialog v-model="open">
    <q-card class="my-card" v-if="contact"  style="width: 700px; max-width: 80vw;">
       <q-img :src="contact.avatar" :ratio="1" />

      <q-card-section>
        <div class="text-h6">{{ contact.name }}</div>
        <div class="text-subtitle2">{{ contact.email }}</div>
      </q-card-section>

    </q-card>
  </q-dialog>
</template>

<script>
export default {
  props: ['value', 'contact'],
  computed: {
    open: {
      get() {
        return this.value;
      },
      set(val) {
        this.$emit('input', val);
      },
    },
  },
};
</script>

<style>

</style>
