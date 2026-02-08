<template>
  <v-container class="py-12 bg-grey-lighten-5 fill-height align-start" fluid>
    <v-row justify="center" class="mb-8">
      <v-col cols="12" md="8" class="text-center">
        <h1 class="text-h3 font-weight-bold text-blue-grey-darken-4 mb-2">
          คณะผู้จัดทำ
        </h1>
        <p class="text-subtitle-1 text-grey-darken-1">
          นักศึกษาระดับชั้นประกาศนียบัตรวิชาชีพ (ปวช.)
        </p>
        <v-divider class="my-4 mx-auto" length="100" thickness="3" color="primary"></v-divider>
      </v-col>
      <v-row justify="center" class="px-4">
      <v-col 
        v-for="(member, index) in members" 
        :key="index" 
        cols="12" 
        sm="6" 
        md="4"
        lg="3"
      >
        <v-hover v-slot="{ isHovering, props }">
          <v-card
            v-bind="props"
            class="mx-auto rounded-xl pb-4 text-center transition-swing"
            :elevation="isHovering ? 12 : 2"
            max-width="350"
            border
          >
            <div class="pt-6 px-6">
              <v-avatar size="200" class="elevation-4">
                <v-img 
                  :src="member.image" 
                  alt="Profile Image" 
                  cover
                >
                  <template v-slot:placeholder>
                    <div class="d-flex align-center justify-center fill-height bg-grey-lighten-3">
                      <v-icon color="grey-lighten-1" size="48">mdi-account</v-icon>
                    </div>
                  </template>
                </v-img>
              </v-avatar>
            </div>

            <v-card-item class="pt-4">
              <div class="text-h6 font-weight-bold text-blue-grey-darken-3 mb-1">
                {{ member.name }}
              </div>
              
              <div class="text-caption text-primary font-weight-bold text-uppercase mb-3">
                ผู้จัดทำ
              </div>

              <v-divider class="mb-4"></v-divider>

              <div class="d-flex justify-center align-center mb-2">
                <v-icon size="small" color="grey" class="mr-2">mdi-card-account-details-outline</v-icon>
                <span class="text-body-2 text-grey-darken-2">
                  รหัสนักศึกษา: <strong>{{ member.studentId }}</strong>
                </span>
              </div>

              <div class="d-flex justify-center align-center">
                <v-icon size="small" color="grey" class="mr-2">mdi-school-outline</v-icon>
                <span class="text-body-2 text-grey-darken-2">
                  ชั้นปีที่: <strong>3/1</strong>
                </span>
              </div>
            </v-card-item>
          </v-card>
        </v-hover>
      </v-col>
    </v-row>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

// ข้อมูลสมาชิกในทีม
// ** สิ่งที่คุณต้องแก้ไข: เปลี่ยนชื่อ, รหัสนักศึกษา และใส่ path รูปภาพจริงของคุณ **
const members = ref([
  {
    name: "นายปณชัย  พ่วงขำ", // คนที่ 1
    studentId: "66209010023",
    image: "/img/1.jpg" // ใส่ path รูป เช่น '/images/member1.jpg'
  },
  {
    name: "นายสุชัจจ์  รัตนวิเวธน์", // คนที่ 2
    studentId: "66209010036",
    image: "/img/2.png" // ใส่ path รูป เช่น '/images/member2.jpg'
  },
  {
    name: "นายราชพฤกษ์  สลีอ่อน", // คนที่ 3
    studentId: "66209010028",
    image: "/img/3.png" // ใส่ path รูป เช่น '/images/member3.jpg'
  }
]);
</script>

<style scoped>
.transition-swing {
  transition: 0.4s cubic-bezier(0.25, 0.8, 0.5, 1);
}
</style>