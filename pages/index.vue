<template>
  <div class="pt-5">
    <div class="row justify-content-center">
      <h3 class="border-bottom pb-2 mb-5 full bold">Top Workers</h3>
      <div class="inner-container">
        <div class="row">
          <div class="row full mb-5">
            <div class="col-6 d-column">
              <h5 class="border-bottom pb-2 mb-3">Sort By Rating</h5>
              <button class="sort-btn" @click='sortByAscending'>Lowets-Highest</button>
              <button class="sort-btn" @click='sortByDescending'>Highest-Lowets</button>
            </div>
            <div class="col-6 d-column">
              <h5 class="border-bottom pb-2 mb-3">Filter By Skill (not working yet)</h5>
              <button class="sort-btn">Cleaining</button>
              <button class="sort-btn">Furniture Moving</button>
              <button class="sort-btn">Repairing</button>
              <button class="sort-btn">Help Moving</button>
              <button class="sort-btn">Car Washing</button>

            </div>
          </div>
        </div>
        <div class="row worker-list">
          <transition-group name="flip-list">
            <Worker v-for='worker in workers' :key='worker' :worker='worker'/>
          </transition-group>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import WorkerCard from '@/components/WorkerCard.vue'

export default {
  transitions : 'slide-up',
  components : {
    Worker : WorkerCard
  },
  data() {
    return {
      workers : [
        {
          name :'Ruhin',
          surname : 'Shukurlu',
          profile_img : 'https://images.pexels.com/photos/220453/pexels-photo-220453.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['cleaining','furniture-moving'],
          rating : 4
        },
        {
          name :'Elchin',
          surname : 'Rahimli',
          profile_img : 'https://images.unsplash.com/photo-1529665253569-6d01c0eaf7b6?ixid=MXwxMjA3fDB8MHxzZWFyY2h8M3x8cHJvZmlsZXxlbnwwfHwwfA%3D%3D&ixlib=rb-1.2.1&w=1000&q=80',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['repairing'],
          rating : 7
        },
        {
          name :'Ferman',
          surname : 'Guliyev',
          profile_img : 'https://media.istockphoto.com/photos/portrait-of-a-cheerful-young-man-picture-id545262108?k=6&m=545262108&s=612x612&w=0&h=atYvV2j41NyaDjFZAPnUrkaes1DNwMzFeRIOY4XhpAo=',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['Help-moving','furniture-moving'],
          rating : 8
        },
        {
          name :'Aidan',
          surname : 'Atakishieva',
          profile_img : 'https://www.rd.com/wp-content/uploads/2017/09/01-shutterstock_476340928-Irina-Bg.jpg',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['Car Washing','furniture-moving'],
          rating : 7
        },
        {
          name :'Azad',
          surname : 'Shahbazov',
          profile_img : 'https://expertphotography.com/wp-content/uploads/2020/08/social-media-profile-photos-3.jpg',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['cleaining'],
          rating : 9
        },
        {
          name :'Amir',
          surname : 'Namazov',
          profile_img : 'https://widgetwhats.com/app/uploads/2019/11/free-profile-photo-whatsapp-4.png',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['cleaining','furniture-moving'],
          rating : 5
        },

        {
          name :'Asgar',
          surname : 'Asgarov',
          profile_img : 'https://nugrowth.com/wp-content/uploads/2015/03/kyle-tillar2.png',
          bio : ` mollitia voluptatibus quas optio corrupti veritatis aliquam obcaecati
                sequi neque? Sed in neque possimus corrupti sun`,
          skills : ['furniture-moving'],
          rating : 7  
        }
      ]
    }
  },
  methods : {
    sortByAscending(){
      this.workers.sort((a,b)=> a.rating > b.rating ? 1 : -1)
    },
    sortByDescending(){
      this.workers.sort((a,b)=> a.rating < b.rating ? 1 : -1)
    },
    filterBySkill(e){

    }
  }
};
</script>

<style>

.flip-list-move {
  transition: transform 1s;
}

.full{
  width: 100%;
}

.sort-btn{
  border: 1px solid #ccc;
  padding: 5px 20px;
  margin-bottom: 10px;
}
.sort-btn.active{
  border-color: green;
}

.worker-list>span{
  display: flex;
    flex-wrap: wrap;
    margin-right: -15px;
    margin-left: -15px;
}

.list-complete-item {
  transition: all 0.8s ease;
  display: inline-block;
  margin-right: 10px;
}

.list-complete-enter-from,
.list-complete-leave-to {
  opacity: 0;
  transform: translateY(30px);
}

.list-complete-leave-active {
  position: absolute;
}
</style>
