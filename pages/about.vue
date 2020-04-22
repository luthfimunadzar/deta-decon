<template>
  <div>    
    <Header />

    <div class="about-wrap">
      <b-container>
        <b-row>
          <b-col lg="12">
            <div class="info">
              <h4>Who we are</h4>

              <p>We are a collective of engineers, developers, architects, and planners working together to build a better future. Our firm, Deta Decon, is responsible for some of the Indonesia's most technically and environmentally advanced buildings and significant public spaces. Through mastery in Technical Expertise, our firm has maintaned its well-acknowledged reputation by succesfully provided the structural design for numerous of the government buildings, airports, state / grant universities, schools, apartments, residences, and corporate buildings throughout the land of Indonesia.</p>
            </div>
            
            <div class="info">
              <h4>People</h4>
  
              <b-row>
                <b-col cols="6" md="4" lg="2" v-for="people in peoples" :key="people.id">
                  <div class="board-item">
                    <span class="image" :style="{ backgroundImage: 'url(' + people.img + ')'}"></span>
                    <div class="text">
                      <h5>{{ people.nama }}</h5>
                      <h6>{{ people.jabatan }}</h6>
                      <span>Exp. {{ people.exp }}</span>
                    </div>
                  </div>
                </b-col>
              </b-row>
            </div>

            <div class="info">
              <h4>Career</h4>
              <p>
                DetaDecon offers a rewarding career experience, a collaborative interdisciplinary environment, and the opportunity to work on some of Indonesia’s most exciting and transformative engineering, and planning projects.
              </p>
              <p>
                Mail to: <a href="mailto:detadecon94@yahoo.com">detadecon94@yahoo.com</a> 
              </p>
              <p>Subject: Name_Job Application</p>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </div>
    
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'

export default {
  components: {
    Header,
    Footer
  },
  data() {
    return {
      peoples: [
        {
          id: 1,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 2,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 3,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 4,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 5,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 6,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 7,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 8,
          img: 'https://cdn2.iconfinder.com/data/icons/lil-silhouettes/2176/person13-512.png',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
      ]
    }
  },
  head () {
    return {
      title: 'About | Deta Decon',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 20-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
        { hid: 'og:title', name: 'og:title', content: 'Deta Decon' },
        { hid: 'og:description', name: 'og:description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 20-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
      ]
    }
  },
}
</script>
