<template>
  <q-page class="">
    <list-contacts />
  </q-page>
</template>

<script>

import ListContacts from '../components/ListContacts';

export default {
  name: 'PageIndex',
  components: { ListContacts },
};
</script>
