<template>
  <!-- Women Banner Section Begin -->
  <section class="women-banner spad">
    <div class="container-fluid">
      <div class="col-lg-12 mt-5" v-if="products.length > 0">
        <div class="row">
          <div
            class="product-item"
            v-for="itemProduct in products"
            :key="itemProduct.id"
          >
            <div class="card-deck">
              <div class="card">
                <div class="pi-pic">
                  <img v-bind:src="itemProduct.galleries[0].photo" alt />
                  <ul>
                    <li @click="saveKeranjang(itemProduct.id, itemProduct.name, itemProduct.price, itemProduct.galleries[0].photo)" class="w-icon active">
                      <a href="#">
                        <i class="icon_bag_alt"></i>
                      </a>
                    </li>
                    <li class="quick-view">
                      <router-link :to="'/product/' + itemProduct.id">
                        + Quick View
                      </router-link>
                    </li>
                  </ul>
                </div>
                <div class="card-body">
                  <div class="catagory-name">{{ itemProduct.type }}</div>
                  <a href="#">
                    <b
                      ><h4>{{ itemProduct.name }}</h4></b
                    >
                  </a>
                  <div class="product-price">Rp. {{ itemProduct.price }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-lg-12" v-else>
        <p>Produk terbaru belum tersedia untuk saat ini.</p>
      </div>
    </div>
  </section>
  <!-- Women Banner Section End -->
</template>
<script>
import axios from "axios";

export default {
  name: "WomenHijabKabul",
  components: {
    //
  },
  data() {
    return {
      products: [],
       keranjangUser: []
    };
  },
  mounted() {
    axios
      .get("http://127.0.0.1:8000/api/products")
      .then((res) => (this.products = res.data.data.data))
      // eslint-disable-next-line no-console
      .catch((err) => console.log(err));
  },
   methods: {
    saveKeranjang(idProduct, nameProduct, priceProduct, photoProduct) {
      var productStored = {
        id: idProduct,
        name: nameProduct,
        price: priceProduct,
        photo: photoProduct
      };

      this.keranjangUser.push(productStored);
      const parsed = JSON.stringify(this.keranjangUser);
      localStorage.setItem("keranjangUser", parsed);
    }
  }
};
</script>

<style scoped>
.product-item {
  margin-right: 25px;
}
.pi-pic {
  height: 250px;
  width: 350px;
}
.card-deck {
  align-items: center;
}
</style>
