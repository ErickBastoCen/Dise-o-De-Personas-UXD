<script>
import axios from 'axios'



let API_URL = 'http://isclab.com.mx/personasuxd/getPersonasUxd.php?${id}'
console.log(API_URL)

export default {
    props: ['id'],
  data() {
    return {
      info: [],
      personajes: [],
      cont:2

    }
  },

  mounted() {
    axios.get(API_URL)

      .then((response) => {
        this.info = response.data.info;
        this.personajes = response.data.results;
      })

  } 
}
</script>

<template>
    <div >
        <h2>Hola</h2>
    </div>
</template>