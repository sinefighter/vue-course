<template>
  <div class="col-md-4">
    <div class="card-berry">
      <a :href="berry.link">
        <img :src="berry.image" class="card-img-top rounded-5" />
      </a>
	  <div class="card-berry__market">
		<span class="market">{{ berry.market }}</span>
		<span 
		:class="{
			'in-stock': berry.status,
			'out-stock': !berry.status
		}">{{ getStatus }}</span>
	  </div>
	  <div class="card-berry__name">
		<a :href="berry.link">
		{{ berry.name }}
		</a>
	  </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    berry: {
      type: Object,
      required: true,
    },
  },
  computed: {
	getStatus() {
		if(this.berry.status) {
			return 'Є в наявності'
		}else{
			return 'Немає в наявності'
		}
	}
  }
};
</script>

<style lang="scss" scoped>
img {
  height: 330px;
  object-fit: cover;
}
.in-stock {
	color: green;
}
.out-stock {
	color: red;
}
.market {
	font-weight: bold;
	margin-right: 10px;
}
.card-berry__name {
	font-size: 18px;
}
</style>