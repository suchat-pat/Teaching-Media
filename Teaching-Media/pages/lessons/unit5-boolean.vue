<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="orange-darken-3" theme="dark" class="pa-6 mb-8 text-center" elevation="4">
          <v-icon size="64" class="mb-4">mdi-gate-and</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">หน่วยที่ 5: พีชคณิตบูลีน (Boolean Algebra)</h1>
          <p class="text-subtitle-1">ทฤษฎี กฎพื้นฐาน และการลดรูปวงจรลอจิก</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="1. ความหมายและสัญลักษณ์พื้นฐาน">
            <template v-slot:prepend>
              <v-icon color="orange-darken-2">mdi-information-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">
              <strong>พีชคณิตบูลีน</strong> เป็นเทคนิคที่ใช้ในการลดรูป Switching Function เพื่อวิเคราะห์และออกแบบวงจรดิจิตอล โดยใช้ตัวแปร 2 สภาวะ คือ <strong>0</strong> หรือ <strong>1</strong>
            </p>
            
            <h3 class="text-h6 text-orange-darken-3 mb-2">สัญลักษณ์ทางเลขคณิต (Operators)</h3>
            <v-row>
              <v-col cols="12" sm="4">
                <v-card color="orange-lighten-5" variant="flat" class="text-center pa-4 h-100">
                  <div class="text-h4 mb-2">.</div>
                  <div class="font-weight-bold">AND Operation</div>
                  <div class="text-caption">ใช้เครื่องหมายจุด (.) แทนการคูณ</div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="4">
                <v-card color="orange-lighten-5" variant="flat" class="text-center pa-4 h-100">
                  <div class="text-h4 mb-2">+</div>
                  <div class="font-weight-bold">OR Operation</div>
                  <div class="text-caption">ใช้เครื่องหมายบวก (+) แทนการบวก</div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="4">
                <v-card color="orange-lighten-5" variant="flat" class="text-center pa-4 h-100">
                  <div class="text-h4 mb-2"><span style="text-decoration: overline">A</span></div>
                  <div class="font-weight-bold">NOT Operation</div>
                  <div class="text-caption">ใช้เครื่องหมายบาร์ (-) หรือขีดบน</div>
                </v-card>
              </v-col>
            </v-row>

            <h3 class="text-h6 text-orange-darken-3 mt-6 mb-2">ตารางค่าความจริง (Truth Table)</h3>
            <p class="mb-2">ตัวอย่างตารางความจริงของฟังก์ชัน F ที่ขึ้นกับตัวแปร x, y, z</p>
            <v-table density="compact" class="text-center truth-table" hover>
              <thead>
                <tr class="bg-grey-lighten-3">
                  <th>x</th><th>y</th><th>z</th><th class="text-orange-darken-2 font-weight-bold">F</th>
                </tr>
              </thead>
              <tbody>
                <tr><td>0</td><td>0</td><td>0</td><td>0</td></tr>
                <tr><td>0</td><td>0</td><td>1</td><td>1</td></tr>
                <tr><td>0</td><td>1</td><td>0</td><td>0</td></tr>
                <tr><td>0</td><td>1</td><td>1</td><td>0</td></tr>
                <tr><td>1</td><td>0</td><td>0</td><td>1</td></tr>
                <tr><td>1</td><td>0</td><td>1</td><td>1</td></tr>
                <tr><td>1</td><td>1</td><td>0</td><td>1</td></tr>
                <tr><td>1</td><td>1</td><td>1</td><td>1</td></tr>
              </tbody>
            </v-table>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="2. ทฤษฎีบทและกฎของพีชคณิตบูลีน (Boolean Theorems)">
            <template v-slot:prepend>
              <v-icon color="orange-darken-2">mdi-format-list-bulleted</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">กฎเหล่านี้ใช้ในการลดรูปสมการให้สั้นลง เพื่อลดจำนวนเกตและลดเวลาหน่วง (Delay Time)</p>
            
            <v-row dense>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">1. Commutative Law (การสลับที่)</div>
                  <ul class="ml-4 mt-1">
                    <li>A + B = B + A</li>
                    <li>A &middot; B = B &middot; A</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">2. Associative Law (การจัดหมู่)</div>
                  <ul class="ml-4 mt-1">
                    <li>(A + B) + C = A + (B + C)</li>
                    <li>(A &middot; B) &middot; C = A &middot; (B &middot; C)</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">3. Distributive Law (การกระจาย)</div>
                  <ul class="ml-4 mt-1">
                    <li>A &middot; (B + C) = (A &middot; B) + (A &middot; C)</li>
                    <li>A + (B &middot; C) = (A + B) &middot; (A + C)</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">4. Identity Law (เอกลักษณ์)</div>
                  <ul class="ml-4 mt-1">
                    <li>A + A = A</li>
                    <li>A &middot; A = A</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">5. Negation Law (การลบล้าง)</div>
                  <ul class="ml-4 mt-1">
                    <li><span style="text-decoration: overline"><span style="text-decoration: overline">A</span></span> = A (Double Negation)</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">6. Redundance Law (การลดทอน)</div>
                  <ul class="ml-4 mt-1">
                    <li>A + (A &middot; B) = A</li>
                    <li>A &middot; (A + B) = A</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">7. กฎเกี่ยวกับ 0 และ 1</div>
                  <ul class="ml-4 mt-1">
                    <li>0 + A = A และ 1 + A = 1</li>
                    <li>1 &middot; A = A และ 0 &middot; A = 0</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="font-weight-bold text-orange-darken-4">8. Complement Law</div>
                  <ul class="ml-4 mt-1">
                    <li><span style="text-decoration: overline">A</span> + A = 1</li>
                    <li><span style="text-decoration: overline">A</span> &middot; A = 0</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" md="12">
                <v-card color="grey-lighten-3" class="pa-2 mt-2">
                  <div class="font-weight-bold text-red-darken-2">10. De Morgan's Theorem (สำคัญมาก)</div>
                  <v-row>
                    <v-col cols="6" class="text-center text-h6">
                      <span style="text-decoration: overline">A + B</span> = <span style="text-decoration: overline">A</span> &middot; <span style="text-decoration: overline">B</span>
                    </v-col>
                    <v-col cols="6" class="text-center text-h6">
                      <span style="text-decoration: overline">A &middot; B</span> = <span style="text-decoration: overline">A</span> + <span style="text-decoration: overline">B</span>
                    </v-col>
                  </v-row>
                  <div class="text-caption text-center mt-1">"เปลี่ยนเครื่องหมาย แยกบาร์"</div>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="3. ตัวอย่างการลดรูป Switching Function">
            <template v-slot:prepend>
              <v-icon color="orange-darken-2">mdi-calculator</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            
            <v-expansion-panels variant="popout" class="mb-4">
              <v-expansion-panel>
                <v-expansion-panel-title class="font-weight-bold">
                  ตัวอย่างที่ 3.1: A &middot; B + <span style="text-decoration: overline">A</span> &middot; B + <span style="text-decoration: overline">A</span> &middot; <span style="text-decoration: overline">B</span>
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <div class="math-steps pl-4 border-left-orange">
                    <div class="step">= B &middot; (A + <span style="text-decoration: overline">A</span>) + <span style="text-decoration: overline">A</span> &middot; <span style="text-decoration: overline">B</span> <span class="text-grey ml-2">(ดึงตัวร่วม B)</span></div>
                    <div class="step">= B &middot; 1 + <span style="text-decoration: overline">A</span> &middot; <span style="text-decoration: overline">B</span> <span class="text-grey ml-2">(กฎ Complement)</span></div>
                    <div class="step">= B + <span style="text-decoration: overline">A</span> &middot; <span style="text-decoration: overline">B</span></div>
                    <div class="step">= (B + <span style="text-decoration: overline">B</span>) &middot; (B + <span style="text-decoration: overline">A</span>) <span class="text-grey ml-2">(กฎการกระจายแบบย้อนกลับ)</span></div>
                    <div class="result font-weight-bold text-success mt-2">
                      ตอบ: B + <span style="text-decoration: overline">A</span>
                    </div>
                  </div>
                </v-expansion-panel-text>
              </v-expansion-panel>

              <v-expansion-panel>
                <v-expansion-panel-title class="font-weight-bold">
                  ตัวอย่างที่ 3.2: A + A &middot; <span style="text-decoration: overline">B</span> + <span style="text-decoration: overline">A</span> &middot; B
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <div class="math-steps pl-4 border-left-orange">
                    <div class="step">= A &middot; (1 + <span style="text-decoration: overline">B</span>) + <span style="text-decoration: overline">A</span> &middot; B <span class="text-grey ml-2">(ดึงตัวร่วม A)</span></div>
                    <div class="step">= A &middot; 1 + <span style="text-decoration: overline">A</span> &middot; B <span class="text-grey ml-2">(กฎ 1 + อะไรก็ได้ = 1)</span></div>
                    <div class="step">= A + <span style="text-decoration: overline">A</span> &middot; B</div>
                    <div class="step">= (A + <span style="text-decoration: overline">A</span>) &middot; (A + B) <span class="text-grey ml-2">(กฎการกระจาย/ลดทอน)</span></div>
                    <div class="result font-weight-bold text-success mt-2">
                       ตอบ: A + B
                    </div>
                  </div>
                </v-expansion-panel-text>
              </v-expansion-panel>

              <v-expansion-panel>
                <v-expansion-panel-title class="font-weight-bold">
                  ตัวอย่างที่ 3.3: <span style="text-decoration: overline">(<span style="text-decoration: overline">A</span> + A &middot; <span style="text-decoration: overline">B</span>) + B</span>
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <div class="math-steps pl-4 border-left-orange">
                    <div class="step">พิจารณาในวงเล็บ: <span style="text-decoration: overline">A</span> + A &middot; <span style="text-decoration: overline">B</span> = <span style="text-decoration: overline">A</span> + <span style="text-decoration: overline">B</span> <span class="text-grey ml-2">(กฎการลดทอน)</span></div>
                    <div class="step">แทนค่ากลับ: <span style="text-decoration: overline">(<span style="text-decoration: overline">A</span> + <span style="text-decoration: overline">B</span>) + B</span></div>
                    <div class="step">จัดหมู่ใหม่: <span style="text-decoration: overline"><span style="text-decoration: overline">A</span> + (<span style="text-decoration: overline">B</span> + B)</span></div>
                    <div class="step">= <span style="text-decoration: overline"><span style="text-decoration: overline">A</span> + 1</span> <span class="text-grey ml-2">(กฎ Complement)</span></div>
                    <div class="step">= <span style="text-decoration: overline">1</span></div>
                    <div class="result font-weight-bold text-success mt-2">
                       ตอบ: 0
                    </div>
                  </div>
                </v-expansion-panel-text>
              </v-expansion-panel>
            </v-expansion-panels>

          </v-card-text>
        </v-card>

        <v-card class="mb-6" elevation="2">
          <v-card-item title="4. แบบฝึกหัดทบทวน (Interactive Quiz)" class="bg-orange-darken-3 text-white">
            <template v-slot:prepend>
              <v-icon>mdi-pencil-box-multiple</v-icon>
            </template>
          </v-card-item>
          
          <v-card-text class="pt-4">
            <div v-for="(q, idx) in exercises" :key="idx" class="mb-6">
              <p class="font-weight-bold mb-2">{{ idx + 1 }}. {{ q.question }}</p>
              
              <v-radio-group v-model="q.selected" inline hide-details class="mb-2">
                <v-radio 
                  v-for="(opt, oIdx) in q.options" 
                  :key="oIdx" 
                  :label="opt" 
                  :value="oIdx" 
                  color="orange-darken-2"
                ></v-radio>
              </v-radio-group>

              <v-expand-transition>
                <div v-if="q.selected !== null">
                  <v-alert 
                    v-if="q.selected === q.answer" 
                    type="success" 
                    variant="tonal" 
                    icon="mdi-check-circle"
                    class="mt-2"
                  >
                    <div class="font-weight-bold">ถูกต้อง!</div>
                    <div>{{ q.explanation }}</div>
                  </v-alert>

                  <v-alert 
                    v-else 
                    type="error" 
                    variant="tonal" 
                    icon="mdi-close-circle"
                    class="mt-2"
                  >
                    <div class="font-weight-bold">ยังไม่ถูกต้อง</div>
                    <div>คำตอบที่ถูกคือ: <strong>{{ q.options[q.answer] }}</strong></div>
                  </v-alert>
                </div>
              </v-expand-transition>
              
              <v-divider class="mt-4" v-if="idx < exercises.length - 1"></v-divider>
            </div>
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
              href="/lessons/หน่วยที่ 5 พีชคณิตบูลีน.pdf" 
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
              href="/lessons/แบบฝึกหัดพีชคณิตบูลีน.pdf" 
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
              href="https://youtu.be/N5-Qqo8Ia6g?si=pdqj1wfgiJYBf8rH" 
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
import { ref } from 'vue';

const exercises = ref([
  {
    question: "กฎการสลับที่ (Commutative Law) ของการคูณ (AND) คือข้อใด?",
    options: ["A + B = B + A", "A . B = B . A", "A . (B + C) = A.B + A.C", "A + 0 = A"],
    answer: 1,
    selected: null, // กำหนดค่าเริ่มต้นเป็น null เพื่อซ่อนเฉลย
    explanation: "ตามทฤษฎีบทที่ 1 กฎการสลับที่ A . B = B . A"
  },
  {
    question: "ตามทฤษฎีบทของ De Morgan ข้อใดถูกต้อง?",
    options: ["(A + B)' = A' + B'", "(A . B)' = A' . B'", "(A + B)' = A' . B'", "A'' = A"],
    answer: 2,
    selected: null, // กำหนดค่าเริ่มต้นเป็น null
    explanation: "De Morgan ระบุว่าบาร์ของผลบวก เท่ากับ ผลคูณของบาร์แยก"
  },
  {
    question: "จงลดรูปสมการ A + A.B",
    options: ["A", "B", "1", "0"],
    answer: 0,
    selected: null, // กำหนดค่าเริ่มต้นเป็น null
    explanation: "ตามกฎ Redundance Law (กฎการลดทอน) ทฤษฎีบทที่ 6: A + (A.B) = A"
  },
  {
    question: "ค่าของ A . A' (A AND NOT A) คือเท่าไร?",
    options: ["A", "1", "0", "A'"],
    answer: 2,
    selected: null, // กำหนดค่าเริ่มต้นเป็น null
    explanation: "ตามทฤษฎีบทที่ 8 กฎ Complement: A . A' = 0 เสมอ"
  }
]);
</script>

<style scoped>
.truth-table th, .truth-table td {
  border: 1px solid #e0e0e0;
}
.border-left-orange {
  border-left: 4px solid #f57c00;
}
.step {
  margin-bottom: 8px;
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