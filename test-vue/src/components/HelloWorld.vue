<template>
  <div>
    <div class="ribbon"></div>
    <v-card height="900" width="256" class="mx-auto">
      <v-navigation-drawer permanent>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="text-h6">
              Application
            </v-list-item-title>
            <v-list-item-subtitle>
              subtext
            </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>


        <div class="text-center">
          <div class="dialog-all">
            <v-dialog v-model="dialog" width="403px" height="188px" left="100px" class="dialog-nav">
              <template v-slot:activator="{ on }">
                <v-btn v-on="on">
                  Try Admin Portal v2
                </v-btn>
              </template>



              <v-card class="dialog-card">
                <v-card-text>
                  New version available
                </v-card-text>

                <v-divider></v-divider>

                <v-card-text>
                  You can now try new version of Management portal for Administrator by accessing here.
                </v-card-text>

                <v-divider></v-divider>

                <v-card-actions>
                  <v-spacer>
                    <div>
                      <v-checkbox v-model="checkbox" :label="`Don't show this message again!`"></v-checkbox>
                    </div>
                  </v-spacer>
                  <v-btn color="primary" text @click="dialog = false">
                    I've got it
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-dialog>
          </div>
        </div>

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
  </div>

</template>
<script>
export default {
  name: 'HelloWorld',

  data() {
    return {
      dialog: false,
      items: [
        { title: 'Dashboard', icon: 'mdi-view-dashboard' },
        { title: 'Photos', icon: 'mdi-image' },
        { title: 'About', icon: 'mdi-help-box' },
      ],
      right: null,
    }
  },
}
</script>
