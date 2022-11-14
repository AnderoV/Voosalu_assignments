<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      class="grey darken-4"
    >
      <div v-if="miniVariant">
        <v-list nav dense>
          <v-list-item v-for="[icon] in links_mini" :key="icon" link>
            <div class="d-flex flex-column align-left">
              <v-list-item-icon>
                <v-icon color="grey">{{ icon }}</v-icon>
              </v-list-item-icon>
            </div>
          </v-list-item>
        </v-list>
      </div>
      <div v-else>
        <v-list nav dense>
          <v-list-item v-for="[icon, text] in links_main" :key="icon" link>
            <v-list-item-icon>
              <v-icon color="grey">{{ icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list nav dense>
          <v-list-item v-for="[icon, text] in links_secondary" :key="icon" link>
            <v-list-item-icon>
              <v-icon color="grey">{{ icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list nav dense>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-subtitle>
                TELLIMUSED
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item
            v-for="[avatar, name, notification] in subscriptions"
            :key="avatar"
            link
          >
            <v-list-item-avatar size="25">
              <v-img :alt="`${name} avatar`" :src="avatar"></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title v-text="name"></v-list-item-title>
            </v-list-item-content>
            <v-icon v-if="notification === 'notification'" color="blue">{{
              "mdi-circle-small"
            }}</v-icon>
            <v-icon v-if="notification === 'live'" color="#f00" size="20">{{
              "mdi-access-point"
            }}</v-icon>
          </v-list-item>
          <div v-if="!showMoreSubscriptions">
            <v-list-item
              link
              @click.stop="showMoreSubscriptions = !showMoreSubscriptions"
            >
              <v-list-item-icon class="mr-4">
                <v-icon color="grey">{{ "mdi-chevron-down" }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title
                  >Kuva veel {{ more_subscriptions.length }}</v-list-item-title
                >
              </v-list-item-content>
            </v-list-item>
          </div>
          <div v-else>
            <v-list-item
              v-for="[avatar, name, notification] in more_subscriptions"
              :key="avatar"
              link
            >
              <v-list-item-avatar size="25">
                <v-img :alt="`${name} avatar`" :src="avatar"></v-img>
              </v-list-item-avatar>

              <v-list-item-content>
                <v-list-item-title v-text="name"></v-list-item-title>
              </v-list-item-content>
              <v-icon v-if="notification === 'notification'" color="blue">{{
                "mdi-circle-small"
              }}</v-icon>
              <v-icon v-if="notification === 'live'" color="#f00" size="20">{{
                "mdi-access-point"
              }}</v-icon>
            </v-list-item>
            <v-list-item link>
              <v-list-item-icon class="mr-4">
                <v-icon color="grey">{{ "mdi-plus-circle" }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>Kanalite sirvimine</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item
              link
              @click.stop="showMoreSubscriptions = !showMoreSubscriptions"
            >
              <v-list-item-icon class="mr-4">
                <v-icon color="grey">{{ "mdi-chevron-up" }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>Näita vähem</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </div>
        </v-list>
        <v-divider></v-divider>
        <v-list nav dense>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-subtitle>
                ROHKEM YOUTUBE'IST
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>
          <v-list-item v-for="[icon, text] in links_more" :key="icon" link>
            <v-list-item-icon>
              <v-icon color="grey">{{ icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list nav dense>
          <v-list-item v-for="[icon, text] in links_more2" :key="icon" link>
            <v-list-item-icon>
              <v-icon color="grey">{{ icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content>
              <v-list-item-title>{{ text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <div class="ml-6 mr-8 mt-2" style="letter">
          <a href="#" class="link mr-1 text--secondary caption">Teave</a>
          <a href="#" class="link mr-1 text--secondary caption">Press</a>
          <a href="#" class="link text--secondary caption">Autoriõigused</a>
          <a href="#" class="link text--secondary caption"
            >Võtke meiega ühendust</a
          >
          <a href="#" class="link text--secondary mr-1 caption">Sisuloojad</a>
          <a href="#" class="link text--secondary mr-1 caption">Reklaam</a>
          <a href="#" class="link text--secondary caption">Arendajad</a>
        </div>
        <div class="ml-6 mr-8 mt-2">
          <a href="#" class="link text--secondary mr-1 caption">Tingimused</a>
          <a href="#" class="link text--secondary caption">Privaatsus</a>
          <a href="#" class="link text--secondary mr-3 caption"
            >Eeskirjad ja ohutus</a
          >
          <a href="#" class="link text--secondary caption"
            >Kuidas YouTube toimib?</a
          >
          <a href="#" class="link text--secondary caption"
            >Proovige uusi funktsioone</a
          >
        </div>
        <p class="ml-6 mt-4 body-2 darken" style="color: #757575">
          © 2021 Google LLC
        </p>
      </div>
    </v-navigation-drawer>

    <v-app-bar :clipped-left="clipped" fixed app flat class="grey darken-4">
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <v-img
        class="mx-2"
        src="https://www.youtube.com/about/static/svgs/icons/brand-resources/YouTube-logo-full_color_dark.svg"
        max-height="80"
        max-width="90"
        contain
      ></v-img>
      <v-spacer />
      <v-text-field
        flat
        hide-details
        :append-icon="'mdi-magnify'"
        placeholder="Otsige"
        outlined
        dense
        class="hidden-sm-and-down"
        @click:append="() => {}"
      ></v-text-field>
      <v-tooltip bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="white" class="ml-2" icon v-bind="attrs" v-on="on"
            ><v-icon>mdi-microphone</v-icon></v-btn
          >
        </template>
        <div class="font-weight-medium">
          Häälotsing
        </div>
      </v-tooltip>
      <v-spacer />
      <div v-for="[icon, name] in toolbar_elements" :key="name">
        <v-tooltip bottom>
          <template v-slot:activator="{ on, attrs }">
            <v-btn color="white" class="ml-2" icon v-bind="attrs" v-on="on"
              ><v-icon>{{ icon }}</v-icon></v-btn
            >
          </template>
          <div class="font-weight-medium">
            {{ name }}
          </div>
        </v-tooltip>
      </div>
      <v-btn icon x-large v-on="on">
        <v-avatar class="brown darken-1" size="34">
          <div class="font-weight-medium">
            {{ user.name.charAt(0) }}
          </div>
        </v-avatar>
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: false,
      fixed: false,
      miniVariant: false,
      showMoreSubscriptions: false,
      title: "Youtube",
      links_mini: [
        ["mdi-home", "Avaleht"],
        ["mdi-fire", "Populaarsed"],
        ["mdi-youtube-subscription", "Tellimused"],
        ["mdi-play-box-multiple", "Kogu"]
      ],
      links_main: [
        ["mdi-home", "Avaleht"],
        ["mdi-fire", "Populaarsed"],
        ["mdi-youtube-subscription", "Tellimused"]
      ],
      links_secondary: [
        ["mdi-play-box-multiple", "Kogu"],
        ["mdi-history", "Ajalugu"],
        ["mdi-play-box-outline", "Teie videod"],
        ["mdi-clock", "Hiljem vaatamiseks"],
        ["mdi-playlist-play", "Lemmikud"],
        ["mdi-thumb-up", "Meeldinud videod"]
      ],
      links_more: [
        ["mdi-youtube", "YouTube Premium"],
        ["mdi-youtube-gaming", "Mängud"],
        ["mdi-access-point", "Otseülekanded"],
        ["mdi-trophy", "Sport"]
      ],
      links_more2: [
        ["mdi-cog", "Seaded"],
        ["mdi-flag", "Teavituste ajalugu"],
        ["mdi-help-circle", "Abi"],
        ["mdi-message-alert", "Saada tagasisidet"]
      ],
      subscriptions: [
        [
          "https://yt3.ggpht.com/ytc/AKedOLSr5Li2HcdUrdvp3k0lE1fMup-phmTaGLMV-S9UGA=s88-c-k-c0x00ffffff-no-rj",
          "MrBeast",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLSIHIhj9Lzsdc3QKNT_qLJG6oKxxRF7yh3EPE2S=s88-c-k-c0x00ffffff-no-rj",
          "SteveWillDoIt",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLQg6gDZ9Z0wuMSRwtdl9e0SiI0mklMDFXeGjBktXg=s88-c-k-c0x00ffffff-no-rj",
          "Athlean-X",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLTPcp3knS7sCL9iFRA0JVBtB9ZL3i8PB5-7W2VF3w=s88-c-k-c0x00ffffff-no-rj",
          "JJ Olatunji",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLSjESdJk3FwjE59utIerCf2MkemkvuPkljZcFUv=s88-c-k-c0x00ffffff-no-rj",
          "JRE Clips",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLSI86C9e9bPlRyc7qjsSu4B6s6SF1y49S0jdUo_ZQ=s88-c-k-c0x00ffffff-no-rj",
          "TGFbro",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLSaXT0o-yJFcs40LF3_1wVCsNgqqLhUaLO-df9BhA=s88-c-k-c0x00ffffff-no-rj",
          "KSI",
          null
        ]
      ],
      more_subscriptions: [
        [
          "https://yt3.ggpht.com/ytc/AKedOLSLOopCIjSu8xD1Chi9Za2NkXvRV2yLrnNKzOB5kQ=s68-c-k-c0x00ffffff-no-rj",
          "TheMacLife",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLTcnYiIWz6PngAxP1MTG0iyHT6bpVeUYLNSsRoh_Q=s88-c-k-c0x00ffffff-no-rj",
          "Nick Knows",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLQHZoxF6R_MuJxQk2u6yboQPtxTuzfQrDh8u1bbGQ=s88-c-k-c0x00ffffff-no-rj",
          "Ridddle",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/vVNRN2owIpF1EKhfENoMhDRwNNXHDjL1o_6oG3K13aMlu3dyl4DZuWkq_oAv8an-B1D5Mzbn_UM=s88-c-k-c0x00ffffff-no-rj",
          "Yes Theory",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLQf2e6s9_FvCfjFM14z_q7LUwlu5J7sUaBak7VtPw=s88-c-k-c0x00ffffff-no-rj",
          "Unbox Therapy",
          "notification"
        ],
        [
          "https://yt3.ggpht.com/DqIU2nFqX2zWIvDsozeFQFfvxYBhFjc0z3Lv6snFIR-vwjBaLMyqKBNCWrBkEnOdP5Zz_Stn=s68-c-k-c0x00ffffff-no-rj",
          "xQc Clips",
          null
        ],
        [
          "https://yt3.ggpht.com/ytc/AKedOLSuJXBTeU2pXPoWkQ8yPTO-aBY5ahEs9ct7wST-3w=s68-c-k-c0x00ffffff-no-rj",
          "xQcOW",
          "notification"
        ]
      ],
      toolbar_elements: [
        ["mdi-video-plus", "Loomine"],
        ["mdi-apps", "YouTube'i rakendused"],
        ["mdi-bell", "Märguanded"]
      ],
      user: {
        name: "Andero",
        picture:
          "https://yt3.ggpht.com/yti/APfAmoFZnCWTDtiX3wPHaxIfnlA8QKYH7qHA7PvAPr0dQw=s88-c-k-c0x00ffffff-no-rj-mo"
      }
    };
  }
};
</script>
<style>
.v-navigation-drawer__content::-webkit-scrollbar {
  width: 8px;
  background-color: #212121;
}

.v-navigation-drawer__content::-webkit-scrollbar-thumb {
  background: #616161;
}

.link {
  text-decoration: none;
  background-color: none;
}
</style>
