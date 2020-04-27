<template>
  <div>    
    <Header />

    <div class="opt-project">
        <b-container>
            <b-row>
                <b-col>
                    <div class="title">
                        Project Section
                    </div>
                    <div class="dropdown-group">
                        <b-dropdown right>
                            <template v-slot:button-content>
                                <span class="d-md-block d-none">Investigation and<br/>Building Audits</span>
                                <span class="d-md-none d-block">Investigation and Building Audits</span>
                            </template>
                            <b-dropdown-item @click="filtered('Investigation and Building Audits')">Investigation and Building Audits</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Investigation and Building Audits')">Investigation and Building Audits</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Investigation and Building Audits')">Investigation and Building Audits</b-dropdown-item>
                        </b-dropdown>
                        <b-dropdown right>
                            <template v-slot:button-content>
                                <span class="d-md-block d-none">Supervision and<br/>Construction Management</span>
                                <span class="d-md-none d-block">Supervision and Construction Management</span>
                            </template>
                            <b-dropdown-item @click="filtered('Supervision and Construction Management')">Supervision and Construction Management</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Supervision and Construction Management')">Supervision and Construction Management</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Supervision and Construction Management')">Supervision and Construction Management</b-dropdown-item>
                        </b-dropdown>
                        <b-dropdown right>
                            <template v-slot:button-content>
                                <span class="d-md-block d-none">Architecture Planning<br/>and Design</span>
                                <span class="d-md-none d-block">Architecture Planning and Design</span>
                            </template>
                            <b-dropdown-item @click="filtered('Architecture Planning and Design')">Architecture Planning and Design</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Architecture Planning and Design')">Architecture Planning and Design</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Architecture Planning and Design')">Architecture Planning and Design</b-dropdown-item>
                        </b-dropdown>
                    </div>
                </b-col>
            </b-row>
        </b-container>
    </div>

    <div class="search">
      <b-container>
        <b-row>
          <b-col>
            <b-form inline class="form-search">
              <label for="" class="mr-3">Filter Project</label>
              <b-form-input v-model="search" placeholder="Cari Berdasarkan Nama Project"></b-form-input>
              <b-button variant="primary" @click.prevent="formSearch()">Cari</b-button>
            </b-form>
          </b-col>
        </b-row>
      </b-container>
    </div>

    <div class="project-wrap">
      <b-container>
        <b-row v-if="dataShow.length != 0">
            <b-col md="4" sm="6" v-for="data in dataShow" :key="data.id">
                <div class="image" :style="{ backgroundImage: 'url(' + data.img + ')'}" @click="openGallery(data.id)">
                    <div class="wrap">
                        <span>{{ data.year }}</span>
                        <h5>{{ data.nama  }}</h5>
                        <h6>{{ data.cat  }}</h6>
                    </div>
                </div>
            </b-col>
        </b-row>
        <b-row v-else>
          <b-col class="text-center">
            <h5 class="mb-0">Hasil Pencarian "{{ this.keyword }}" Tidak Ditemukan</h5>
          </b-col>
        </b-row>
      </b-container>
    </div>
    
    <Footer />

    <client-only>
      <light-box ref="lightbox" :media="image" :show-caption="true" :show-light-box="false" :show-thumbs="false"/>
    </client-only>
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
      dataShow: [],
      keyword: "",
      image: [
        { 
          thumb: '',
          src: '',
          caption: '',
        },
      ],
      dataProject: [
          {
              id: 1,
              nama: 'Gelora Bung Karno',
              year: '2017 - 2018',
              cat: 'Supervision and Construction Management',
              img: '/project-1.jpg',
          },
          {
              id: 2,
              nama: 'Athlete Villages Kemayoran (Blok 10D2) Tower 3,4',
              year: '2017 - 2018',
              cat: 'Supervision and Construction Management, Architecture Planning and Design',
              img: '/project-2.jpg',
          },
          {
              id: 3,
              nama: 'Kampus UIN Suska Riau',
              year: '2005 - 2008',
              cat: 'Supervision and Construction Management',
              img: '/project-3.jpg',
          },
          {
              id: 4,
              nama: 'UIN Raden Patah Palembang',
              year: '2017 - 2020',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-4.jpg',
          },
          {
              id: 5,
              nama: 'UIN Sumatera Utara',
              year: '2017 - 2020',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-5.jpg',
          },
          {
              id: 6,
              nama: 'UIN Sunan Ampel Surabaya',
              year: '2012 - 2013',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-6.jpg',
          },
          {
              id: 7,
              nama: 'UIN Sultan Taha Jambi',
              year: '2018',
              cat: 'Detail Engineering Design',
              img: '/project-7.jpg',
          },
          {
              id: 8,
              nama: 'Bank Indonesia Building',
              year: '2009',
              cat: 'Structural Design',
              img: '/project-8.jpg',
          },
          {
              id: 9,
              nama: 'Sarana Wisma Islamic Centre',
              year: '2010',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-9.jpg',
          },
      ],
      search: "",
    }
  },
  created() {
    this.dataShow = this.dataProject
  },
  methods: {
    filtered(params){
      let tempFiltered = this.dataProject.filter( e => e.cat.toLowerCase().includes(params.toLowerCase()));

      this.dataShow = tempFiltered
    },
    formSearch(){
      this.keyword = this.search
      let tempSearch = this.dataProject.filter( obj => obj.nama.toLowerCase().includes(this.search.toLowerCase()))

      this.dataShow = tempSearch
    },
    openGallery(params){
      let tempImage = this.dataProject.filter( obj => obj.id === params);

      this.image[0].thumb = tempImage[0].img;
      this.image[0].src = tempImage[0].img;
      this.image[0].caption = tempImage[0].year + " " + tempImage[0].nama + "<br/>" + tempImage[0].cat;
      this.$refs.lightbox.showImage(0)
    }
  },
  head () {
    return {
      title: 'Project | Deta Decon',
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
