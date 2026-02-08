<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="deep-purple-darken-3" theme="dark" class="pa-6 mb-8 text-center" elevation="4">
          <v-icon size="64" class="mb-4">mdi-head-lightbulb-outline</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">หน่วยที่ 4: ตรรกศาสตร์ (Logic)</h1>
          <p class="text-subtitle-1">การให้เหตุผล ค่าความจริง สัจนิรันดร์ และตัวบ่งปริมาณ</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="1. พื้นฐานตรรกศาสตร์และประพจน์">
            <template v-slot:prepend>
              <v-icon color="deep-purple">mdi-alphabetical-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <v-alert color="deep-purple-lighten-5" border="start" border-color="deep-purple" class="mb-4">
              <strong>โครงสร้างระบบคณิตศาสตร์:</strong> ประกอบด้วย คำอนิยาม (Undefined Terms) &rarr; บทนิยาม (Definitions) &rarr; สัจพจน์ (Axioms) &rarr; ทฤษฎีบท (Theorems)
            </v-alert>
            
            <h3 class="text-h6 text-deep-purple-darken-1 mb-2">ประพจน์ (Proposition)</h3>
            <p class="mb-2">คือ ประโยคบอกเล่าหรือปฏิเสธที่มีค่าความจริงเป็น <strong>จริง (True: T)</strong> หรือ <strong>เท็จ (False: F)</strong> อย่างใดอย่างหนึ่งเท่านั้น</p>
            <ul class="ml-4 mb-4">
              <li><v-icon color="success" size="small">mdi-check</v-icon> <em>"4 เป็นจำนวนเฉพาะ"</em> (เป็นประพจน์ มีค่าความจริงเป็น เท็จ)</li>
              <li><v-icon color="error" size="small">mdi-close</v-icon> <em>"ห้ามเดินลัดสนาม"</em> (ไม่ใช่ประพจน์ เป็นประโยคคำสั่ง)</li>
              <li><v-icon color="error" size="small">mdi-close</v-icon> <em>"x + 1 = 2"</em> (ไม่ใช่ประพจน์ เป็นประโยคเปิด เพราะไม่รู้ค่า x)</li>
            </ul>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="2. ตัวเชื่อมประพจน์และค่าความจริง">
            <template v-slot:prepend>
              <v-icon color="deep-purple">mdi-table-large</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">กำหนดให้ p และ q เป็นประพจน์ สรุปค่าความจริงได้ดังนี้</p>
            
            <v-table hover density="comfortable" class="truth-table text-center">
              <thead>
                <tr class="bg-deep-purple-lighten-4">
                  <th class="text-center font-weight-bold">p</th>
                  <th class="text-center font-weight-bold">q</th>
                  <th class="text-center font-weight-bold text-blue-darken-2">และ (p &and; q)</th>
                  <th class="text-center font-weight-bold text-orange-darken-2">หรือ (p &or; q)</th>
                  <th class="text-center font-weight-bold text-green-darken-2">ถ้า..แล้ว (p &rarr; q)</th>
                  <th class="text-center font-weight-bold text-purple-darken-2">ก็ต่อเมื่อ (p &harr; q)</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(row, i) in truthTable" :key="i">
                  <td><v-chip :color="row.p === 'T' ? 'success' : 'error'" size="small" variant="flat">{{ row.p }}</v-chip></td>
                  <td><v-chip :color="row.q === 'T' ? 'success' : 'error'" size="small" variant="flat">{{ row.q }}</v-chip></td>
                  <td class="font-weight-medium">{{ row.and }}</td>
                  <td class="font-weight-medium">{{ row.or }}</td>
                  <td class="font-weight-medium" :class="{'bg-red-lighten-5': row.if === 'F'}">{{ row.if }}</td>
                  <td class="font-weight-medium">{{ row.iff }}</td>
                </tr>
              </tbody>
            </v-table>

            <v-row class="mt-4">
              <v-col cols="12" sm="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="text-subtitle-2 font-weight-bold">ข้อสังเกตสำคัญ:</div>
                  <ul class="text-body-2 pl-4">
                    <li><strong>และ (&and;):</strong> จริงกรณีเดียว คือ T &and; T</li>
                    <li><strong>หรือ (&or;):</strong> เท็จกรณีเดียว คือ F &or; F</li>
                    <li><strong>ถ้า..แล้ว (&rarr;):</strong> เท็จกรณีเดียว คือ T &rarr; F</li>
                    <li><strong>ก็ต่อเมื่อ (&harr;):</strong> จริงเมื่อค่าความจริงเหมือนกัน</li>
                  </ul>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6">
                <v-card variant="tonal" class="pa-2 h-100">
                  <div class="text-subtitle-2 font-weight-bold">นิเสธ (~):</div>
                  <p class="text-body-2">กลับค่าความจริงเป็นตรงข้าม เช่น ~T &equiv; F</p>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="3. รูปแบบประพจน์ที่สมมูลกัน (Equivalence)">
            <template v-slot:prepend>
              <v-icon color="deep-purple">mdi-equal-box</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">ประพจน์สองรูปแบบสมมูลกัน (&equiv;) ก็ต่อเมื่อมีค่าความจริงตรงกันกรณีต่อกรณี</p>
            
            <v-row>
              <v-col cols="12" md="6">
                <h4 class="text-subtitle-1 font-weight-bold text-deep-purple">กฎการเปลี่ยนรูปเงื่อนไข (สำคัญมาก)</h4>
                <v-list density="compact" class="bg-grey-lighten-4 rounded">
                  <v-list-item>
                    p &rarr; q &equiv; ~p &or; q
                  </v-list-item>
                  <v-list-item>
                    p &rarr; q &equiv; ~q &rarr; ~p (แย้งสลับที่)
                  </v-list-item>
                </v-list>
              </v-col>
              <v-col cols="12" md="6">
                <h4 class="text-subtitle-1 font-weight-bold text-deep-purple">กฎเดอมอร์แกน (De Morgan's)</h4>
                <v-list density="compact" class="bg-grey-lighten-4 rounded">
                  <v-list-item>
                    ~(p &and; q) &equiv; ~p &or; ~q
                  </v-list-item>
                  <v-list-item>
                    ~(p &or; q) &equiv; ~p &and; ~q
                  </v-list-item>
                </v-list>
              </v-col>
            </v-row>
            <v-row>
               <v-col cols="12">
                 <h4 class="text-subtitle-1 font-weight-bold text-deep-purple">กฎการแจกแจง</h4>
                 <p class="text-body-1">p &or; (q &and; r) &equiv; (p &or; q) &and; (p &or; r)</p>
                 <p class="text-body-1">p &and; (q &or; r) &equiv; (p &and; q) &or; (p &and; r)</p>
               </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="4. สัจนิรันดร์และการอ้างเหตุผล">
            <template v-slot:prepend>
              <v-icon color="deep-purple">mdi-logic</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <h3 class="text-h6 mb-2">สัจนิรันดร์ (Tautology)</h3>
            <p class="mb-2">คือ รูปแบบของประพจน์ที่มีค่าความจริงเป็น <strong>จริงทุกกรณี</strong></p>
            <p><strong>วิธีตรวจสอบ:</strong></p>
            <ol class="ml-4 mb-4">
              <li>ใช้ตารางค่าความจริง (ต้องได้ T ทุกช่อง)</li>
              <li><strong>วิธีหาข้อขัดแย้ง (นิยม):</strong> สมมติให้ประพจน์เป็น <strong>เท็จ (F)</strong> แล้วหาค่าความจริงย่อย หากเกิดข้อขัดแย้ง แสดงว่าเป็นสัจนิรันดร์</li>
            </ol>

            <v-divider class="my-4"></v-divider>

            <h3 class="text-h6 mb-2">การอ้างเหตุผล (Arguments)</h3>
            <p class="mb-2">ตรวจสอบโดยดูว่า (เหตุ<sub>1</sub> &and; เหตุ<sub>2</sub> &and; ... &and; เหตุ<sub>n</sub>) &rarr; ผล เป็น <strong>สัจนิรันดร์</strong> หรือไม่</p>
            <v-row>
              <v-col cols="12" sm="6">
                <v-card variant="outlined" color="success" class="pa-2">
                  <div class="text-center font-weight-bold">สมเหตุสมผล (Valid)</div>
                  <div class="text-center">เป็นสัจนิรันดร์</div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6">
                <v-card variant="outlined" color="error" class="pa-2">
                  <div class="text-center font-weight-bold">ไม่สมเหตุสมผล (Invalid)</div>
                  <div class="text-center">ไม่เป็นสัจนิรันดร์</div>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="5. ประโยคเปิดและตัวบ่งปริมาณ">
            <template v-slot:prepend>
              <v-icon color="deep-purple">mdi-set-all</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            
            <p class="mb-4 text-body-1">
              <strong>ประโยคเปิด (Open Sentence):</strong> คือประโยคที่มีตัวแปร ซึ่งเมื่อแทนค่าตัวแปรแล้วจะกลายเป็นประพจน์ (มีค่าความจริง)
            </p>
            
            <v-table density="comfortable" class="mb-6 border rounded">
              <thead class="bg-grey-lighten-4">
                <tr>
                  <th class="text-center text-subtitle-1 font-weight-bold">ชื่อ</th>
                  <th class="text-center text-subtitle-1 font-weight-bold">สัญลักษณ์</th>
                  <th class="text-left text-subtitle-1 font-weight-bold">ความหมาย</th>
                  <th class="text-left text-subtitle-1 font-weight-bold">เงื่อนไขความจริง</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td class="text-center font-weight-bold text-deep-purple">For All</td>
                  <td class="text-center text-h5 math-font">&forall;x</td>
                  <td>สำหรับ x <strong>ทุกตัว</strong></td>
                  <td>จริง เมื่อแทน x <u>ทุกตัว</u> ในเอกภพสัมพัทธ์ ($U$) แล้วจริง</td>
                </tr>
                <tr>
                  <td class="text-center font-weight-bold text-deep-purple">For Some</td>
                  <td class="text-center text-h5 math-font">&exists;x</td>
                  <td>มี x <strong>บางตัว</strong></td>
                  <td>จริง เมื่อมี x <u>อย่างน้อย 1 ตัว</u> ในเอกภพสัมพัทธ์ ($U$) ที่แทนแล้วจริง</td>
                </tr>
              </tbody>
            </v-table>

            <div class="bg-deep-purple-lighten-5 pa-4 rounded-lg border-thin border-deep-purple">
              <h4 class="text-h6 font-weight-bold text-deep-purple-darken-2 mb-3">
                <v-icon icon="mdi-swap-horizontal" class="mr-2"></v-icon>
                สมมูลและนิเสธของตัวบ่งปริมาณ
              </h4>
              <p class="mb-2 text-body-2 text-grey-darken-3">การกระจายนิเสธเข้าไป จะทำให้ตัวบ่งปริมาณ "กลับด้าน"</p>
              
              <v-row class="mt-2">
                <v-col cols="12" md="6">
                  <v-card variant="outlined" class="text-center pa-3 bg-white">
                    <div class="text-caption text-grey mb-1">นิเสธของ For All</div>
                    <div class="text-h6 math-font text-deep-purple">
                      &sim;&forall;x [P(x)] &nbsp;&equiv;&nbsp; &exists;x [&sim;P(x)]
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card variant="outlined" class="text-center pa-3 bg-white">
                    <div class="text-caption text-grey mb-1">นิเสธของ For Some</div>
                    <div class="text-h6 math-font text-deep-purple">
                      &sim;&exists;x [P(x)] &nbsp;&equiv;&nbsp; &forall;x [&sim;P(x)]
                    </div>
                  </v-card>
                </v-col>
              </v-row>
            </div>

          </v-card-text>
        </v-card>


        <v-card class="mb-6" elevation="2">
          <v-card-item title="แบบฝึกหัดทบทวน (Interactive Exercises)" class="bg-deep-purple text-white">
            <template v-slot:prepend>
              <v-icon>mdi-pencil-box-multiple</v-icon>
            </template>
          </v-card-item>
          
          <v-card-text class="pt-4">
            <v-expansion-panels variant="popout">
              
              <v-expansion-panel v-for="(q, idx) in exercises" :key="idx">
                <v-expansion-panel-title>
                  <span class="font-weight-bold mr-2">ข้อที่ {{ idx + 1 }}:</span> {{ q.question }}
                </v-expansion-panel-title>
                <v-expansion-panel-text>
                  <v-alert :type="q.type || 'info'" variant="tonal" class="mt-2">
                    <div class="font-weight-bold mb-2">เฉลย:</div>
                    <div v-html="q.answer"></div>
                  </v-alert>
                </v-expansion-panel-text>
              </v-expansion-panel>

            </v-expansion-panels>
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
              href="/lessons/ตรรกศาสตร์.pdf" 
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
              href="/lessons/แบบฝึกตรรกศาสตร์4.2.pdf" 
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
              href="https://youtu.be/eTBFewOC8Ys?si=8ErOGYH2dlZlEC8u" 
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

// ข้อมูลตารางค่าความจริง
const truthTable = ref([
  { p: 'T', q: 'T', and: 'T', or: 'T', if: 'T', iff: 'T' },
  { p: 'T', q: 'F', and: 'F', or: 'T', if: 'F', iff: 'F' },
  { p: 'F', q: 'T', and: 'F', or: 'T', if: 'T', iff: 'F' },
  { p: 'F', q: 'F', and: 'F', or: 'F', if: 'T', iff: 'T' },
]);

// ข้อมูลแบบฝึกหัด (เปลี่ยนสัญลักษณ์ LaTeX เป็น HTML Entities)
const exercises = ref([
  {
    question: "กำหนดให้ p, q เป็นจริง และ r เป็นเท็จ จงหาค่าความจริงของ [(p ∧ s) ∨ (p ∧ r)] → (p ∨ s)",
    answer: "<strong>เป็นจริง (True)</strong><br>วิธีคิด:<br>1. พิจารณาตัวหลัง (p ∨ s) เนื่องจาก p เป็นจริง ดังนั้น (p ∨ s) เป็นจริงแน่นอน (T ∨ ? ≡ T)<br>2. ประพจน์หลักเชื่อมด้วย '→' และตัวหลังเป็นจริง (T)<br>3. ดังนั้น ? → T ย่อมได้ <strong>จริง</strong> เสมอ",
    type: 'success'
  },
  {
    question: "จงตรวจสอบว่าเป็นสัจนิรันดร์หรือไม่: [(p → q) ∧ p] → q",
    answer: "<strong>เป็นสัจนิรันดร์</strong><br>วิธีตรวจสอบ (วิธีหาข้อขัดแย้ง):<br>1. สมมติให้ประพจน์เป็น เท็จ (F)<br>2. จะได้ว่า [(p → q) ∧ p] ต้องเป็น T และ q ต้องเป็น F<br>3. จาก [(p → q) ∧ p] เป็น T แสดงว่า p ต้องเป็น T<br>4. แทนค่า p=T, q=F ใน (p → q) จะได้ T → F ซึ่งได้ F (ขัดแย้งกับที่ต้องเป็น T ในข้อ 2)<br>5. เกิดข้อขัดแย้ง แสดงว่าสมมติเป็นเท็จไม่ได้ ∴ เป็นสัจนิรันดร์",
    type: 'info'
  },
  {
    question: "จงหานิเสธของข้อความ ∀x [x + 3 > 5]",
    answer: "<strong>∃x [x + 3 ≤ 5]</strong><br>หลักการ:<br>1. เปลี่ยนตัวบ่งปริมาณ ∀ เป็น ∃<br>2. ใส่นิเสธที่ประโยคเปิด ~(x + 3 > 5) คือ x + 3 ≤ 5",
    type: 'warning'
  },
  {
    question: "การอ้างเหตุผลนี้สมเหตุสมผลหรือไม่?<br>เหตุ 1) p → q<br>เหตุ 2) q → s<br>เหตุ 3) ~s<br>ผลสรุป: ~p",
    answer: "<strong>สมเหตุสมผล (Valid)</strong><br>วิธีคิด:<br>จากเหตุ 1 และ 2 ใช้กฎการถ่ายทอดจะได้ p → s<br>จาก p → s และเหตุ 3 (~s) ใช้กฎการแย้งสลับที่ (Modus Tollens) จะสรุปได้ว่า <strong>~p</strong><br>ตรงกับผลสรุปพอดี",
    type: 'success'
  }
]);
</script>

<style scoped>
.truth-table th {
  font-size: 1.1rem !important;
}
.truth-table td {
  font-size: 1rem;
}
.math-box {
  font-family: "Cambria Math", "Times New Roman", serif;
  font-size: 1.25rem;
  text-align: center;
  padding: 16px;
  border: 2px solid #673ab7;
  border-radius: 8px;
  background-color: #f3e5f5;
  font-weight: 500;
}
/* เพิ่มคลาสสำหรับฟอนต์คณิตศาสตร์ */
.math-font {
  font-family: 'Times New Roman', Times, serif;
  font-style: italic;
  letter-spacing: 1px;
}
.v-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15) !important;
}
</style>