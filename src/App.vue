<template>
  <div id="app">
    <v-app app>
      <v-app-bar
        app
        dense
        flat
        elevation="0"
        absolute
        fixed
        overflow
        elevate-on-scroll
        scroll-target="#scrolling-techniques-7"
        color="white"
      >
        <v-app-bar-nav-icon
          @click="drawer = true"
          class="d-flex d-sm-none"
        ></v-app-bar-nav-icon>
        <v-toolbar-title id="title" class="mx-10 my-auto">
          <p class="my-auto text-h5 text--lighten-5 mr-16" id="title-web">
            Hilmi Satrio
          </p>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-tabs
          v-model="tab"
          align-with-title
          class="d-none d-sm-flex justify-md-end me-10"
        >
          <v-tabs-slider color="green"></v-tabs-slider>
          <!-- batas -->
          <!-- <v-tab v-for="item in items" :key="item">
            {{ item.title }}
          </v-tab> -->
          <!-- batas -->
          <v-tab @click="home_menu">Home</v-tab>
          <v-tab @click="about_menu">Tentang Saya</v-tab>
          <v-tab @click="skill_menu">Keahlian</v-tab>
          <v-tab @click="portfolio_menu">Portfolio</v-tab>
          <v-tab @click="contact_menu">Hubungi Saya</v-tab>
        </v-tabs>
        <!-- </template> -->
      </v-app-bar>
      <!-- Add a navigation bar -->
      <v-navigation-drawer v-model="drawer" absolute temporary>
        <v-list nav dense>
          <v-list-item-group>
            <!-- batas -->
            <!-- <v-list-item v-for="(item, action) in items" :key="item.id">
              <v-list-item-title @click="action">{{
                item
              }}</v-list-item-title>
            </v-list-item> -->
            <!-- batas -->
            <v-list-item>
              <v-list-item-title @click="home_menu"> Home </v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title @click="about_menu">
                Tentang saya
              </v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title @click="skill_menu">
                Keahlian
              </v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title @click="portfolio_menu">
                Portfolio
              </v-list-item-title>
            </v-list-item>
            <v-list-item>
              <v-list-item-title @click="contact_menu">
                Hubungi Saya
              </v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>
      <!-- main section -->
      <section>
        <v-container class="intro-section" id="home">
          <v-row class="align-center px-5" style="height: 55rem">
            <v-col
              lg="6"
              xs="12"
              sm="5"
              md="6"
              class="pa-6 font-weight-bold py-16"
            >
              <p><span class="green--text">halo</span>, selamat datang</p>
              <p class="display-3 text-h4">
                <span class="green--text">Saya, </span>Muhammad Hilmi Satrio
              </p>
              <p class="display-3 text-h5">
                <span class="green--text">Student</span> &
                <span class="pink--text">Programmer</span>
              </p>
              <v-subheader
                >Jangan mengejar sesuatu yang terbaik, tapi kejarlah sesuatu
                yang bermanfaat</v-subheader
              >
              <br />
              <br />
              <v-btn
                id="btn-contact"
                large
                elevation="5"
                color="pink"
                class="white--text mt-5 ml-7 px-10 py-5 rounded-pill"
                href="#contact"
                >Hubungi Saya
              </v-btn>
            </v-col>
            <v-col lg="6" xs="12" sm="5" md="6">
              <!-- <v-img
                src="https://preview.colorlib.com/theme/jackco/assets/img/hero/xhero_right.png.pagespeed.ic.U76_mb-Zcf.webp"
              ></v-img> -->
              <v-img :src="image_profil" max-width="80%" class="mx-auto">
              </v-img>
            </v-col>
          </v-row>
        </v-container>
        <!-- pendidikan -->
        <v-container id="aboutme">
          <p class="display-3 text-h5 pink--text mt-10">Tentang Saya</p>
          <v-row>
            <v-col
              lg="6"
              xs="12"
              sm="5"
              md="6"
              cols="12"
              class="pa-6 font-weight-bold py-10"
            >
              <p class="text-h6 black--text">Profil singkat</p>
              <p class="grey--text">
                Nama saya<span class="black--text"> Muhammad Hilmi Satrio</span
                >, saat ini saya berusia 20 tahun. Keseharian saya adalah
                sebagai seorang mahasiswa disalah satu universitas di
                Jakarta.<br />
                Ketertarikan ke dalam dunia Informatika, khususnya programming
                diawali adanya rasa keingintahuan pembuatan sebuah software yang
                saya pakai dari berbagai device. Oleh karena itu saya memutuskan
                untuk mengambil program studi
                <span class="black--text">Teknik Informatika</span>. Hingga saat
                ini saya selalu menyempatkan waktu untuk belajar web dan mobile
                developer, dengan Harapan supaya menjadi seorang developer
                expert.
              </p>
            </v-col>
            <v-col
              lg="6"
              xs="12"
              sm="5"
              md="6"
              cols="12"
              class="pa-6 font-weight-bold py-10"
            >
              <p class="text-h6 black--text">Mari Berteman</p>
              <p class="grey--text">
                Berikut ini beberapa akun resmi saya, jika anda tertarik
                silahkan klik tautan dibawah ini.
              </p>
              <v-row class="mt-8">
                <v-chip class="px-4 ma-3" color="primary" @click="fb">
                  <v-icon left size="20" @submit="fb">mdi-facebook</v-icon>
                  Facebook
                </v-chip>
                <v-chip
                  class="px-4 ma-3 white--text"
                  color="#01ff56"
                  @click="wa"
                >
                  <v-icon left size="20">mdi-whatsapp</v-icon>
                  whatsapp
                </v-chip>
                <v-chip
                  class="px-4 ma-3 white--text"
                  color="#833AB4"
                  @click="ig"
                >
                  <v-icon left size="20">mdi-instagram</v-icon>
                  instagram
                </v-chip>
                <v-chip class="px-4 ma-3" color="info" @click="linkedin">
                  <v-icon left size="20">mdi-linkedin</v-icon>
                  Linkedin
                </v-chip>
                <v-chip class="px-4 ma-3" color="dark" @click="github">
                  <v-icon left size="20">mdi-github</v-icon>
                  github
                </v-chip>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
        <!-- route pendidikan -->
        <v-container id="riwayat-pendidikan">
          <p class="display-3 text-h5 pink--text mt-10">Riwayat Pendidikan</p>
          <v-div class="mx-auto" justify-center>
            <v-img class="mx-auto" :src="image_school" max-width="60%"></v-img>
          </v-div>
        </v-container>
        <!-- skill -->
        <v-container id="skill">
          <p class="display-3 text-h5 pink--text mt-10">Keahlian Saya</p>
          <v-row class="mt-3">
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img :src="image_java" max-width="30%" class="mx-auto"></v-img>
            </v-col>
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img :src="image_php" max-width="30%" class="mx-auto"></v-img>
            </v-col>
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img
                :src="image_kotlin"
                max-width="30%"
                class="mx-auto"
              ></v-img>
            </v-col>
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img :src="image_sql" max-width="30%" class="mx-auto"></v-img>
            </v-col>
          </v-row>
          <v-row class="mt-8">
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img :src="image_html" max-width="30%" class="mx-auto"></v-img>
            </v-col>
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img :src="image_css" max-width="30%" class="mx-auto"></v-img>
            </v-col>
            <v-col lg="3" xs="6" sm="3" md="3" cols="6">
              <v-img :src="image_vue" max-width="30%" class="mx-auto"></v-img>
            </v-col>
          </v-row>
        </v-container>
        <!-- portfolio -->
        <v-container class="mt-10" id="portfolio">
          <p class="display-3 text-h5 pink--text mt-10">Portfolio</p>
          <v-row justify="center">
            <v-expansion-panels accordion>
              <v-expansion-panel v-for="(item, i) in data_portfolio" :key="i">
                <v-expansion-panel-header class="text-h6 text--black">{{
                  "#" + item.no + ". " + item.title
                }}</v-expansion-panel-header>
                <v-expansion-panel-content class="mx-auto my-7">
                  <v-img
                    :src="item.image_portfolio"
                    max-width="80%"
                    class="mx-auto mb-7"
                  ></v-img>
                  {{ item.text }}
                  <v-chip class="px-4 ma-3" color="dark" @click="github_keppoya_note">
                    <v-icon left size="20">mdi-github</v-icon>
                    github
                  </v-chip>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
        </v-container>
        <!-- contact me -->
        <v-container class="mt-10" id="contact">
          <p class="display-3 text-h5 pink--text mt-10">Hubungi saya</p>
          <v-row>
            <v-col class="flex justify-center" cols="12">
              <v-card
                class="mx-auto px-7 py-8 rounded-lg green lighten-4"
                max-width="30rem"
              >
                <p class="text-h5 text-center" id="title-contact">
                  Hubungi saya
                </p>
                <form
                  ref="form"
                  lazy-validation
                  class="mx-auto"
                  @submit.prevent="sendEmail"
                >
                  <v-text-field
                    name="name"
                    v-model="name"
                    :rules="text"
                    label="Name"
                    required
                  ></v-text-field>
                  <v-text-field
                    name="email"
                    v-model="email"
                    :rules="text"
                    label="E-mail"
                    required
                  ></v-text-field>
                  <v-textarea
                    name="message"
                    v-model="message"
                    :rules="text"
                    label="text"
                    required
                  ></v-textarea>
                  <v-div class="mx-auto">
                    <!-- <v-btn color="success" class="mr-16" type="submit" value="Send">
                      Kirim
                    </v-btn> -->
                    <input type="submit" value="Send" />
                  </v-div>
                </form>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>
      <!-- <v-footer dark padless class="mt-16">
        <v-card class="flex" flat tile>
          <v-card-title class="teal">
            <strong class="subheading"
              >Get connected with us on social networks!</strong
            >

            <v-spacer></v-spacer>

            <v-btn v-for="icon in icons" :key="icon" class="mx-4" dark icon>
              <v-icon size="24px">
                {{ icon }}
              </v-icon>
            </v-btn>
          </v-card-title>

          <v-card-text class="py-2 white--text text-center">
            {{ new Date().getFullYear() }} — <strong>hilmisatrio</strong>
          </v-card-text>
        </v-card>
      </v-footer> -->
      <v-footer dark padless class="mt-16">
        <v-card
          tile
          flat
          width="100%"
          color="black"
          dark
          height="5rem"
          class="d-flex align-center justify-center"
        >
          &copy; 2022 powered by vue js & vuetify
        </v-card>
      </v-footer>
    </v-app>
  </div>
</template>
<script src="https://smtpjs.com/v3/smtp.js"></script>
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase.js"></script>

<script>
import colors from "vuetify/lib/util/colors";
import Vue from "vue";
import emailjs from "emailjs-com";

export default {
  name: "App",

  data: () => ({
    drawer: false,
    tab: null,
    image_school: require("./assets/riwayatpendidikan.svg"),
    image_java: require("./assets/java.png"),
    image_php: require("./assets/php.png"),
    image_kotlin: require("./assets/kotlin.png"),
    image_vue: require("./assets/veu.png"),
    image_sql: require("./assets/database.png"),
    image_html: require("./assets/html-5.png"),
    image_css: require("./assets/css-3.png"),
    image_profil: require("./assets/profil.png"),
    image_logo: require("./assets/logo-web.png"),
    name: "",
    email: "",
    message: "",
    // items :[
    //   {
    //     title : "Home",
    //     action : "home_menu"
    //   },
    //    {
    //     title : "Tentang saya",
    //     action : "about_menu"
    //   },
    //    {
    //     title : "Keahlian",
    //     action : "skill_menu"
    //   },

    // ],
    items: ["Home", "Tentang saya", "Keahlian", "Portfolio", "Hubungi saya"],
    icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
    pages: [
      "home_menu",
      "about_menu",
      "skill_menu",
      "portfolio_menu",
      "contact_menu",
    ],
    data_portfolio: [
      {
        no: "1",
        title: "Keppoya Note Application",
        image_portfolio: require("./assets/keppoya_note_app.png"),
        text:
          "Keppoya Note Application adalah sebuah aplikasi pencatatan berbasis mobile android. Aplikasi ini didukung dengan sistem database, sehingga data yang dimasukan oleh user akan tersimpan kedalam file system device tersebut." +
          "Terdapat beberapa fitur pada aplikasi ini, seperti jam, tanggal, menulis, mengubah, dan menghapus data. Aplikasi ini terlihat simpel tanpa mengurangi esensi sehingga cocok digunakan oleh siapapun. Selain itu terdapat juga fitur yang tidak kalah penting yaitu star, cara kerja fitur tersebut" +
          " jika user menggeser menu star maka catatan tersebut akan menjadi prioritas dengan tanda bintang. Keppoya Note App dapat di install dengan kriteria device minimal android versi 8.1 (oreo), namun versi tersebut dapat diturunkan lagi sesuai dengan kebutuhan user." +
          "Bahasa yang digunakan dalam pembuatan applikasi ini adalah Kotlin. Penggunaan bahasa kotlin dipilih karena lebih up to date dan mudah dipahami oleh developer. Tools yang digunakan adalah Android Studio",
      },
    ],
  }),
  theme: {
    themes: {
      light: {
        primary: colors.red.darken1, // #E53935
        secondary: colors.red.lighten4, // #FFCDD2
        accent: colors.indigo.base, // #3F51B5
      },
    },
  },
  methods: {
    sendEmail(e) {
      try {
        emailjs.sendForm(
          "service_8juuwog",
          "template_yvdnl7h",
          e.target,
          "AGsSqlCGPwUr_oYhI",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
        alert(
          "Pesan anda telah dikirim melalui email. terima kasih, " +
            this.name +
            "👋"
        );
      } catch (error) {
        console.log({ error });
      }
      // Reset form field
      this.name = "";
      this.email = "";
      this.message = "";
    },
    fb() {
      window.location.href =
        "https://www.facebook.com/muhamadhilmisatrio.satrio";
    },
    ig() {
      window.location.href = "https://www.instagram.com/hilmisatrio";
    },
    github() {
      window.location.href = "https://github.com/hilmisatrio";
    },
    linkedin() {
      alert("belum tersedia 🙏");
    },
    wa() {
      alert("belum tersedia 🙏");
    },
    contact_menu() {
      window.location.href = "/#contact";
    },
    about_menu() {
      window.location.href = "/#aboutme";
    },
    skill_menu() {
      window.location.href = "/#skill";
    },
    portfolio_menu() {
      window.location.href = "/#portfolio";
    },
    home_menu() {
      window.location.href = "/#home";
    },
    github_keppoya_note(){
      window.location.href = "https://github.com/hilmisatrio/Keppoya-Note-Application";
    },
  },
  mounted() {},
};
</script>
<style>
#app {
  scroll-behavior: smooth;
}
template {
  scroll-behavior: smooth;
}
#title {
  margin-right: 20px;
}
input[type="submit"] {
  background-color: #4caf50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
input[type="submit"]:hover {
  background-color: #b8c7b9;
}
#title-contact {
  color: grey;
}
#title-web {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  color: #20c420;
}
</style>
