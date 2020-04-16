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
                <div class="image" :style="{ backgroundImage: 'url(' + data.img + ')'}">
                    <div class="wrap">
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
      dataProject: [
          {
              id: 1,
              nama: 'Project 1',
              cat: 'Investigation and Building Audits',
              img: '/project-1.jpg',
          },
          {
              id: 2,
              nama: 'Project 2',
              cat: 'Investigation and Building Audits',
              img: '/project-2.jpg',
          },
          {
              id: 3,
              nama: 'Project 3',
              cat: 'Investigation and Building Audits',
              img: '/project-3.jpg',
          },
          {
              id: 4,
              nama: 'Project 4',
              cat: 'Supervision and Construction Management',
              img: '/project-4.jpg',
          },
          {
              id: 5,
              nama: 'Project 5',
              cat: 'Supervision and Construction Management',
              img: '/project-5.jpg',
          },
          {
              id: 6,
              nama: 'Project 6',
              cat: 'Supervision and Construction Management',
              img: '/project-6.jpg',
          },
          {
              id: 7,
              nama: 'Project 7',
              cat: 'Architecture Planning and Design',
              img: '/project-7.jpg',
          },
          {
              id: 8,
              nama: 'Project 8',
              cat: 'Architecture Planning and Design',
              img: '/project-8.jpg',
          },
          {
              id: 9,
              nama: 'Project 9',
              cat: 'Architecture Planning and Design',
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
      let tempFiltered = this.dataProject.filter( e => e.cat === params);

      this.dataShow = tempFiltered
    },
    formSearch(){
      this.keyword = this.search
      let tempSearch = this.dataProject.filter( obj => obj.nama.toLowerCase().includes(this.search.toLowerCase()))

      this.dataShow = tempSearch
    }
  }
}
</script>
