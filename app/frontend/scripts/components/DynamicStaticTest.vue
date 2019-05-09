<template>
<main id="home">
</main>

</template>

<script>
import {mapState} from 'vuex'
import axios from 'axios'

export default {
    props:[
      'routeConfig',
     // 'tabsConfig',
      // 'templateURL'
    ],
  data: () => {
    return   {
      rawHtml : ''
    }
  },
  computed: {
    ...mapState({
      user: 'user'
    })
  },
  mounted(){
    // here we go fetch the raw HTML content of a webpage
    // let template_url = (this.templateURL) ? this.templateURL : 'https://co-demos.com/error'
    // let head = {
    //   headers: {
    //     // 'Access-Control-Allow-Origin': '*',
    //     'accept' : 'text/html',
    //   }
    // }
    // axios.get(template_url, head)
    //   .then( (response) => {
    //     // console.log(response);
    //     this.rawHtml = (response && response.data) ? response.data : '<br><br>there is an Error <br><br>'}
    //   )
    //   .catch( (err) => {this.rawHtml = '<br><br>there is an <strong> Error </strong><br><br>'} )
    //let testScript = document.createElement('script');
    //testScript.setAttribute('src', 'https://cdn.jsdelivr.net/npm/bulma-carousel@4.0.4/dist/js/bulma-carousel.min.js');
    //testScript.setAttribute('src', 'https://cdn.jsdelivr.net/gh/co-demos/cis-data/scripts/home.js');
    //  document.head.appendChild(testScript);
    //let ext_CSS_url_1 = "https://cdnjs.cloudflare.com/ajax/libs/bulma/0.6.2/css/bulma.min.css"; 
    //let ext_script_url_2 = "https://cdn.jsdelivr.net/gh/CBalsier/test-content/scripts/test_who.js";
    //console.log(ext_script_url_1, ext_script_url_2, " is script");
    //let extCSS1 = document.createElement('link')
    //extCSS1.setAttribute('rel', 'stylesheet');
    //extCSS1.setAttribute('href', ext_CSS_url_1);
    let ext_script_url_2 = "./static/test_script.js";
    let extScript2 = document.createElement('script');
    extScript2.setAttribute('src', ext_script_url_2);
    document.head.appendChild(extScript2);

   //}
    },
    methods: {
      goBack(e){
        e.preventDefault()
        this.$router.back()
      }
    }
  }
</script>
