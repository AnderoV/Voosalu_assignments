<template>
  <v-container>
    <v-row>
      <v-col v-for="(video, n) in videos" :key="n" cols="3" class="mb-5 pl-10">
        <v-hover v-slot="{ hover }" open-delay="500">
          <div>
            <v-row dense
              ><v-img v-if="hover" :src="video.thumbnailwebp" contain></v-img>
              <v-img v-else :src="video.thumbnailjpg" contain></v-img>
            </v-row>
            <v-row class="mt-5" dense>
              <v-col :cols="2" class="pl-0 pr-0">
                <v-avatar size="40">
                  <v-img :src="video.avatar"></v-img> </v-avatar
              ></v-col>
              <v-col :cols="10" class="pl-0">
                <v-list-item-title
                  class="font-weight-bold"
                  style="white-space: pre-wrap; margin-bottom: -20px;"
                  >{{ video.title }}
                </v-list-item-title>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.channelName }}
                  <v-icon color="grey" size="14" class="ml-1">{{
                    "mdi-check-circle"
                  }}</v-icon>
                </v-list-item-subtitle>
                <v-list-item-subtitle
                  class="pl-0"
                  style="color: #aaa; font-size: 15px"
                >
                  {{ video.views }}
                  <v-icon color="grey" size="20" class="ml-0 mr-0">{{
                    "mdi-circle-small"
                  }}</v-icon>
                  {{ video.date }}
                </v-list-item-subtitle></v-col
              >
            </v-row>
          </div>
        </v-hover>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      videos: [
        {
          title: "Green Goblin Smokes Weed",
          channelName: "Colaws",
          views: "284 tuh vaatamist",
          date: "3 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/F31Z56Hhbtg/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDGQ3V5JfHNxRn1HW_KicLfbI7Krw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/DUpxo_mgb2E/mqdefault_6s.webp?du=3000&sqp=CMqo04IG&rs=AOn4CLAYzIxmiR6nH-CM_z55OrJEI245bw",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLStpC1ynGa92h_AOdu5oq1GbLJIzefkyASwwckXWw=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "no officer the homework folder was a joke",
          channelName: "RudyMemez",
          views: "3,1 mln vaatamist",
          date: "5 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/CDc7Le0osW4/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLAOUUi9SGjtNFy4ZbA9TAcNMJI4AQ",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/gICHHgfB36s/mqdefault_6s.webp?du=3000&sqp=CLyJ04IG&rs=AOn4CLAmw7FZYqnu6dzMw5ptdsrrO26vvw",
          avatar:
            "https://yt3.ggpht.com/8mNclJ19oy5HCWMMXw6OepiITtuSJDE58aIuOBFcsR-hYrivpstKe8ShKVHxZgc6a1YlxS2Z5w=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "UwU but it hits differently",
          channelName: "Benzy CODM",
          views: "4,4 mln vaatamist",
          date: "5 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/0xvNRqgNhxk/hq2.jpg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/qRnrofE95LQ/mqdefault_6s.webp?du=3000&sqp=CIy904IG&rs=AOn4CLDmpyL-fHtIg1L_xIxbmkrKjYJ9xw",
          avatar:
            "https://yt3.ggpht.com/7qOzoqORN9HZmp6u6gbtR8KMRCDjDIeneyJb9VHJq6OTj0q8920JxqNUx6AEyWFXa6sR8hpIhg=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "i forgot u had 6th sense",
          channelName: "le glandeur",
          views: "658 tuh vaatamist",
          date: "7 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/hi-jXkx2fX8/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLBypjWrbeoMLiH5vL1aQyzmWu2uzg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/hVL3uYrSa0I/mqdefault_6s.webp?du=3000&sqp=CKS704IG&rs=AOn4CLAS3fy-8HguJiaWo5zgaDk_vWRWCA",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLQz3XQcqYkIXP_f_zMuinwP4QpIjoIcWKXtpstb=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "The kid who says who asked",
          channelName: "Dylan Zitkus",
          views: "3,2 mln vaatamist",
          date: "1 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/EpuvcAqnxvk/hq2.jpg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/lIK1jnYr0yw/mqdefault_6s.webp?du=3000&sqp=COyH04IG&rs=AOn4CLDyrWJQx_BO30r-2O6vY1ai-M9ssg",
          avatar:
            "https://yt3.ggpht.com/yFDw8mRgbqXeJd8vcS27pqIQvlVAFGCLm1jvnHepjqstzlffrYOFBsm-6CvSwKW_0Z8nQTzZ=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Peter has a pig",
          channelName: "Arya Stark",
          views: "375 tuh vaatamist",
          date: "2 aasta eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/GSKWBSITLUY/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLAEX_IQVkdHdBd8YwTeQaOwCDmOSw",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/1YJmBakHc3w/mqdefault_6s.webp?du=3000&sqp=CPzJ04IG&rs=AOn4CLCJA4ZOSo86hOyDGWXSBzaE8mOCnw",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLQkkOksq8um6kCP2pXG0kqJqpD9i6cZHXwuZwYs=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "the gas got him",
          channelName: "TheBoy",
          views: "1 mln vaatamist",
          date: "1 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/zqu_aXjf5Zc/hq2.jpg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/VrKW58MS12g/mqdefault_6s.webp?du=3000&sqp=CKDB04IG&rs=AOn4CLB9NHkPo3NJL8gIN4bz--IzuRBZqA",
          avatar:
            "https://yt3.ggpht.com/eQXVZ55dHuyj-oMdl465hZR12Z9ILj8BzEJ0dq_AxjEov7eFt9BfWqYTrBoISD65wc1dhf0nLbo=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: 'Dont mess with this man.',
          channelName: "Clips.YTshorts",
          views: "19 mln vaatamist",
          date: "3 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi_webp/GPdD4vn9lvY/hq2.webp",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/6MIIvoNWzL0/mqdefault_6s.webp?du=3000&sqp=CLe304IG&rs=AOn4CLCa2xd9KOcu_EjVhnc_ZRfMuxH9tA",
          avatar:
            "https://yt3.ggpht.com/KLF8derYqOv5YI127MV9J_XX3U_bndkyLwLe8kraX3FsBbG39Y-WhYypzLP5Mqvw7M0KlFcgdw=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Conor wants Usman but Joe Rogan predict a disaster",
          channelName: "Mojahed Fudailat",
          views: "155 tuh vaatamist",
          date: "5 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/O86qgRG_vAM/hqdefault.jpg?sqp=-oaymwEcCOADEI4CSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLBggjM15azlsWLosWPjJsCrIGniLg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/3HOuBTGabI4/mqdefault_6s.webp?du=3000&sqp=CK6H04IG&rs=AOn4CLArdbY-PDHpzAvUt9zZdtXR_ETi-g",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLSgoDA62Esa3PoTDmsgrrnBz0GST25kYkjaECxA=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title:
            "Jon Jones explains his crazy habit",
          channelName: "XcellentMMA Clips",
          views: "85 tuh vaatamist",
          date: "11 päeva eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/Cw0321TEqTs/hq2.jpg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/mAySKo0s27g/mqdefault_6s.webp?du=3000&sqp=CKir04IG&rs=AOn4CLDigFisk5uIx8rZmawafiH_AzI_4g",
          avatar:
            "https://yt3.ggpht.com/ry6yxMC2KCPlJrfo_oq91czOfq9wsRGDkIWoggh7KxCT7Di-Q42BdE7PlxEYk1B0obSeL4vJ=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Girls with autism vs boys with S",
          channelName: "ohchiz",
          views: "1.3 mln vaatamist",
          date: "4 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/zBl6Cvh4ECA/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLBN-zCrY_8dnGgKjAL0kCg-NU8IBQ",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/BbkoV0C12PU/mqdefault_6s.webp?du=3000&sqp=COSx04IG&rs=AOn4CLBQuG_q_zqoz_djx91knojuQnXUuA",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLTJJxBdTR6bYjHouZ1ui2ss7S6iYpRWGT_0Q_Y4NA=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Bro breathing in 4k",
          channelName: "Impact",
          views: "22 mln vaatamist",
          date: "3 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/B6UwuwBF2TE/hq2.jpg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/uJbB1LVPMNs/mqdefault_6s.webp?du=3000&sqp=CPbG04IG&rs=AOn4CLCVL4Kund57kF6qOnQhA8JBosxQBw",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLSxlx4bm6Ua8Eo-g7BkAWgYbLqFASi3K6Xky_xy9A=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "Lawyers be like",
          channelName: "Meme Zee",
          views: "1,2 mln vaatamist",
          date: "4 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/A1nXtzYTzM0/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLDgG__gRCFVLAvS7h9GZj1TK1nH7g",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/OqTKMrgacCc/mqdefault_6s.webp?du=3000&sqp=CPnP04IG&rs=AOn4CLCo1pxdF3Hh_8Zj6iBTHykm57szMA",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLR8ScVz60IhEd1hIKSVCgz8VHzYYEUW3W6uvU3sGQ=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title:
            "The Nut Room is Crazy",
          channelName: "Don Stever",
          views: "11 mln vaatamist",
          date: "3 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/6OUDk4gMFLA/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLA9rTMsESXrtVlCkrPuxw0P1lMQVA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/kyg4Mt5NP94/mqdefault_6s.webp?du=3000&sqp=CJLN04IG&rs=AOn4CLA32q681jWXhJ8lxPZZ-yBOJOTsMg",
          avatar:
            "https://yt3.ggpht.com/YUzAO_Rh19AKpkumKYszbKrk0X9RRszHfcAvrh3uBu8thvBR9uaTq5-9NGZAFLbSWAHr89Y_=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "nah hes wrong for that",
          channelName: "Editsbyrealist",
          views: "9,5 mln vaatamist",
          date: "3 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/PEZyJH6H2hI/hq2.jpg",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/jCr29oI727M/mqdefault_6s.webp?du=3000&sqp=CNe904IG&rs=AOn4CLBZ2qw5q7-g4JKOME17c8lo7TgfHA",
          avatar:
            "https://yt3.ggpht.com/OoHzlh6uII2Tc-05evrqvWnHS689kckWcjJhULCoNXI0jidJsWpZ1cnoxf4kTw3w8M9SogMN=s88-c-k-c0x00ffffff-no-rj"
        },
        {
          title: "When youre Overly Religious",
          channelName: "Strategiser",
          views: "1,2 mln vaatamist",
          date: "6 kuu eest",
          thumbnailjpg:
            "https://i.ytimg.com/vi/3UHLD-j7dZI/hq720.jpg?sqp=-oaymwEcCOgCEMoBSFXyq4qpAw4IARUAAIhCGAFwAcABBg==&rs=AOn4CLBTKudaTK8fD4HvUkm-dqiJ46oHRA",
          thumbnailwebp:
            "https://i.ytimg.com/an_webp/h667P20VFO4/mqdefault_6s.webp?du=3000&sqp=CM6y04IG&rs=AOn4CLCXNRnt79iufC67QZbhoYlZfQ3Syg",
          avatar:
            "https://yt3.ggpht.com/ytc/AKedOLTFTBflottkAI9Tjko81tBgIz9rlwjF1wkb0PDP=s88-c-k-c0x00ffffff-no-rj"
        }
      ]
    };
  }
};
</script>
