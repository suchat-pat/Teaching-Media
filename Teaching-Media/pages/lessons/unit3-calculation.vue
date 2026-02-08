<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="indigo" theme="dark" class="pa-6 mb-8 text-center" elevation="4">
          <v-icon size="64" class="mb-4">mdi-calculator</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">หน่วยที่ 3: การคำนวณเลขฐาน</h1>
          <p class="text-subtitle-1">การบวก ลบ คูณ หาร และการใช้คอมพลีเมนต์ในระบบเลขฐานต่างๆ</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="1. การคำนวณเลขฐานสอง (Binary Calculation)">
            <template v-slot:prepend>
              <v-icon color="indigo">mdi-numeric-2-box-multiple-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">คอมพิวเตอร์ใช้ระบบเลขฐานสองในการคำนวณเนื่องจากตรงกับสถานะเปิด/ปิดของวงจรไฟฟ้า</p>
            
            <v-row>
              <v-col cols="12" md="6">
                <v-card variant="tonal" color="indigo-lighten-4" class="pa-3 mb-3 h-100">
                  <div class="text-subtitle-1 font-weight-bold text-indigo-darken-3 mb-2">กฏการบวก (Addition)</div>
                  <ul class="pl-4">
                    <li>0 + 0 = 0</li>
                    <li>0 + 1 = 1</li>
                    <li>1 + 0 = 1</li>
                    <li>1 + 1 = 0 (ทด 1)</li>
                    <li>1 + 1 + 1 = 1 (ทด 1)</li>
                  </ul>
                  
                  <v-divider class="my-3"></v-divider>
                  
                  <div class="text-subtitle-2 font-weight-bold mb-1">ตัวอย่าง: (1100)<sub>2</sub> + (1010)<sub>2</sub></div>
                  <div class="bg-white rounded pa-2 border" style="width: fit-content;">
                    <pre class="text-body-1 font-mono mb-0 text-black">
  1100
+ 1010
------
 10110
</pre>
                  </div>
                  <div class="mt-2"><strong>ตอบ:</strong> (10110)<sub>2</sub></div>
                </v-card>
              </v-col>

              <v-col cols="12" md="6">
                <v-card variant="tonal" color="red-lighten-4" class="pa-3 mb-3 h-100">
                  <div class="text-subtitle-1 font-weight-bold text-red-darken-3 mb-2">กฏการลบ (Subtraction)</div>
                  <ul class="pl-4">
                    <li>0 - 0 = 0</li>
                    <li>1 - 0 = 1</li>
                    <li>1 - 1 = 0</li>
                    <li>0 - 1 = 1 (ยืมหลักหน้ามา 1 แล้วค่าหลักเดิมเหลือ 0, ค่าที่ยืมมาจะเป็น 2 ในฐานสิบ)</li>
                  </ul>

                  <v-divider class="my-3"></v-divider>

                  <div class="text-subtitle-2 font-weight-bold mb-1">ตัวอย่าง: (1100)<sub>2</sub> - (1010)<sub>2</sub></div>
                  <div class="bg-white rounded pa-2 border" style="width: fit-content;">
                    <pre class="text-body-1 font-mono mb-0 text-black">
  1100
- 1010
------
  0010
</pre>
                  </div>
                  <div class="mt-2"><strong>ตอบ:</strong> (10)<sub>2</sub></div>
                </v-card>
              </v-col>

              <v-col cols="12" md="6">
                <v-card variant="tonal" color="green-lighten-4" class="pa-3 mb-3 h-100">
                  <div class="text-subtitle-1 font-weight-bold text-green-darken-3 mb-2">การคูณ (Multiplication)</div>
                  <p class="mb-2">เหมือนเลขฐานสิบ: 1 &times; 1 = 1, นอกนั้นได้ 0</p>
                  
                  <div class="text-subtitle-2 font-weight-bold mb-1">ตัวอย่าง: (1100)<sub>2</sub> &times; (101)<sub>2</sub></div>
                  <div class="bg-white rounded pa-2 border" style="width: fit-content;">
                    <pre class="text-body-1 font-mono mb-0 text-black">
    1100
  &times;  101
  ------
    1100
   0000
  1100
  ------
  111100
</pre>
                  </div>
                  <div class="mt-2"><strong>ตอบ:</strong> (111100)<sub>2</sub></div>
                </v-card>
              </v-col>

               <v-col cols="12" md="6">
                <v-card variant="tonal" color="orange-lighten-4" class="pa-3 mb-3 h-100">
                  <div class="text-subtitle-1 font-weight-bold text-orange-darken-3 mb-2">การหาร (Division)</div>
                  <p class="mb-2">ใช้วิธีหารยาวเหมือนเลขฐานสิบ</p>
                  
                  <div class="text-subtitle-2 font-weight-bold mb-1">ตัวอย่าง: (1111)<sub>2</sub> &divide; (101)<sub>2</sub></div>
                  <div class="bg-white rounded pa-2 border" style="width: fit-content;">
                    <pre class="text-body-1 font-mono mb-0 text-black">
      11
    ____
101)1111
    101
    ---
     101
     101
     ---
       0
</pre>
                  </div>
                  <div class="mt-2"><strong>ตอบ:</strong> (11)<sub>2</sub></div>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="2. การคำนวณเลขฐานแปด (Octal Calculation)">
            <template v-slot:prepend>
              <v-icon color="indigo">mdi-numeric-8-box-multiple-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <v-alert type="info" variant="tonal" class="mb-4">
              <strong>หลักการ:</strong> ใช้ตัวเลข 0-7 หากผลลัพธ์เกิน 7 ให้ลบด้วย 8 แล้วทดไปหลักถัดไป (กรณีบวก) หรือยืมมาทีละ 8 (กรณีลบ)
            </v-alert>
            <v-row>
              <v-col cols="12" md="6">
                <div class="text-h6 text-indigo-darken-1 mb-2">การบวก (Addition)</div>
                <p>ตัวอย่าง: (4356)<sub>8</sub> + (5726)<sub>8</sub></p>
                <ul class="text-body-2 text-grey-darken-3 mb-2">
                  <li>6+6=12 (เกิน 8) &rightarrow; 12-8=4 ทด 1</li>
                  <li>5+2+1(ทด)=8 &rightarrow; 8-8=0 ทด 1</li>
                  <li>3+7+1(ทด)=11 &rightarrow; 11-8=3 ทด 1</li>
                  <li>4+5+1(ทด)=10 &rightarrow; 10-8=2 ทด 1</li>
                </ul>
                <p><strong>ตอบ:</strong> (12304)<sub>8</sub></p>
              </v-col>
              <v-col cols="12" md="6">
                <div class="text-h6 text-indigo-darken-1 mb-2">การลบ (Subtraction)</div>
                <p>ตัวอย่าง: (12304)<sub>8</sub> - (5726)<sub>8</sub></p>
                <ul class="text-body-2 text-grey-darken-3 mb-2">
                  <li>4-6 ไม่ได้ ยืมหลักหน้ามา 8 เป็น 12-6=6</li>
                  <li>หลักถัดไปถูกยืมเหลือ 0 (เดิมคือ 0 ยืมต่อเป็น 8 ถูกยืมไป 1 เหลือ 7)</li>
                  <li>...ทำต่อตามหลักการยืม...</li>
                </ul>
                <p><strong>ตอบ:</strong> (4356)<sub>8</sub></p>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="3. การคำนวณเลขฐานสิบหก (Hexadecimal Calculation)">
             <template v-slot:prepend>
              <v-icon color="indigo">mdi-numeric-0-box-multiple-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
           <v-card-text>
            <v-alert type="warning" variant="tonal" class="mb-4">
              <strong>ข้อควรจำ:</strong> A=10, B=11, C=12, D=13, E=14, F=15. หลักการทดและยืมใช้ค่า 16
            </v-alert>
             <v-row>
              <v-col cols="12" md="6">
                <div class="text-h6 text-indigo-darken-1 mb-2">การบวก (Addition)</div>
                <p>ตัวอย่าง: (A3C6)<sub>16</sub> + (2EC6)<sub>16</sub></p>
                <ul class="text-body-2 text-grey-darken-3">
                  <li>6+6 = 12 (C)</li>
                  <li>C(12) + C(12) = 24. เกิน 16 &rightarrow; 24-16 = 8 (ทด 1)</li>
                  <li>3 + E(14) + 1(ทด) = 18. เกิน 16 &rightarrow; 18-16 = 2 (ทด 1)</li>
                  <li>A(10) + 2 + 1(ทด) = 13 (D)</li>
                </ul>
                 <p class="mt-2"><strong>ตอบ:</strong> (D28C)<sub>16</sub></p>
              </v-col>
               <v-col cols="12" md="6">
                <div class="text-h6 text-indigo-darken-1 mb-2">การลบ (Subtraction)</div>
                <p>ตัวอย่าง: (123A4)<sub>16</sub> - (B726)<sub>16</sub></p>
                <p>ยืมหลักหน้ามาทีละ 16 เช่น 4-6 ไม่ได้ ยืม A มาเป็น 4+16=20 แล้วลบ 6 เหลือ 14 (E)</p>
                <p><strong>ตอบ:</strong> (6C7E)<sub>16</sub></p>
              </v-col>
             </v-row>
           </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="4. คอมพลีเมนต์ (Complements)">
            <template v-slot:prepend>
              <v-icon color="indigo">mdi-swap-horizontal-bold</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p>การลบเลขสามารถทำได้โดยการ <strong>"บวกด้วยคอมพลีเมนต์ของตัวลบ"</strong></p>
            
            <v-table density="compact" class="mt-4">
              <thead>
                <tr>
                  <th>ฐาน</th>
                  <th>r-1 Complement (นำค่าสูงสุดลบ)</th>
                  <th>r Complement (r-1 Complement + 1)</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td><strong>ฐาน 10</strong></td>
                  <td><strong>9's Comp:</strong> เอา 9 ลบทุกหลัก</td>
                  <td><strong>10's Comp:</strong> 9's Comp + 1</td>
                </tr>
                <tr>
                   <td><strong>ฐาน 2</strong></td>
                  <td><strong>1's Comp:</strong> กลับ 0 เป็น 1, 1 เป็น 0</td>
                  <td><strong>2's Comp:</strong> 1's Comp + 1</td>
                </tr>
                 <tr>
                   <td><strong>ฐาน 8</strong></td>
                  <td><strong>7's Comp:</strong> เอา 7 ลบทุกหลัก</td>
                  <td><strong>8's Comp:</strong> 7's Comp + 1</td>
                </tr>
                 <tr>
                   <td><strong>ฐาน 16</strong></td>
                  <td><strong>15's Comp:</strong> เอา F(15) ลบทุกหลัก</td>
                  <td><strong>16's Comp:</strong> 15's Comp + 1</td>
                </tr>
              </tbody>
            </v-table>
            <div class="mt-2 text-caption text-grey-darken-1">
                * หลักการคำนวณ: หากใช้ r Complement ให้ตัดตัวทดทิ้ง, หากใช้ r-1 Complement ให้นำตัวทดมาบวกเพิ่มที่หลักสุดท้าย
            </div>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="5. แบบฝึกหัดทบทวน (Exercises)">
            <template v-slot:prepend>
              <v-icon color="indigo">mdi-clipboard-list-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <v-list lines="two">
              <v-list-item>
                <template v-slot:prepend><v-icon color="indigo">mdi-pencil</v-icon></template>
                <v-list-item-title class="text-black font-weight-medium">จงบวกเลขฐานสอง: (1011011.110)<sub>2</sub> + (11101.11)<sub>2</sub></v-list-item-title>
                <v-list-item-subtitle class="text-caption">แบบฝึกหัดข้อ 1.</v-list-item-subtitle>
              </v-list-item>
              <v-list-item>
                <template v-slot:prepend><v-icon color="indigo">mdi-pencil</v-icon></template>
                <v-list-item-title class="text-black font-weight-medium">จงลบเลขฐานแปด: (32141.04)<sub>8</sub> - (3674.43)<sub>8</sub></v-list-item-title>
                <v-list-item-subtitle class="text-caption">แบบฝึกหัดข้อ 2.</v-list-item-subtitle>
              </v-list-item>
              <v-list-item>
                <template v-slot:prepend><v-icon color="indigo">mdi-pencil</v-icon></template>
                <v-list-item-title class="text-black font-weight-medium">จงคูณเลขฐานสิบหก: (846AC)<sub>16</sub> &times; (6E)<sub>16</sub></v-list-item-title>
                 <v-list-item-subtitle class="text-caption">แบบฝึกหัดข้อ 3.</v-list-item-subtitle>
              </v-list-item>
              <v-list-item>
                <template v-slot:prepend><v-icon color="indigo">mdi-pencil</v-icon></template>
                <v-list-item-title class="text-black font-weight-medium">จงลบด้วยวิธี 2's Complement: (1011101)<sub>2</sub> - (0111011)<sub>2</sub></v-list-item-title>
                 <v-list-item-subtitle class="text-caption">แบบฝึกหัดข้อ 4.</v-list-item-subtitle>
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
              href="/lessons/การบวกลบเลขฐาน.pdf" 
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
              href="/lessons/ใบงานเพื่อการทดสอบความเชี่ยวชาญเลขฐาน-1.pdf" 
              target="_blank"
              color="red-darken-1" 
              size="large" 
              prepend-icon="mdi-file-pdf-box"
              elevation="2"
            >
              แบบทดสอบเพิ่มเติม (PDF)
            </v-btn>
            <br><br>
            <v-btn 
              href="https://youtube.com/playlist?list=PL5MJvF5C-NIQoZmVikjDJEKojg4mwOPx_&si=QSAY59hvxql8JcRx" 
              target="_blank"
              color="red-darken-4" 
              size="large" 
              elevation="2"
            >
              ศึกษาเพิ่มเติมจากคลิปวิดีโอ
            </v-btn>
          </v-card-text>
        </v-card>

      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
// ไม่ต้องใช้ script เพิ่มเติมสำหรับการแสดงผลข้อมูล static
</script>

<style scoped>
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