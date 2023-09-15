<script setup>
import { ref } from 'vue';

const travellist=ref([
{name : 'ท่าช้าง', price:200}, 
{name :'Goodviews', price:250},
{name :'ตะวันแดง', price:300}, 
{name :'Warmup', price:200},
]);

const selectedStore = ref(null);
const selectedTable = ref(null);
const nameInput = ref(''); 
const contactInput = ref(''); 
const dateTimeInput = ref('');
const isDataComplete = ref(false);

const setSelectedTable = (table) => {
  selectedTable.value = table;
};

const showReservationData = () => {

  if (selectedStore.value && selectedTable.value && nameInput.value && contactInput.value && dateTimeInput.value) {
    isDataComplete.value = true;
  } else {
    isDataComplete.value = false;
  }
};

const reserveTable = () => {

  if (selectedStore.value && selectedTable.value && nameInput.value && contactInput.value && dateTimeInput.value) {
    
    showReservationData();
    alert('จองโต๊ะสำเร็จ \n*ท่านสามารถดูข้อมูลได้ ด้านซ้ายของปุ่มจองโต๊ะ');
  } else {
    alert('กรุณากรอกข้อมูลให้ครบทุกช่อง');
  }
};

const onSuccess = () => {
  
  window.location.reload();
};


</script>

<template>
  <header>
    <h1>จองโต๊ะร้านเหล้า</h1>
  </header>

  <body>
    <div class="card-con">
      <div class="card" style="width: 18rem;">
        <img src="/imgs_project/goodview.jpg" class="card-img-top" alt="กู๊ดวิว">
        <div class="card-body">
          <h5 class="card-title"><b>{{ travellist[1].name }}</b></h5>
          <p>ราคา : {{ travellist[1].price }} บาท</p>
          <button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModalopen1" @click="selectedStore = travellist[1].name">
            จอง
          </button>

          
          <div class="modal fade" id="exampleModalopen1" tabindex="-1" aria-labelledby="exampleModalLabel1" aria-hidden="true">
            <div class="modal-dialog">
              <div class="modal-content">
                <div class="modal-header">
                  <h1 class="modal-title fs-5" id="exampleModalLabel1">Goodviews</h1>
                  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>

                <div class="modal-body-button">
                  <div class="button-table">
                  <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('A01')">A01</button>
                  <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('A02')">A02</button>
                  <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('A03')">A03</button>
                  <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('A04')">A04</button>
                  <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('A05')">A05</button>
                  <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('A06')">A06</button>
                  <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('B01')">B01</button>
                  <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('B02')">B02</button>
                  <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('B03')">B03</button>
                  <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('B04')">B04</button>
                  <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('B05')">B05</button>
                  <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                  @click="setSelectedTable('B06')">B06</button>
                  </div>
                </div>

                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">ยกเลิก</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="card" style="width: 18rem;">
        <img src="/imgs_project/tawandang.jpg" class="card-img-top" alt="ตะวันแดง">
        <div class="card-body">
          <h5 class="card-title"><b>{{ travellist[2].name }}</b></h5>
          <p>ราคา : {{ travellist[2].price }} บาท</p>
          <button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModalopen2" @click="selectedStore = travellist[2].name">
            จอง
          </button>

          
          <div class="modal fade" id="exampleModalopen2" tabindex="-1" aria-labelledby="exampleModalLabel2" aria-hidden="true">
            <div class="modal-dialog">
              <div class="modal-content">
                <div class="modal-header">
                  <h1 class="modal-title fs-5" id="exampleModalLabel2">ตะวันแดง</h1>
                  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>

                <div class="modal-body-button">
                  <div class="button-table">
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A01')">A01</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A02')">A02</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A03')">A03</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A04')">A04</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A05')">A05</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A06')">A06</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B01')">B01</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B02')">B02</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B03')">B03</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B04')">B04</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B05')">B05</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B06')">B06</button>
                  </div>
                </div>

                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">ยกเลิก</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    
      <div class="card" style="width: 18rem;">
        <img src="/imgs_project/tachang.jpg" class="card-img-top" alt="ท่าช้าง">
        <div class="card-body">
          <h5 class="card-title"><b>{{ travellist[0].name }}</b></h5>
          <p>ราคา : {{ travellist[0].price }} บาท</p>
          <button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModalopen3" @click="selectedStore = travellist[0].name">
            จอง
          </button>

          
          <div class="modal fade" id="exampleModalopen3" tabindex="-1" aria-labelledby="exampleModalLabel3" aria-hidden="true">
            <div class="modal-dialog">
              <div class="modal-content">
                <div class="modal-header">
                  <h1 class="modal-title fs-5" id="exampleModalLabel3">ท่าช้าง</h1>
                  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>

                <div class="modal-body-button">
                  <div class="button-table">
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A01')">A01</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A02')">A02</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A03')">A03</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A04')">A04</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A05')">A05</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A06')">A06</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B01')">B01</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B02')">B02</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B03')">B03</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B04')">B04</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B05')">B05</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B06')">B06</button>
                  </div>
                </div>

                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">ยกเลิก</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="card" style="width: 18rem;">
        <img src="/imgs_project/warm_up.jpg" class="card-img-top" alt="วอร์มอัพ">
        <div class="card-body">
          <h5 class="card-title"><b>{{ travellist[3].name }}</b></h5>
          <p>ราคา : {{ travellist[3].price }} บาท</p>
          
          <button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModalopen4" @click="selectedStore = travellist[3].name">
            จอง
          </button>

          
          <div class="modal fade" id="exampleModalopen4" tabindex="-1" aria-labelledby="exampleModalLabel4" aria-hidden="true">
            <div class="modal-dialog">
              <div class="modal-content">
                <div class="modal-header">
                  <h1 class="modal-title fs-5" id="exampleModalLabel4">Warmup</h1>
                  <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>

                <div class="modal-body-button">
                  <div class="button-table">
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A01')">A01</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A02')">A02</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A03')">A03</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A04')">A04</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A05')">A05</button>
                    <button type="button" class="btn btn-warning" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('A06')">A06</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B01')">B01</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B02')">B02</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B03')">B03</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B04')">B04</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B05')">B05</button>
                    <button type="button" class="btn btn-dark" data-bs-toggle="modal" data-bs-target="#exampleModalopen"
                    @click="setSelectedTable('B06')">B06</button>
                  </div>
                </div>

                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">ยกเลิก</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>    
    </div>

    <div class="modal fade" id="exampleModalopen" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">ร้าน : {{ selectedStore }}</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <div class="input-group mb-3">
              <span class="input-group-text" id="exampleModalLabel">โต๊ะ : {{ selectedTable }}</span>
            </div>
    
            <div class="input-group mb-3">
              <span class="input-group-text">ชื่อ</span>
              <div class="form-floating">
                <input type="text" class="form-control" id="floatingInputGroup1" v-model="nameInput">
              </div>
            </div>
    
            <div class="input-group mb-3">
              <span class="input-group-text">เบอร์ติดต่อ</span>
              <div class="form-floating">
                <input type="number" class="form-control" id="floatingInputGroup2" v-model="contactInput">
              </div>
            </div>
    
            <div class="input-group mb-3">
              <span class="input-group-text">วันที่และเวลา</span>
              <div class="form-floating">
                <input type="datetime-local" class="form-control" id="floatingInputGroup3" v-model="dateTimeInput">
              </div>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-info" data-bs-toggle="modal" data-bs-target="#reservationModal" @click="showReservationData" v-if="isDataComplete">
              ดูข้อมูล
            </button>
                        
            <button type="button" class="btn btn-primary" @click="reserveTable">จองโต๊ะ</button>            
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">ยกเลิก</button>
          </div>
        </div>
      </div>
    </div>

    <div class="modal fade" id="reservationModal" tabindex="-1" aria-labelledby="reservationModalLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="reservationModalLabel">ข้อมูลการจองโต๊ะ</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <div class="entry">
              <p>ร้าน: {{ selectedStore }}</p>
              <p>โต๊ะ: {{ selectedTable }}</p>
              <p>ชื่อ: {{ nameInput }}</p>
              <p>เบอร์ติดต่อ: {{ contactInput }}</p>
              <p>วันที่และเวลา: {{ dateTimeInput }}</p>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">ปิด</button>
            <button type="button" class="btn btn-primary" @click="onSuccess">สำเร็จ</button>
          </div>
        </div>
      </div>
    </div>
  </body>

  <footer class="d-flex justify-content-center py-3">
    <ul class="nav nav-pills">
      <li class="nav-item"><a href="https://www.facebook.com/pages/Goodview-Village-Chiangmai/1333396683427720" class="nav-link">Goodviews</a></li>
      <li class="nav-item"><a href="https://www.facebook.com/ThachangFanpage" class="nav-link">ท่าช้าง</a></li>
      <li class="nav-item"><a href="https://www.facebook.com/Tawandangmahasoncm" class="nav-link">ตะวันแดง</a></li>
      <li class="nav-item"><a href="https://www.facebook.com/warmupcafe1999" class="nav-link">Warmup</a></li>
    </ul>
  </footer>
</template>


<style scoped>
.card{
  margin: 50px;
  margin-top: 80px;
  background-color: #ffffff;
  border-radius: 10px; /* ขอบการ์ด */
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2); /* เงา */
  padding: 20px
}
.card-con{
  display: grid;
  grid-template-columns: auto auto auto auto;
  justify-content: center;
}

.card-con button{
  border-radius: 10px;
}

.button-table button{
  margin: 10px;
  margin-right: 50px;
  flex: 0 0 calc(20% - 10px);
  border-radius: 10px;
}

.button-table {
  display: flex;
  flex-wrap: wrap;
  gap: 10px
}

.card img{
  border-radius: 9px;
}
</style>