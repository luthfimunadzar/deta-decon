<template>
  <div>    
    <Header />

    <div class="about-wrap">
      <b-container>
        <b-row>
          <b-col lg="12">
            <div class="info">
              <h4>Awards</h4>
              
              <div class="project-wrap px-0 py-0">
                <b-container class="px-0">
                  <b-row no-gutters v-if="dataShow.length != 0">
                      <b-col md="6" sm="6" v-for="data in dataShow" :key="data.id">
                          <div class="image" :style="{ backgroundImage: 'url(' + data.img + ')'}" @click="openGallery(data.id)">
                              <div class="wrap">
                                  <span>{{ data.year }}</span>
                                  <h5>{{ data.nama  }}</h5>
                              </div>
                          </div>
                      </b-col>
                  </b-row>
                </b-container>
              </div>
            </div>
          </b-col>
          <b-col lg="12">
            <div class="info">
              <h4>Business Certifications</h4>

              <div class="achievement-item">
                <h5>Certificate Of Business Entity Other Consultancy Services</h5>

                <h6>Classification Of Business Fields : Other Consultancy</h6>
                <table class="table table-bordered">
                  <thead>
                    <tr>
                      <th>Subclassification Code</th>
                      <th>Subclassification</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>KL401</td>
                      <td>Environmental Consultancy Services</td>
                    </tr>
                    <tr>
                      <td>KL403</td>
                      <td>Project Management Services Related to Building Construction</td>
                    </tr>
                    <tr>
                      <td>KL406</td>
                      <td>Project Management Services Related to Other Civil Engineering Construction Work</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div class="achievement-item">
                <hr/>
                <h5>Certificate of Business Entity Construction Planner Services</h5>

                <h6>Classification Of Business Fields :	Spatial Planning</h6>
                <table class="table table-bordered">
                  <thead>
                    <tr>
                      <th>Subclassification Code</th>
                      <th>Subclassification</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>PR103</td>
                      <td>Planning and Design Services for Building and Landscape Environment</td>
                    </tr>
                  </tbody>
                </table>

                <h6>Classification Of Business Fields : 	Architectural Planning</h6>
                <table class="table table-bordered">
                  <thead>
                    <tr>
                      <th>Subclassification Code</th>
                      <th>Subclassification</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>AR101</td>
                      <td>Architectural Advice and Design Services</td>
                    </tr>
                    <tr>
                      <td>AR102</td>
                      <td>Architectural Design Services</td>
                    </tr>
                    <tr>
                      <td>AR103</td>
                      <td>Building Appraisal and Maintenance Service Services</td>
                    </tr>
                    <tr>
                      <td>AR104</td>
                      <td>Interior Design Services</td>
                    </tr>
                  </tbody>
                </table>

                <h6>Classification Of Business Fields : 	Engineering Planning</h6>
                <table class="table table-bordered">
                  <thead>
                    <tr>
                      <th>Subclassification Code</th>
                      <th>Subclassification</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>RE101</td>
                      <td>Engineering Consultancy and Consultancy Services</td>
                    </tr>
                    <tr>
                      <td>RE102</td>
                      <td>Engineering Design Services for Foundation and Building Structure Construction</td>
                    </tr>
                    <tr>
                      <td>RE104</td>
                      <td>Engineering Design Services for Civil Engineering Works in Transportation</td>
                    </tr>
                    <tr>
                      <td>RE105</td>
                      <td>Engineering Design Services for Mechanical and Electrical Works in Buildings</td>
                    </tr>
                  </tbody>
                </table>
              </div>

              <div class="achievement-item">
                <hr/>
                <h5>Certificate of Construction Supervision Services Business Entity				</h5>

                <h6>Classification Of Business Fields : 	Engineering Oversight</h6>
                <table class="table table-bordered">
                  <thead>
                    <tr>
                      <th>Subclassification Code</th>
                      <th>Subclassification</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>RE201</td>
                      <td>Building Construction Work Supervisor Services</td>
                    </tr>
                  </tbody>
                </table>

                <h6>Classification Of Business Fields : 	Architectural Supervision</h6>
                <table class="table table-bordered">
                  <thead>
                    <tr>
                      <th>Subclassification Code</th>
                      <th>Subclassification</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr>
                      <td>AR201</td>
                      <td>Contract Administration Supervision Services</td>
                    </tr>
                  </tbody>
                </table>
              </div>
            </div>
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
          nama: 'Award for the provision of sports facilities and infrastructure in the 2018 Asian Games XVII from the Vice President of the Republic of Indonesia M. Jusuf Kalla',
          year: '2018',
          img: '/awards.jpeg',
        },
      ],
    }
  },
  created() {
    this.dataShow = this.dataProject
  },
  methods: {
    openGallery(params){
      let tempImage = this.dataProject.filter( obj => obj.id === params);

      this.image[0].thumb = tempImage[0].img;
      this.image[0].src = tempImage[0].img;
      this.image[0].caption = tempImage[0].year + " " + tempImage[0].nama;
      this.$refs.lightbox.showImage(0)
    }
  },
  head () {
    return {
      title: 'Deta Decon - Awards & Business Certifications',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'description', name: 'description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
        { hid: 'og:title', name: 'og:title', content: 'Deta Decon - Awards & Business Certifications' },
        { hid: 'keywords', name: 'keywords', content: 'Deta Decon, PT Deta Decon, Deta, Decon, Construction, Civil, Indonesia'},
        { hid: 'og:description', name: 'og:description', content: 'PT Deta Decon is a structural & civil consulting firm based in Jakarta, Indonesia. Founded in 1994, the 26-year old company has delivered excellence through the area of expertise in building structure, building skin, building performance, construction support services, property loss consulting and sustainability. ' },
      ]
    }
  },
}
</script>
