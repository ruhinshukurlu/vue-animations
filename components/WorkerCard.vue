<template>
  <div class="col-4 mb-4">
    <div class="worker-item">
      <div class="card" >
        <div class="d-flex p-3">
          <img :src="worker.profile_img" class="card-img-top" alt="..." />
          <div class="d-column ml-3">
            <h5 class="bold border-bottom pb-2 mb-3">{{ worker.name }} {{ worker.surname }}</h5>
            <div class="d-flex align-items-center rating-box">
                <span>Rating : </span>
                <span> &nbsp {{ worker.rating }} / 10</span>
                <RatingStar />
            </div>
          </div>
        </div>
        <div class="card-body">
          <div class="d-column">
            <span class="featured-skills-header border-bottom bold pb-1 mb-3">Featured Skills</span>
            <div class="d-flex tasker-category full justify-content-between" v-for="skill in worker.skills" :key='skill'>
              <label class="category-name">{{skill}}</label>
              <span class="category-price">$38.82/hr</span>
            </div>
          </div>
          <div class="card-text d-column">
            <span class="full border-bottom pb-1 mb-2 bold"
              >I'm the right person for the job:</span
            >
            <p>{{ worker.bio }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import RatingStar from "@/components/RatingStar";
export default {
  components: {
    RatingStar,
  },
  props: ["worker"],
};
</script>
<style >
.worker-item img {
    width: 150px;
    height: 150px;
    border-radius: 10px;
  object-fit: cover;
}

.card-title {
  font-weight: bold;
}

.worker-item{
    /* box-shadow: 0px 0px 30px -11px rgba(0,0,0,0.75);
-webkit-box-shadow: 0px 0px 30px -11px rgba(0,0,0,0.75);
-moz-box-shadow: 0px 0px 30px -11px rgba(0,0,0,0.75); */
height: 100%;
}

.card{
    height: 100%;
    border-color: rgb(39, 241, 208);
    border-width: 2.5px;
    border-radius: 10px;
}

.rating-box span {
  font-weight: bold;
  display: flex;
  align-items: center;
}

.category-name{
    border: 1px solid rgb(44, 236, 204);
    padding: 5px 10px;
    border-radius: 5px;
}
</style>