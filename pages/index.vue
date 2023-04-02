<template>
    <div>
        <Navtop />
        <section class="container my-auto p-5 text-center">
            <div class="row justify-content-center">
                <div class="col-4">
                    <div class="row mx-auto">
                        <div class="col-12 text-left pb-3"><img src="/images/nameweb.png" /></div>
                        <div class="col-12 text-left text-white pb-3">Lorem Ipsum is simply Lorem Ipsum is simply Lorem
                            Ipsum is simply
                        </div>
                        <div class="col-12 text-left text-white pb-3">Lorem Ipsum is simply dummy text of the printing and
                            typesetting
                            industry. Lorem Ipsum has been the industry's </div>
                    </div>
                </div>
                <div class="col-4 my-auto"><img src="/images/bicycle.png" /></div>
            </div>
        </section>
        <section class="container my-auto p-5 text-center">
            <div class="justify-content-center pb-5"><img src="/images/nameweb_2.png" /></div>
            <div class="justify-content-center pb-5"><img src="/images/avastar.png" /></div>
            <div class="justify-content-center text-white pb-2">Lorem Ipsum is simply</div>
            <div class="justify-content-center pb-5">
                <div class="row justify-content-center">
                    <div class="col-6">
                        <h3 class="text-white">Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                            Lorem Ipsum has been
                            the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley
                            of type and scrambled it to make a type specimen book.</h3>
                    </div>
                </div>
            </div>
        </section>
        <section class="container my-auto p-5 text-center" id="bg_yellow">
            <div class="justify-content-center pb-5"><img src="/images/lorem.png" /></div>
            <div class="row" id="space_card">
                <div class="col-4" v-for="item in items" :key="id">
                    <div class="card">
                        <img class="card-img-top" :src="item.thumbnail" alt="image" style="height: 200px;" />
                        <div class="card-body" style="height: 280px;">
                            <h3 class="card-title text-center"><strong>{{ item.title }}</strong></h3>
                            <p class="card-text text-center">{{ item.description }}</p>
                            <p class="card-text text-left pt-2"><strong>Price: </strong> {{ item.price }}</p>
                            <p class="card-text text-left"><strong>DiscountPercentage: </strong>{{ item.discountPercentage
                            }}</p>
                            <p class="card-text text-left"><strong>Rating: </strong>{{ item.rating }}</p>
                            <p class="card-text text-left"><strong>Stock: </strong>{{ item.stock }}</p>
                            <p class="card-text text-left"><strong>Brand: </strong>{{ item.brand }}</p>
                            <p class="card-text text-left"><strong>Category: </strong>{{ item.category }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="container my-auto p-5 text-center">
            <div class="row justify-content-center">
                <div class="col-4 my-auto"><img src="/images/bicycle.png" /></div>
                <div class="col-4">
                    <h1 class="text-2xl text-white"><strong>ติดต่อเรา</strong></h1>
                    <input type="text" class="form-control no-border mb-3" id="inputname" placeholder="ชื่อ - นามสกุล">
                    <input type="text" class="form-control no-border mb-3" id="inputphone" placeholder="เบอร์ติดต่อ">
                    <input type="email" class="form-control no-border mb-3" id="inputemail" placeholder="อีเมล">
                    <input type="date" class="form-control no-border mb-3" id="inputdate" placeholder="วันที่"
                        value="2023-01-31">
                    <p class="text-white text-left">Lorem Ipsum is simply dummy text</p>
                    <p class="text-white text-left pb-5">Lorem Ipsum is simply dummy text</p>
                    <button class="btn_lorem">LOREM</button>
                </div>
            </div>
        </section>
    </div>
</template>
  
<script setup>
import { ref } from 'vue';
const items = ref([])

fetch('https://dummyjson.com/products?limit=3')
    .then(res => res.json())
    .then((result) => {
        items.value = result.products
        // console.log(result.products)
    })
</script>
<style></style>
