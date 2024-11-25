<script setup>

</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <h1 class="text-center my-3">Учет товаров</h1>
        <div class="mb-3">
          <label for="exampleFormControlInput1" class="form-label">Название</label>
          <input type="email" class="form-control" id="exampleFormControlInput1" placeholder="name@example.com">
        </div>
        <div class="mb-3">
          <label for="date" class="form-label">Дата добавления</label>
          <input type="date" class="form-control" id="date">
        </div>
        <div class="mb-3">
          <label for="count" class="form-label">Количество</label>
          <input type="number" class="form-control" id="date">
        </div>
        <div class="mb-3">
          <label for="price" class="form-label">Цена</label>
          <input type="number" class="form-control" id="date">
        </div>
        <div>
          <button type="button" class="btn btn-outline-success">Добавить</button>
        </div>
      </div>
    </div>
    <div class="row row-cols-1 row-cols-md-2 mt-4">
  <div class="col">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">HP</h5>
        <p class="card-text">$1000</p>
        <p class="card-text">x10</p>
        <p class="card-text">25.11.2024</p>
      </div>
      <div class="card-footer">
        <button class="btn btn-outline-danger">Удалить</button>
      </div>
    </div>
  </div>
</div>
<div class="row my-4">
  <div class="col">
    <h3 class="text-end">Общая сумма товаров: $8478</h3>
  </div>
</div>
  </div>
</template>

