<template>
 
  <v-app>
    <v-card height="100vh" width="256" class="m-0">
      <v-navigation-drawer permanent>
        <v-list-item>
          <!-- <v-list-item-avatar>
              <v-img src="https://randomuser.me/api/portraits/women/85.jpg"></v-img>
            </v-list-item-avatar> -->
          <v-list-item-content>
            <v-list-item-title class="text-h6">
              Simeon Olorunninwo
            </v-list-item-title>
            <v-list-item-subtitle>
              Software Engineer
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>

        <v-list dense nav>
          <v-list-item v-for="item in items" :key="item.title" link>
            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-card>
   <v-main>
    <v-container>
      <slot/>
    </v-container>
   </v-main>
   
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
.v-application--wrap {
  flex-direction: row;
  flex: 0 auto;
}
</style>

<script>
export default {
  data() {
    return {
      items: [
        { title: "About", icon: "mdi-account-box-outline" },
        { title: "Projects", icon: "mdi-apps" },
        { title: "Education", icon: "mdi-school-outline" },
        { title: "Contacts", icon: "mdi-message-text-outline" },
      ],
      right: null,
    };
  },
};
</script>
