<script setup>
import { ref, computed } from "vue";
const products = ref([
  {
    id: 1,
    name: 'Tesla',
    date: '20.11.2024',
    count: 10,
    price: 4000,
  },
  {
    id: 2,
    name: 'Aser',
    date: '10.11.2024',
    count: 150,
    price: 1000,
  },
  {
    id: 3,
    name: 'HP',
    date: '11.11.2024',
    count: 18,
    price: 5000,
  },
  {
    id: 4,
    name: 'Asus',
    date: '05.11.2024',
    count: 25,
    price: 3000,
  }
]);

const name = ref('');
const date = ref('');
const count = ref(1);
const price = ref(0);

const addProduct = () => {
  if (name.value && date.value && count.value && price.value) {
    products.value.push({

    id: Date.now(),
    name: name.value,
    date: date.value,
    count: count.value,
    price: price.value,

    });
  }
}
const removeProduct = (id) => {
  products.value = products.value.filter((product) => product.id !=id);
}

const totalSum = computed(() => {
  return products.value.reduce((sum, product) => sum + (product.price * product.count), 0);
});

</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <h1 class="text-center my-3">Учет товаров</h1>
        <div class="mb-3">
          <label for="name" class="form-label">Название</label>
          <input type="text" v-model="name" class="form-control" :class="{'is-invalid': !name}" id="name">
          <div class="invalid-feedback">
        Заполните пожалуйста название!
      </div>
        </div>
        <div class="mb-3">
          <label for="date" class="form-label">Дата добавления</label>
          <input type="date" v-model="date" class="form-control" :class="{'is-invalid': !date}" id="date">
          <div class="invalid-feedback">
            Заполните пожалуйста дату!
      </div>
        </div>
        <div class="mb-3">
          <label for="count" class="form-label">Количество</label>
          <input type="number" v-model="count" class="form-control" :class="{'is-invalid': !count}" id="date">
          <div class="invalid-feedback">
            Заполните пожалуйста Количество!
      </div>
        </div>
        <div class="mb-3">
          <label for="price" class="form-label">Цена</label>
          <input type="number" v-model="price" class="form-control" :class="{'is-invalid': !price}" id="date">
          <div class="invalid-feedback">
            Заполните пожалуйста цену!
      </div>
        </div>
        <div>
          <button @click="addProduct" type="button" class="btn btn-outline-success">Добавить</button>
        </div>
      </div>
    </div>
    <div class="row row-cols-1 row-cols-md-2 mt-4">
  <div class="col" v-for="product in products" :key="product.id">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <p class="card-text">{{ product.price }}</p>
        <p class="card-text">{{ product.count }}</p>
        <p class="card-text">{{ product.date }}</p>
      </div>
      <div class="card-footer">
        <button @click="removeProduct(product.id)" class="btn btn-outline-danger">Удалить</button>
      </div>
    </div>
  </div>
</div>
<div class="row my-4">
  <div class="col">
    <h3 class="text-end">Общая сумма товаров: ${{ totalSum }}</h3>
  </div>
</div>
  </div>
</template>

