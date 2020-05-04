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
          img: '/people1.jpg',
          nama: 'Ir. Chairul Basri Nasution',
          jabatan: 'Direktur Utama',
          exp: '40 Years'
        },
        {
          id: 2,
          img: '/people2.jpg',
          nama: 'Ir. Mardiana Daoed',
          jabatan: 'Direktur',
          exp: '38 Years'
        },
        {
          id: 3,
          img: '/people3.jpg',
          nama: 'Ir. Azwar Muchtasar',
          jabatan: 'Team Leader, TA Struktur, TA Manajemen Konstruksi',
          exp: '35 Years'
        },
        {
          id: 4,
          img: '/people4.jpg',
          nama: 'Ir. Devy Kartika',
          jabatan: 'TA. Arsitektur',
          exp: '25 Years'
        },
        {
          id: 5,
          img: '/people5.jpg',
          nama: 'Ir. Farida Ansuria',
          jabatan: 'TA. Struktur',
          exp: '27 Years'
        },
        {
          id: 6,
          img: '/people6.jpg',
          nama: 'Ir. Sudiro',
          jabatan: 'TA. Estimator',
          exp: '30 Years'
        },
        {
          id: 7,
          img: '/people7.jpeg',
          nama: 'Ir. Djadjuli Hasjim',
          jabatan: 'TA. Mekanikal',
          exp: '30 Years'
        },
        {
          id: 8,
          img: '/people8.jpg',
          nama: 'Ir. Fayandi Zakir',
          jabatan: 'TA. Arsitektur',
          exp: '31 Years'
        },
        {
          id: 9,
          img: '/people9.jpg',
          nama: 'Yusuf Munawar, ST.',
          jabatan: 'TA. Manajemen Konstruksi',
          exp: '25 Years'
        },
        {
          id: 10,
          img: '/people10.jpg',
          nama: 'Rois, ST.',
          jabatan: 'TA. Elektrikal',
          exp: '18 Years'
        },
        {
          id: 11,
          img: '/people11.jpg',
          nama: 'Wahyu Raharjo, ST.',
          jabatan: 'TA. Manajemen Mutu',
          exp: '21 Years'
        },
      ]
    }
  },
  head () {
    return {
      title: 'About | Deta Decon',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
        { hid: 'og:title', name: 'og:title', content: 'Deta Decon' },
        { hid: 'og:description', name: 'og:description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
      ]
    }
  },
}
</script>
