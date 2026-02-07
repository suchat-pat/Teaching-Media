<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="teal" theme="dark" class="pa-6 mb-8 text-center" elevation="4">
          <v-icon size="64" class="mb-4">mdi-numeric</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">หน่วยที่ 2: ระบบตัวเลขฐาน</h1>
          <p class="text-subtitle-1">ความหมาย การเปลี่ยนฐาน และการคำนวณในระบบฐานต่างๆ</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="1. ความหมายและประเภทของเลขฐาน">
            <template v-slot:prepend>
              <v-icon color="teal">mdi-information-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4 text-body-1">
              <strong>เลขฐาน (Number Base)</strong> หมายถึง กลุ่มข้อมูลที่มีจำนวนหลัก (Digit) ตามชื่อของฐานนั้นๆ เป็นสัญลักษณ์ทางคณิตศาสตร์ที่แสดงถึงจำนวนต่างๆ
            </p>
            <v-row>
              <v-col cols="12" sm="6" md="3">
                <v-card color="teal-lighten-5" variant="flat" class="h-100">
                  <v-card-title class="text-subtitle-1 font-weight-bold text-teal-darken-3">
                    ฐานสอง (Binary)
                  </v-card-title>
                  <v-card-text>
                    ประกอบด้วยตัวเลข 2 ตัว คือ <strong>0, 1</strong> นิยมใช้ในการประมวลผลคอมพิวเตอร์
                  </v-card-text>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6" md="3">
                <v-card color="teal-lighten-5" variant="flat" class="h-100">
                  <v-card-title class="text-subtitle-1 font-weight-bold text-teal-darken-3">
                    ฐานแปด (Octal)
                  </v-card-title>
                  <v-card-text>
                    ประกอบด้วยตัวเลข 8 ตัว คือ <strong>0, 1, 2, 3, 4, 5, 6, 7</strong>
                  </v-card-text>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6" md="3">
                <v-card color="teal-lighten-5" variant="flat" class="h-100">
                  <v-card-title class="text-subtitle-1 font-weight-bold text-teal-darken-3">
                    ฐานสิบ (Decimal)
                  </v-card-title>
                  <v-card-text>
                    เลขในชีวิตประจำวัน ประกอบด้วย 10 ตัว คือ <strong>0-9</strong>
                  </v-card-text>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6" md="3">
                <v-card color="teal-lighten-5" variant="flat" class="h-100">
                  <v-card-title class="text-subtitle-1 font-weight-bold text-teal-darken-3">
                    ฐานสิบหก (Hex)
                  </v-card-title>
                  <v-card-text>
                    ประกอบด้วย <strong>0-9</strong> และตัวอักษร <strong>A-F</strong> (A=10, B=11, ..., F=15)
                  </v-card-text>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="2. ตารางเปรียบเทียบค่าเลขฐาน">
            <template v-slot:prepend>
              <v-icon color="teal">mdi-table</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-table density="compact" hover>
            <thead>
              <tr class="bg-teal-lighten-4">
                <th class="text-center font-weight-bold">ฐานสิบ (Decimal)</th>
                <th class="text-center font-weight-bold">ฐานสอง (Binary)</th>
                <th class="text-center font-weight-bold">ฐานแปด (Octal)</th>
                <th class="text-center font-weight-bold">ฐานสิบหก (Hex)</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, index) in compareTable" :key="index">
                <td class="text-center">{{ item.dec }}</td>
                <td class="text-center">{{ item.bin }}</td>
                <td class="text-center">{{ item.oct }}</td>
                <td class="text-center font-weight-bold text-teal">{{ item.hex }}</td>
              </tr>
            </tbody>
          </v-table>
          <v-card-text class="text-caption text-grey text-center">
            อ้างอิงข้อมูลจากตารางเปรียบเทียบเลขฐาน
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="3. การเปลี่ยนฐานและค่าประจำหลัก">
            <template v-slot:prepend>
              <v-icon color="teal">mdi-calculator-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            
            <h3 class="text-h6 text-teal-darken-2 mb-2">3.1 การเปลี่ยน "เลขฐานอื่น" เป็น "เลขฐานสิบ" (การกระจาย)</h3>
            <p class="mb-4">
              ใช้หลักการคูณเลขโดดด้วย <strong>ค่าประจำหลัก</strong> (Base<sup>n</sup>) แล้วนำมาบวกกัน
            </p>
            <v-alert border="start" color="teal-lighten-4" variant="tonal" class="mb-4">
              <strong>ตัวอย่าง:</strong> แปลง (10010)<sub>2</sub> เป็นฐานสิบ<br>
              <strong>วิธีทำ:</strong> (1 &times; 2<sup>5</sup>) + (1 &times; 2<sup>4</sup>) + (0 &times; 2<sup>3</sup>) + (0 &times; 2<sup>2</sup>) + (1 &times; 2<sup>1</sup>) + (0 &times; 2<sup>0</sup>) <br>
              = 32 + 16 + 0 + 0 + 2 + 0<br>
              <strong>= 50</strong>
            </v-alert>

            <v-divider class="my-6"></v-divider>

            <h3 class="text-h6 text-teal-darken-2 mb-2">3.2 การเปลี่ยน "เลขฐานสิบ" เป็น "เลขฐานอื่น" (การหารสั้น)</h3>
            <p class="mb-4">
              ใช้หลักการนำเลขฐานที่ต้องการไป <strong>หารสั้น</strong> จำนวนในฐานสิบเรื่อยๆ แล้วนำ <strong>เศษที่เหลือ</strong> มาเขียนเรียงจากล่างขึ้นบน
            </p>
            
            <v-row>
               <v-col cols="12" md="6">
                 <v-card variant="tonal" class="pa-4 h-100">
                   <p class="font-weight-bold mb-2">ตัวอย่าง: เปลี่ยน 748 เป็น ฐานห้า</p>
                   <div class="font-mono text-body-2 pl-4 py-2" style="border-left: 3px solid teal; background-color: #f5f5f5;">
                     <div>5 ) 748  ---> เศษ 3</div>
                     <div>5 ) 149  ---> เศษ 4</div>
                     <div>5 )  29  ---> เศษ 4</div>
                     <div>5 )   5  ---> เศษ 0</div>
                     <div>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1  ---> (ผลลัพธ์สุดท้าย)</div>
                   </div>
                   <p class="mt-2 text-teal font-weight-bold">
                     ตอบ: อ่านจากล่างขึ้นบน = 10443<sub>5</sub>
                   </p>
                 </v-card>
               </v-col>
               <v-col cols="12" md="6">
                 <p>
                   <strong>แนวคิดเชิงรูปธรรม (การมัดดินสอ):</strong><br>
                   เหมือนการจัดกลุ่มดินสอ 748 แท่ง:
                 </p>
                 <ul class="ml-4 mt-2">
                   <li>มัดละ 5<sup>4</sup> (625) ได้ 1 มัด</li>
                   <li>มัดละ 5<sup>3</sup> (125) ได้ 0 มัด</li>
                   <li>มัดละ 5<sup>2</sup> (25) ได้ 4 มัด</li>
                   <li>มัดละ 5<sup>1</sup> (5) ได้ 4 มัด</li>
                   <li>เศษ 5<sup>0</sup> (1) เหลือ 3 แท่ง</li>
                 </ul>
                 <p class="mt-2">เขียนรวมกันได้ 10443<sub>5</sub></p>
               </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="4. การคำนวณและการเปลี่ยนฐานระหว่างระบบ (Arbitrary Base Conversion)">
            <template v-slot:prepend>
              <v-icon color="teal">mdi-swap-horizontal</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">
              การเปลี่ยนจากฐาน A ไปฐาน B หรือการบวกลบเลขต่างฐาน มักนิยม <strong>แปลงเป็นฐานสิบก่อน</strong> ทำการคำนวณ แล้วจึงแปลงผลลัพธ์กลับเป็นฐานเป้าหมาย
            </p>

            <v-expansion-panels variant="popout" class="mb-4">
              <v-expansion-panel>
                <v-expansion-panel-title class="text-subtitle-1 font-weight-bold">
                  ตัวอย่างที่ 1: (12211)<sub>3</sub> - (1111)<sub>2</sub> ตอบในฐาน 5
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <ol class="pl-4">
                    <li class="mb-2">
                      <strong>แปลง (12211)<sub>3</sub> เป็นฐานสิบ:</strong><br>
                      (1 &times; 3<sup>4</sup>) + (2 &times; 3<sup>3</sup>) + (2 &times; 3<sup>2</sup>) + (1 &times; 3<sup>1</sup>) + (1 &times; 3<sup>0</sup>) <br>
                      = 81 + 54 + 18 + 3 + 1 = <strong>157</strong>
                    </li>
                    <li class="mb-2">
                      <strong>แปลง (1111)<sub>2</sub> เป็นฐานสิบ:</strong><br>
                      8 + 4 + 2 + 1 = <strong>15</strong>
                    </li>
                    <li class="mb-2">
                      <strong>หาผลลบในฐานสิบ:</strong><br>
                      157 - 15 = <strong>142</strong>
                    </li>
                    <li>
                      <strong>แปลง 142 เป็นฐาน 5:</strong><br>
                      142 &divide; 5 = 28 เศษ 2<br>
                      28 &divide; 5 = 5 เศษ 3<br>
                      5 &divide; 5 = 1 เศษ 0<br>
                      <strong>ตอบ: 1032<sub>5</sub></strong>
                    </li>
                  </ol>
                </v-expansion-panel-text>
              </v-expansion-panel>

              <v-expansion-panel>
                <v-expansion-panel-title class="text-subtitle-1 font-weight-bold">
                  ตัวอย่างที่ 2: (23110)<sub>4</sub> + (10110)<sub>2</sub> - (1112)<sub>3</sub> ตอบในฐาน 8
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <ol class="pl-4">
                    <li class="mb-2">
                      <strong>แปลงเป็นฐานสิบ:</strong><br>
                      (23110)<sub>4</sub> = 725<br>
                      (10110)<sub>2</sub> = 22<br>
                      (1112)<sub>3</sub> = 41
                    </li>
                    <li class="mb-2">
                      <strong>คำนวณ:</strong><br>
                      725 + 22 - 41 = <strong>704</strong>
                    </li>
                    <li>
                      <strong>แปลง 704 เป็นฐาน 8:</strong><br>
                      704 &divide; 8 = 88 เศษ 0<br>
                      88 &divide; 8 = 11 เศษ 0<br>
                      11 &divide; 8 = 1 เศษ 3<br>
                      <strong>ตอบ: 1300<sub>8</sub></strong>
                    </li>
                  </ol>
                </v-expansion-panel-text>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="5. แบบฝึกหัดทบทวน">
            <template v-slot:prepend>
              <v-icon color="teal">mdi-pencil-box-multiple</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-2">จงเปลี่ยนฐานเลขต่อไปนี้:</p>
            <v-list density="compact">
              <v-list-item prepend-icon="mdi-chevron-right">
                11110<sub>2</sub> เป็น ฐานสิบ
              </v-list-item>
              <v-list-item prepend-icon="mdi-chevron-right">
                1464<sub>7</sub> เป็น ฐานสิบ
              </v-list-item>
              <v-list-item prepend-icon="mdi-chevron-right">
                34 (ฐานสิบ) เป็น ฐาน 5
              </v-list-item>
              <v-list-item prepend-icon="mdi-chevron-right">
                (12210<sub>3</sub> - 11111<sub>2</sub>) ตอบในฐาน 6
              </v-list-item>
            </v-list>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="6. ศึกษาเพิ่มเติม (Further Study)">
            <template v-slot:prepend>
              <v-icon color="cyan-darken-2">mdi-book-education-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text class="text-center py-6">
            <p class="text-body-1 mb-4">
              หากต้องการศึกษาเนื้อหาอย่างละเอียด สามารถดาวน์โหลดเอกสารประกอบการเรียนได้ที่ปุ่มด้านล่าง
            </p>
            
            <v-btn 
              href="/lessons/บทที่2 เลขฐาน.pdf" 
              target="_blank"
              color="red-darken-1" 
              size="large" 
              prepend-icon="mdi-file-pdf-box"
              elevation="2"
              class="mb-4"
            >
              เปิดดูเอกสารประกอบ (PDF)
            </v-btn>
            <br>
            <v-btn 
              href="/lessons/แบบฝึก2.pdf" 
              target="_blank"
              color="red-darken-1" 
              size="large" 
              prepend-icon="mdi-file-pdf-box"
              elevation="2"
            >
              แบบทดสอบเพิ่มเติม (PDF)
            </v-btn>

          </v-card-text>
        </v-card>

      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

const compareTable = ref([
  { dec: 0, bin: '0000', oct: '0', hex: '0' },
  { dec: 1, bin: '0001', oct: '1', hex: '1' },
  { dec: 2, bin: '0010', oct: '2', hex: '2' },
  { dec: 3, bin: '0011', oct: '3', hex: '3' },
  { dec: 4, bin: '0100', oct: '4', hex: '4' },
  { dec: 5, bin: '0101', oct: '5', hex: '5' },
  { dec: 6, bin: '0110', oct: '6', hex: '6' },
  { dec: 7, bin: '0111', oct: '7', hex: '7' },
  { dec: 8, bin: '1000', oct: '10', hex: '8' },
  { dec: 9, bin: '1001', oct: '11', hex: '9' },
  { dec: 10, bin: '1010', oct: '12', hex: 'A' },
  { dec: 11, bin: '1011', oct: '13', hex: 'B' },
  { dec: 12, bin: '1100', oct: '14', hex: 'C' },
  { dec: 13, bin: '1101', oct: '15', hex: 'D' },
  { dec: 14, bin: '1110', oct: '16', hex: 'E' },
  { dec: 15, bin: '1111', oct: '17', hex: 'F' },
  { dec: 16, bin: '10000', oct: '20', hex: '10' },
]);
</script>

<style scoped>
.v-card-text {
  line-height: 1.8;
}
/* เพิ่มฟอนต์ Mono สำหรับแสดงการตั้งหาร */
.font-mono {
  font-family: 'Courier New', Courier, monospace;
}

.v-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15) !important;
}
</style>