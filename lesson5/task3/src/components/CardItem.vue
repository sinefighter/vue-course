<template>
  <div class="card mb-3">
    <div class="row g-0">
      <div class="col-md-4">
        <a :href="laptop.link">
          <img :src="laptop.image" class="img-fluid rounded-start" />
        </a>
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">
            <a :href="laptop.link">
              {{ laptop.name }}
            </a>
          </h5>
		  <p v-if="getEconomy">
			Ваша економія: <b style="color: red">{{ getEconomy }}</b>
		  </p>
		  <div class="price-old" v-if="laptop.priceOld">{{ laptop.priceOld }} грн</div>
		  <div class="price" :class="{'price-new': laptop.priceOld}">{{ laptop.price }} грн</div>

		  <div class="button">
			<a :href="laptop.link" class="btn btn-success">Купити</a>
		  </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    laptop: {
      type: Object,
      required: true,
    },
  },
  computed: {
    getEconomy() {
		if(this.laptop.economy > 0) {
			return this.laptop.economy
		}else{
			return 0
		}
	}
  },
};
</script>

<style lang="scss" scoped>
.price-old {
	font-size: 28px;
	color: grey;
	text-decoration: line-through;
}
.price {
	font-size: 40px;
}
.price-new {
	color: red;
}
</style>