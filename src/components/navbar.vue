<template>
  <nav class="navbar navbar-expand-lg "
       :class="[ `navbar-${theme}`,`bg-${theme}`,'navbar-lg','navbar']" >

    <div class='collapse navbar-collapse' id='navbarSupportedContent'>
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active" v-for="(page,index) in pages" :key="index">
          <a class="nav-link"
             :class="{active: activePage===index}"
             :href="page.link.url"
             aria-current="page"

             @click.prevent= "navlinkclick(index)"
          >{{page.link.text}}</a>
        </li>
      </ul>

      <form class="d-flex">
        <button class="btn btn-primary"
                @click.prevent="change()"
        > toggle</button>

      </form>
    </div>

  </nav>

</template>
<script>
export default {
  props: ['pages','activePage','navlinkclick'],

  data()
  {
    return{
      theme:'dark'
    }
  },
  methods :{
    change(){
      let theme='light';
      if(this.theme==='light')
      {
        this.theme='dark'
      }
      else
        this.theme=theme;
    }
  }

}
</script>