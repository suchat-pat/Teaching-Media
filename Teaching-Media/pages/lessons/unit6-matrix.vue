<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="cyan-darken-3" theme="dark" class="pa-6 mb-8 text-center" elevation="4">
          <v-icon size="64" class="mb-4">mdi-matrix</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">หน่วยที่ 6: เมทริกซ์ (Matrix)</h1>
          <p class="text-subtitle-1">ความหมาย การดำเนินการ ดีเทอร์มิแนนต์ และอินเวอร์ส</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="1. ความหมายและลักษณะของเมทริกซ์">
            <template v-slot:prepend>
              <v-icon color="cyan-darken-2">mdi-information-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">
              <strong>เมทริกซ์ (Matrix)</strong> คือ กลุ่มของตัวเลขที่เรียงกันเป็นรูปสี่เหลี่ยมภายในเครื่องหมายวงเล็บ [ ] หรือ ( )
            </p>
            <v-row align="center">
              <v-col cols="12" sm="6" class="text-center">
                <v-card color="grey-lighten-4" class="pa-4 d-flex flex-column align-center">
                  <div class="text-subtitle-1 font-weight-bold mb-2">ตัวอย่างเมทริกซ์ A</div>
                  <div class="matrix-box">
                    <table>
                      <tr><td>2</td><td>0</td></tr>
                      <tr><td>1</td><td>3</td></tr>
                    </table>
                  </div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6">
                <ul class="mt-2 ml-4">
                  <li><strong>สมาชิก (Element):</strong> ตัวเลขแต่ละตัวที่อยู่ในเมทริกซ์</li>
                  <li><strong>แถว (Row):</strong> การเรียงตัวในแนวนอน</li>
                  <li><strong>หลัก (Column):</strong> การเรียงตัวในแนวตั้ง</li>
                  <li><strong>มิติ (Dimension):</strong> บอกขนาดเป็น <em>m &times; n</em> (จำนวนแถว &times; จำนวนหลัก)</li>
                </ul>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="2. การบวก ลบ และคูณเมทริกซ์">
            <template v-slot:prepend>
              <v-icon color="cyan-darken-2">mdi-calculator-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            
            <v-expansion-panels variant="popout" class="mb-4">
              <v-expansion-panel>
                <v-expansion-panel-title class="font-weight-bold text-cyan-darken-4">
                  2.1 การบวกและการลบ (Addition & Subtraction)
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <v-alert type="info" variant="tonal" class="mb-4">
                    <strong>เงื่อนไข:</strong> เมทริกซ์ทั้งสองต้องมี <strong>มิติเท่ากัน</strong> เท่านั้น
                  </v-alert>
                  <p><strong>นิยาม:</strong> ให้นำสมาชิกที่อยู่ <strong>ตำแหน่งเดียวกัน</strong> มาบวกหรือลบกัน</p>
                  
                  <div class="text-center text-h6 my-4 font-italic">
                    C<sub>ij</sub> = A<sub>ij</sub> &plusmn; B<sub>ij</sub>
                  </div>

                  <v-card variant="outlined" class="pa-4 text-center">
                    <p class="font-weight-bold mb-3">ตัวอย่าง:</p>
                    <div class="d-flex align-center justify-center flex-wrap gap-2">
                      <div class="matrix-box small">
                        <table><tr><td>1</td><td>2</td></tr></table>
                      </div>
                      <span class="text-h5 mx-2">+</span>
                      <div class="matrix-box small">
                        <table><tr><td>3</td><td>5</td></tr></table>
                      </div>
                      <span class="text-h5 mx-2">=</span>
                      <div class="matrix-box small text-success">
                        <table><tr><td>4</td><td>7</td></tr></table>
                      </div>
                    </div>
                  </v-card>
                </v-expansion-panel-text>
              </v-expansion-panel>

              <v-expansion-panel>
                <v-expansion-panel-title class="font-weight-bold text-cyan-darken-4">
                  2.2 การคูณเมทริกซ์ (Multiplication)
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <ul class="ml-4">
                    <li class="mb-2"><strong>การคูณด้วยค่าคงที่ (Scalar):</strong> นำค่าคงที่คูณสมาชิก <em>ทุกตัว</em> ในเมทริกซ์</li>
                    <li><strong>การคูณเมทริกซ์ด้วยเมทริกซ์:</strong>
                      <br>ทำได้เมื่อ <em>จำนวนหลักของตัวตั้ง = จำนวนแถวของตัวคูณ</em>
                      <br>วิธีการคือเอา <strong>"แถว คูณ หลัก"</strong> แล้วนำผลคูณมาบวกกัน
                    </li>
                  </ul>
                </v-expansion-panel-text>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="3. ดีเทอร์มิแนนต์และอินเวอร์ส (Det & Inverse)">
            <template v-slot:prepend>
              <v-icon color="cyan-darken-2">mdi-function</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <div class="text-center mb-4">
              กำหนดเมทริกซ์ A = 
              <div class="matrix-box inline-matrix">
                <table><tr><td>a</td><td>b</td></tr><tr><td>c</td><td>d</td></tr></table>
              </div>
            </div>

            <v-row>
              <v-col cols="12" md="6">
                <v-card color="cyan-lighten-5" class="pa-4 text-center h-100">
                  <h3 class="text-h6 text-cyan-darken-4 mb-2">ดีเทอร์มิแนนต์ (Determinant)</h3>
                  <div class="text-h5 font-weight-bold my-2">det(A) = ad - bc</div>
                  <div class="text-caption text-grey-darken-2">(คูณลง - คูณขึ้น)</div>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card color="cyan-lighten-5" class="pa-4 text-center h-100">
                  <h3 class="text-h6 text-cyan-darken-4 mb-2">อินเวอร์สการคูณ (A<sup>-1</sup>)</h3>
                  <div class="d-flex align-center justify-center">
                    <span class="mr-2 text-h6">A<sup>-1</sup> = </span>
                    <div class="d-flex align-center">
                      <div class="text-center mr-2">
                        <div style="border-bottom: 1px solid black;">1</div>
                        <div>det(A)</div>
                      </div>
                      <div class="matrix-box">
                        <table><tr><td>d</td><td>-b</td></tr><tr><td>-c</td><td>a</td></tr></table>
                      </div>
                    </div>
                  </div>
                  <div class="text-caption text-error mt-2">เงื่อนไข: det(A) &ne; 0</div>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" elevation="2">
          <v-card-item title="4. แบบฝึกหัดทบทวน (Exercises)" class="bg-cyan-darken-3 text-white">
            <template v-slot:prepend>
              <v-icon>mdi-pencil-box-multiple</v-icon>
            </template>
          </v-card-item>
          
          <v-card-text class="pt-4">
            <div class="d-flex flex-wrap align-center justify-center gap-4 mb-6 text-body-1 bg-grey-lighten-4 pa-4 rounded">
              <div>
                <strong>A = </strong>
                <div class="matrix-box inline-matrix"><table><tr><td>1</td><td>2</td></tr><tr><td>2</td><td>7</td></tr></table></div>
              </div>
              <div>
                <strong>B = </strong>
                <div class="matrix-box inline-matrix"><table><tr><td>3</td><td>5</td></tr><tr><td>6</td><td>-2</td></tr></table></div>
              </div>
              <div>
                <strong>C = </strong>
                <div class="matrix-box inline-matrix"><table><tr><td>3</td><td>-8</td></tr><tr><td>4</td><td>1</td></tr></table></div>
              </div>
            </div>

            <v-expansion-panels variant="popout">
              <v-expansion-panel v-for="(q, idx) in exercises" :key="idx">
                <v-expansion-panel-title>
                  <span class="font-weight-bold mr-2">ข้อที่ {{ idx + 1 }}:</span> จงหาค่าของ {{ q.question }}
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <div class="d-flex align-center flex-wrap">
                    <span class="mr-3 font-weight-bold">คำตอบคือ:</span>
                    <div class="matrix-box text-cyan-darken-4">
                      <table>
                        <tr>
                          <td>{{ q.answer[0][0] }}</td>
                          <td>{{ q.answer[0][1] }}</td>
                        </tr>
                        <tr>
                          <td>{{ q.answer[1][0] }}</td>
                          <td>{{ q.answer[1][1] }}</td>
                        </tr>
                      </table>
                    </div>
                  </div>
                  <v-divider class="my-3"></v-divider>
                  <div class="text-body-2 text-grey-darken-2">
                    <strong>วิธีทำ:</strong> {{ q.explanation }}
                  </div>
                </v-expansion-panel-text>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="5. ศึกษาเพิ่มเติม (Further Study)">
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
              href="/lessons/Matrix.pdf" 
              target="_blank"
              color="red-darken-1" 
              size="large" 
              prepend-icon="mdi-file-pdf-box"
              elevation="2"
            >
              เปิดดูเอกสารประกอบ (PDF)
            </v-btn>
            <br>
            <br>
            <v-btn 
              href="/lessons/แบบฝึกทักษะ เรื่อง การบวกและการลบเมตริกซ์.pdf" 
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

const exercises = ref([
  {
    question: "A + B",
    // เก็บข้อมูลเป็น Array ซ้อน Array เพื่อนำไปวนลูปสร้างตารางเมทริกซ์
    answer: [[4, 7], [8, 5]], 
    explanation: "1+3=4, 2+5=7, 2+6=8, 7+(-2)=5"
  },
  {
    question: "B - A",
    answer: [[2, 3], [4, -9]],
    explanation: "3-1=2, 5-2=3, 6-2=4, (-2)-7=-9"
  },
  {
    question: "(A + B) + C",
    answer: [[7, -1], [12, 6]],
    explanation: "จาก A+B=[4 7; 8 5] นำไปบวก C=[3 -8; 4 1] จะได้ 4+3=7, 7+(-8)=-1, 8+4=12, 5+1=6"
  }
]);
</script>

<style scoped>
/* CSS สำหรับสร้างกรอบเมทริกซ์แบบ HTML 100% */
.matrix-box {
  display: inline-block;
  position: relative;
  padding: 0 6px;
  vertical-align: middle;
}

/* สร้างวงเล็บก้ามปู [] ด้วย Border */
.matrix-box::before,
.matrix-box::after {
  content: "";
  position: absolute;
  top: 0;
  bottom: 0;
  width: 6px;
  border: 2px solid black;
}

.matrix-box::before {
  left: 0;
  border-right: none; /* วงเล็บเปิด */
}

.matrix-box::after {
  right: 0;
  border-left: none; /* วงเล็บปิด */
}

.matrix-box table {
  border-collapse: collapse;
}

.matrix-box td {
  padding: 4px 8px;
  text-align: center;
  font-family: 'Courier New', Courier, monospace;
  font-weight: bold;
  font-size: 1.1rem;
}

/* ปรับขนาดสำหรับตัวอย่างเล็กๆ */
.matrix-box.small td {
  padding: 2px 4px;
  font-size: 1rem;
}

.inline-matrix {
  margin: 0 4px;
}

.v-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15) !important;
}
</style>