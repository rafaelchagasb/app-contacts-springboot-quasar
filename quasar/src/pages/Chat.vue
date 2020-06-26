<template>
  <div>
    <q-toolbar class="bg-primary text-white">
      <q-btn flat round dense icon="arrow_back" class="q-mr-sm" @click="backList" />
      <q-avatar>
        <q-img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/Andrzej_Person_Kancelaria_Senatu.jpg/400px-Andrzej_Person_Kancelaria_Senatu.jpg"
          :ratio="1" />
      </q-avatar>

      <q-toolbar-title>Quasar Framework</q-toolbar-title>

    </q-toolbar>

    <q-footer>
        <q-toolbar class="bg-grey-3 text-black row">
          <q-btn round flat icon="insert_emoticon" class="q-mr-sm" />
          <q-input rounded outlined dense class="WAL__field col-grow q-mr-sm"
            bg-color="white" v-model="message" placeholder="Type a message" />
          <q-btn round flat icon="mic" />
        </q-toolbar>
      </q-footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: '',
    };
  },
  methods: {
    backList() {
      this.$router.push({ path: '/' });
    },
  },
};
</script>

<style>

</style>
