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
                            <b-dropdown-item @click="filtered('Structure Investigation')">Structure Investigation</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Building Audits')">Building Audits</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Structure Strengthening & Design')">Structure Strengthening & Design</b-dropdown-item>
                        </b-dropdown>
                        <b-dropdown right>
                            <template v-slot:button-content>
                                <span class="d-md-block d-none">Supervision and<br/>Construction Management</span>
                                <span class="d-md-none d-block">Supervision and Construction Management</span>
                            </template>
                            <b-dropdown-item @click="filtered('Project Management & Supervision Consultant')">Project Management & Supervision Consultant</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Construction Management')">Construction Management</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Supervision Consultant')">Supervision Consultant</b-dropdown-item>
                        </b-dropdown>
                        <b-dropdown right>
                            <template v-slot:button-content>
                                <span class="d-md-block d-none">Architecture Planning<br/>and Design</span>
                                <span class="d-md-none d-block">Architecture Planning and Design</span>
                            </template>
                            <b-dropdown-item @click="filtered('Detail Engineering Design')">Detail Engineering Design</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Architecture Design')">Architecture Design</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Structure Design')">Structure Design</b-dropdown-item>
                            <b-dropdown-item @click="filtered('Mechanical, Electrical and Plumbing Design')">Mechanical, Electrical and Plumbing Design</b-dropdown-item>
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
            <b-form inline class="form-search" @submit.prevent="formSearch()">
              <label for="" class="mr-3">Filter Project</label>
              <b-form-input v-model="search" placeholder="Cari Berdasarkan Nama Project"></b-form-input>
              <b-button variant="primary" type="submit">Cari</b-button>
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
          // old
          {
              id: 1,
              nama: 'Gelora Bung Karno',
              year: '2017-2018',
              cat: 'Supervision and Construction Management',
              img: '/project-1.jpg',
          },
          {
              id: 2,
              nama: 'Athlete Villages Kemayoran (Blok 10D2) Tower 3,4',
              year: '2017-2018',
              cat: 'Supervision and Construction Management, Architecture Planning and Design',
              img: '/project-2.jpg',
          },
          {
              id: 3,
              nama: 'Management Construction & Supervision The Upgrading of Islamic University of Sultan Syarif Kasim (SUSKA) Project ',
              year: '2006-2008',
              cat: 'Construction Management',
              img: '/project-3.jpg',
          },
          {
              id: 4,
              nama: 'UIN Raden Patah Palembang',
              year: '2017-2020',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-4.jpg',
          },
          {
              id: 5,
              nama: 'UIN Sumatera Utara',
              year: '2017-2020',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-5.jpg',
          },
          {
              id: 6,
              nama: 'Project Management and Supervision Consultant of  UIN Sunan Ampel',
              year: '2013-2015',
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
              nama: 'Multifunction Koperbi Building Bank of Indonesia',
              year: '2008',
              cat: 'Detail Engineering Design (Public Buildings & Infra Structure)',
              img: '/project-8.jpg',
          },
          {
              id: 9,
              nama: 'Sarana Wisma Islamic Centre',
              year: '2010',
              cat: 'Project Management & Supervision Consultant',
              img: '/project-9.jpg',
          },
          // ded
          {
              id: 10,
              nama: 'The Upgrading and Development of The Semarang State University',
              year: '2013',
              cat: 'Detail Engineering Design (Educational Building)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 11,
              nama: 'The Upgrading Development Of State Islamic University Of Sunan Gunung Djati Bandung',
              year: '2010',
              cat: 'Detail Engineering Design (Educational Building)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 12,
              nama: 'University of Alauddin Makassar',
              year: '2007-2008',
              cat: 'Detail Engineering Design (Educational Building)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 13,
              nama: 'The Development and Upgrading of STAIN Malang Project',
              year: '2005',
              cat: 'Detail Engineering Design (Educational Building)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 14,
              nama: 'Detail Engineering Desain for Auditorium/ Multipurpose Building of The State University of Gorontalo.',
              year: '2011',
              cat: 'Detail Engineering Design (Educational Building)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 15,
              nama: 'Islamic Centre Jakarta',
              year: '2005, 2006, 2007',
              cat: 'Detail Engineering Design (Public Buildings & Infra Structure)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 16,
              nama: 'Master Plan & DED Of Menteng Park, Cental of Jakarta',
              year: '2006',
              cat: 'Detail Engineering Design (Public Buildings & Infra Structure)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 17,
              nama: 'Detail Engineering Desain of Training Centre of Pusdiklat Pajak, Ministry of Finance (2014), 11 th Floors + 1 Basement',
              year: '2014',
              cat: 'Detail Engineering Design (Public Buildings & Infra Structure)',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          // mk
          {
              id: 18,
              nama: 'Construction Management “Hotel Grandika Project – Blok M”',
              year: '2013-2014',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 19,
              nama: 'Construction Management of Continous Class III Hospital Building, RSUD Arifin Achmad',
              year: '2013',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 20,
              nama: 'Construction Management of Riau Province Development Office',
              year: '2012-2013',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 21,
              nama: 'Work on Construction Management of the Phase II Annex Building Renovation Project and Mosque PT. ASKES',
              year: '2010',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 22,
              nama: 'Construction Management of the Phase I Annex Building Renovation Project and Mosque PT. ASKES',
              year: '2009',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 23,
              nama: 'Construction Management Building Construction Work B Regional Office Directorate General of Customs and Excise, Jakarta',
              year: '2010',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 24,
              nama: 'PPM Building Construction Management Construction Work',
              year: '2009-2010',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 25,
              nama: 'Construction Management Construction Madrasa International Standard',
              year: '2009',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 26,
              nama: 'Construction Management Construction of East Jakarta Mayor Office Building Block C and D - 16 floors (multi years)',
              year: '2007-2009',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          {
              id: 27,
              nama: 'Construction Management of Riau Main Stadium Construction',
              year: '2008',
              cat: 'Construction Management',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          // PMSC
          {
              id: 28,
              nama: 'Project Management And Supervision Consultant, The Development and Upgrading of The State University of Jakarta (UNJ)',
              year: '2011-2013',
              cat: 'Project Management & Supervision Consultant',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          // Supervision
          {
              id: 28,
              nama: 'Rusunawa Supervision Development Work - 2 (PP10-17)',
              year: '2010-2011',
              cat: 'Supervision Consultant',
              img: 'https://place-hold.it/426x261?text=Project+Image',
          },
          // Building Audit
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
      this.keyword = params

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
