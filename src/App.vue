<template>
  <navbar :pages="pages"
           :navlinkclick="(index)=>activePage=index"
           :active-page="activePage">

  </navbar>

  <pageview :page="pages[activePage]"></pageview>
</template>
<script>
import pageview from "@/components/pageview.vue";
import navbar from "@/components/navbar.vue";
export default{
  components:{
    pageview,navbar
  },
  data(){
    return{
      activePage:0,
      pages:[
        {
          link: {text:'Home',url:'index.html'},
          pageTitle:'Home',
          contenue: 'bienvenue dans le monde magnifique de vuejs',
        },
        {
          link: {text:'Contact ',url:'Contact.html'},
          pageTitle:'Contact',
          contenue: 'le contenue principale sera ici',
        },

        {
          link: {text:'à propos',url:'About.html'},
          pageTitle:'About',
          contenue: "la page d'à propos",
        }
      ],
    };
  },
}
</script>