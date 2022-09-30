.<template>
  <div class="home">
    <div class="card-body">
      <div class="our-staffs" v-for="(staff, index) in staffs" :key="index">
        <p class="details-text">Name: {{ staff.name }}</p>
        <p class="details-text">Gender:{{ staff.gender }}</p>
        <p class="details-text">Role: {{ staff.role }}</p>
        <p class="details-text">complexion: {{ staff.complexion }}</p>
      </div>
    </div>

    <div class="word">{{ word }}</div>

    <div class="count-box">
      <h1 class="count-text">count is: {{ count }}</h1>
      <button class="btn" @click="increseCount">count</button>
    </div>

    <div class="countries-holder">
      <div class="country">
        <div class="img">
          <img class="picture" src="" alt="" />
        </div>
        <div class="details"></div>
      </div>
    </div>
  </div>
</template>

<script>
import { computed } from '@vue/runtime-core';
// @ is an alias to /src


export default {
  name: 'HomeView',
  components: {
    
  },

  data() {
    return{
      staffs: [
        {name: 'musa adamu', gender: 'male', role:'web developer', complexion: 'dark skinned' },
        {name: 'goodness adeeyo', gender: 'female', role:'back-end developer', complexion: 'choco skinned' },
        {name: 'great pam', gender: 'male', role:'team motivator', complexion: 'dark skinned' },
        {name: 'joshua hycent', gender: 'male', role:'full-stack developer', complexion: 'senior front-end developer' },
        {name: 'victor Essien', gender: 'male', role:'dev ops', complexion: 'dark skinned' },
        {name: 'Anibiet peters', gender: 'female', role:'ui/ux designer', complexion: 'dark skinned' },
        {name: 'ikey ', gender: 'male', role:'project manager', complexion: 'light-skinned' }
      ],

      word:  ' i am learning more about vue',

      count: 0,
   }
  },


methods: {
   increseCount(){
      this.count++;
      if (this.count < 7) {

        document.querySelector(".count-text").classList.add("black");
        // document.querySelector(".count-text").classList.remove("red");

      }else if (this.count <= 10) {
        
        document.querySelector(".count-text").classList.remove("black");
        document.querySelector(".count-text").classList.add("green");
        
      }else {
        document.querySelector(".count-text").classList.remove("green");
        document.querySelector(".count-text").classList.add("red");

      }
    },
}
       

}




</script>

<style>
.card-body {
  height: fit-content;
  width: 100%;
  display: flex;
  flex: wrap;
  border: 1px solid black;
  margin-top: 50px;
  background-color: #f5fffa;
}
.our-staffs {
  height: fit-content;
  width: 200px;
  background-color: #ffffff;
  margin: 10px;
  padding: 10px 20px 10px 20px;
  border: 1px solid black;
  border-radius: 2px;
  background-color: rgb(153, 228, 203);
}

.details-text {
  font-family: sans-serif;
  font-size: 15px;
  text-transform: capitalize;
}

.word {
  text-align: center;

  font-family: sans-serif;
  font-size: 20px;
  margin-top: 20px;
  margin-bottom: 20px;
  text-transform: capitalize;
}

.count-box {
  flex-direction: column;
  margin: 0 auto;
  width: 150px;
  height: 50px;
  border: 1px solid black;
}

.btn {
  background-color: blue;
  color: #ffffff;
  outline: none;
}

.count-text {
  font-size: 20px;
  font-family: sans-serif;
  /* margin: 50px 50px; */
}

.countries {
  width: 100%;
  height: fit-content;
  display: flex;
  flex-wrap: wrap;
}

.country {
  height: 60vh;
  width: 25%;
  background-color: rgb(105, 105, 161);
  margin: 20px 15px 15px 15px;
}

.img {
  width: 100%;
  height: 30vh;
  background-color: red;
}

.picture {
  /* object-fit: cover;
  width: 100%; */
}

.black {
  color: black;
}

.red {
  color: red;
  /* background-color: red; */
}

.green {
  color: green;
  /* background-color: green; */
}
</style>
