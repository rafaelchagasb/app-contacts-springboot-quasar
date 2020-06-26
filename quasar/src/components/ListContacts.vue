<template>
  <div>
    <q-toolbar v-if="!searching" class="bg-primary text-white">
      <q-toolbar-title>App</q-toolbar-title>

      <q-btn flat round dense icon="search" @click="searching = true" />
    </q-toolbar>

    <q-input v-if="searching" v-model="text" placeholder="Search" maxlength="12">
        <template v-slot:before>
          <q-btn flat round dense icon="arrow_back" @click="searching = false" />
        </template>
      </q-input>

    <q-list bordered>
      <q-item-label header>Onlines</q-item-label>

      <q-item v-for='contact in contacts' :key='contact.id' class='q-my-sm' clickable v-ripple>
        <q-item-section avatar @click="showDetail = true; selectedContact = contact">
          <q-avatar>
            <q-img :src="contact.avatar" :ratio="1" />
          </q-avatar>
        </q-item-section>

        <q-item-section @click="openChat">
          <q-item-label>{{ contact.name }}</q-item-label>
          <q-item-label caption lines='1'>{{ contact.email }}</q-item-label>
        </q-item-section>

        <q-item-section side>
          <q-icon name='chat_bubble' color='green' />
        </q-item-section>
      </q-item>

      <q-separator />
      <!-- <q-item-label header>Offline</q-item-label>

      <q-item v-for='contact in offline' :key='contact.id' class='q-mb-sm' clickable v-ripple>
        <q-item-section avatar>
          <q-avatar>
            <img :src='`https://cdn.quasar.dev/img/${contact.avatar}`' />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ contact.name }}</q-item-label>
          <q-item-label caption lines='1'>{{ contact.email }}</q-item-label>
        </q-item-section>

        <q-item-section side>
          <q-icon name='chat_bubble' color='grey' />
        </q-item-section>
      </q-item> -->
    </q-list>

    <detail-contact v-model="showDetail" :contact="selectedContact" />

  </div>
</template>

<script>
const contacts = [
  {
    id: 1,
    name: 'Ruddy Jedrzej',
    email: 'rjedrzej0@discuz.net',
    letter: 'R',
    avatar: 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/Andrzej_Person_Kancelaria_Senatu.jpg/400px-Andrzej_Person_Kancelaria_Senatu.jpg',
  },
  {
    id: 2,
    name: 'Mallorie Alessandrini',
    email: 'malessandrini1@marketwatch.com',
    letter: 'M',
    avatar: 'http://cassavafilms.com/wp-content/uploads/2013/01/100522-glennclose.jpg',
  },
  {
    id: 3,
    name: 'Samuel',
    email: 'sam @microsoft.com',
    letter: 'E',
    avatar: 'https://cdn.britannica.com/77/191077-050-63262B99/Samuel-L-Jackson.jpg',
  },
  {
    id: 4,
    name: 'Sheldon',
    email: 'sfawdrey3@wired.com',
    letter: 'S',
    avatar: 'https://pbs.twimg.com/profile_images/365042597/sheldon_400x400.jpg',
  },
];

import DetailContact from './DetailContact';

export default {
  data() {
    return {
      contacts,
      searching: false,
      text: '',
      showDetail: false,
      selectedContact: undefined,
    };
  },
  components: {
    DetailContact,
  },
  methods: {
    openChat() {
      this.$router.push({ path: 'chat' });
    },
  },
};
</script>
