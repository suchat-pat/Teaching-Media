<template>
  <v-container class="py-8">
    <v-row justify="center">
      <v-col cols="12" md="10">
        <v-card color="primary" theme="dark" class="pa-6 mb-8 text-center" elevation="4">
          <v-icon size="64" class="mb-4">mdi-math-compass</v-icon>
          <h1 class="text-h3 font-weight-bold mb-2">หน่วยที่ 1: ระบบจำนวนจริง</h1>
          <p class="text-subtitle-1">สรุปเนื้อหา สมบัติ การแยกตัวประกอบ และการแก้สมการ-อสมการ</p>
        </v-card>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="10">
        
        <v-card class="mb-6" variant="outlined">
          <v-card-item title="1. ชนิดของจำนวนต่างๆ (Types of Numbers)">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-family-tree</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4"><strong>จำนวนจริง (R):</strong> คือจำนวนที่มีอยู่จริงบนเส้นจำนวน ประกอบด้วย:</p>
            <v-row>
              <v-col cols="12" sm="6">
                <v-list density="compact">
                  <v-list-subheader class="font-weight-bold text-primary">จำนวนตรรกยะ (Q)</v-list-subheader>
                  <v-list-item prepend-icon="mdi-check-circle-outline">จำนวนเต็ม (I): เต็มบวก (1, 2, ...), ศูนย์ (0), เต็มลบ (-1, -2, ...)</v-list-item>
                  <v-list-item prepend-icon="mdi-check-circle-outline">
                    เศษส่วน: ที่เขียนในรูป <span class="fraction"><sup>a</sup>&frasl;<sub>b</sub></span> ได้
                  </v-list-item>
                  <v-list-item prepend-icon="mdi-check-circle-outline">ทศนิยมรู้จบ และทศนิยมซ้ำ</v-list-item>
                </v-list>
              </v-col>
              <v-col cols="12" sm="6">
                <v-list density="compact">
                  <v-list-subheader class="font-weight-bold text-error">จำนวนอตรรกยะ (Q')</v-list-subheader>
                  <v-list-item prepend-icon="mdi-close-circle-outline">ทศนิยมไม่รู้จบและไม่ซ้ำ</v-list-item>
                  <v-list-item prepend-icon="mdi-close-circle-outline">ถอดรากไม่ลงตัว เช่น &radic;2, &radic;3</v-list-item>
                  <v-list-item prepend-icon="mdi-close-circle-outline">ค่าคงที่พิเศษ เช่น &pi;, e</v-list-item>
                </v-list>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="2. สมบัติการเท่ากันของจำนวนจริง">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-equal</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-table density="comfortable">
            <thead>
              <tr>
                <th class="text-left">ชื่อสมบัติ</th>
                <th class="text-left">นิยาม</th>
              </tr>
            </thead>
            <tbody>
              <tr><td>สมบัติการสะท้อน</td><td>a = a</td></tr>
              <tr><td>สมบัติการสมมาตร</td><td>ถ้า a = b แล้ว b = a</td></tr>
              <tr><td>สมบัติการถ่ายทอด</td><td>ถ้า a = b และ b = c แล้ว a = c</td></tr>
              <tr><td>การบวกด้วยตัวเท่า</td><td>ถ้า a = b แล้ว a + c = b + c</td></tr>
              <tr><td>การคูณด้วยตัวเท่า</td><td>ถ้า a = b แล้ว ac = bc</td></tr>
            </tbody>
          </v-table>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="3. สมบัติการบวกและการคูณ">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-plus-minus-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <v-row>
              <v-col cols="12" md="6">
                <h4 class="text-h6 mb-2">สมบัติการบวก</h4>
                <ul>
                    <li><strong>เอกลักษณ์การบวก:</strong> คือ 0 เพราะ 0 + a = a</li>
                    <li><strong>อินเวอร์สการบวก:</strong> ของ a คือ -a (บวกกันได้ 0)</li>
                </ul>
              </v-col>
              <v-col cols="12" md="6">
                <h4 class="text-h6 mb-2">สมบัติการคูณ</h4>
                <ul>
                  <li><strong>เอกลักษณ์การคูณ:</strong> คือ 1 เพราะ 1 &times; a = a</li>
                  <li><strong>อินเวอร์สการคูณ:</strong> ของ a คือ <span class="fraction"><sup>1</sup>&frasl;<sub>a</sub></span> (คูณกันได้ 1) โดย a &ne; 0</li>
                </ul>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="4. การแยกตัวประกอบพหุนาม (Factoring)">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-function-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <v-alert type="info" variant="tonal" class="mb-4">
              สูตรที่สำคัญต้องจำ:
            </v-alert>
            <v-row>
              <v-col cols="12" sm="6">
                <v-sheet border rounded class="pa-3 mb-2 bg-grey-lighten-4 font-mono">
                  a<sup>2</sup> - b<sup>2</sup> = (a - b)(a + b)
                </v-sheet>
                <v-sheet border rounded class="pa-3 mb-2 bg-grey-lighten-4 font-mono">
                  (a &plusmn; b)<sup>2</sup> = a<sup>2</sup> &plusmn; 2ab + b<sup>2</sup>
                </v-sheet>
              </v-col>
              <v-col cols="12" sm="6">
                <v-sheet border rounded class="pa-3 mb-2 bg-grey-lighten-4 font-mono">
                  a<sup>3</sup> - b<sup>3</sup> = (a - b)(a<sup>2</sup> + ab + b<sup>2</sup>)
                </v-sheet>
                <v-sheet border rounded class="pa-3 mb-2 bg-grey-lighten-4 font-mono">
                  a<sup>3</sup> + b<sup>3</sup> = (a + b)(a<sup>2</sup> - ab + b<sup>2</sup>)
                </v-sheet>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="5. การแก้สมการและอสมการ">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-variable</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <h4 class="text-h6 mb-2">การแก้สมการกำลังสอง ax<sup>2</sup> + bx + c = 0</h4>
            <p>หากแยกตัวประกอบไม่ได้ ให้ใช้สูตร:</p>
            
            <div class="text-center my-4 d-flex justify-center">
              <v-sheet color="secondary" rounded class="px-6 py-2 d-inline-flex align-center text-h5 text-white">
                <span class="mr-2">x = </span>
                <div class="d-flex flex-column align-center">
                  <span style="border-bottom: 2px solid white; padding-bottom: 2px; line-height: 1.2;">-b &plusmn; &radic;(b<sup>2</sup> - 4ac)</span>
                  <span style="line-height: 1.2;">2a</span>
                </div>
              </v-sheet>
            </div>

            <v-divider class="my-4"></v-divider>
            <h4 class="text-h6 mb-2">ข้อระวังในการแก้อสมการ</h4>
            <v-list density="compact">
              <v-list-item prepend-icon="mdi-alert">เมื่อคูณหรือหารด้วย <strong>เลขลบ</strong> ต้องกลับเครื่องหมายเสมอ</v-list-item>
              <v-list-item prepend-icon="mdi-alert">ห้ามคูณไขว้ตัวแปรที่ไม่ทราบค่า (ไม่รู้ว่าเป็นบวกหรือลบ)</v-list-item>
            </v-list>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="6. ค่าสัมบูรณ์ (Absolute Value)">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-side-lines</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p><strong>นิยาม:</strong> |x| คือค่าที่เป็นบวกเสมอ</p>
            <v-row class="mt-2">
              <v-col cols="12" sm="4">
                <v-card variant="tonal" color="success" class="pa-4 text-center h-100 d-flex align-center justify-center">
                  <div>
                    <div class="text-h6 font-weight-bold mb-1">|x| &lt; a</div>
                    <div>&rarr; -a &lt; x &lt; a</div>
                  </div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="4">
                <v-card variant="tonal" color="warning" class="pa-4 text-center h-100 d-flex align-center justify-center">
                  <div>
                    <div class="text-h6 font-weight-bold mb-1">|x| &gt; a</div>
                    <div>&rarr; x &gt; a หรือ x &lt; -a</div>
                  </div>
                </v-card>
              </v-col>
              <v-col cols="12" sm="4">
                <v-card variant="tonal" color="error" class="pa-4 text-center h-100 d-flex align-center justify-center">
                   <div>
                    <div class="text-h6 font-weight-bold mb-1">|a| = |b|</div>
                    <div>&rarr; a<sup>2</sup> = b<sup>2</sup></div>
                  </div>
                </v-card>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="7. พื้นฐานระบบเลขโรมัน">
            <template v-slot:prepend>
              <v-icon color="indigo">mdi-book-open-variant</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <p class="mb-4">ชาวโรมันนำตัวหนังสือกรีกมาดัดแปลงเป็นตัวเลขโรมันเมื่อประมาณ 300 - 100 ปีก่อนคริสต์ศักราช โดยใช้สัญลักษณ์พื้นฐาน 7 ตัว</p>
            
            <v-table density="compact" class="border rounded-lg mb-4">
              <thead>
                <tr class="bg-indigo-lighten-5">
                  <th class="text-center font-weight-bold">ตัวเลขโรมัน</th>
                  <th v-for="sym in ['I', 'V', 'X', 'L', 'C', 'D', 'M']" :key="sym" class="text-center">{{ sym }}</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td class="text-center font-weight-bold bg-grey-lighten-4">ตัวเลขฮินดูอาราบิก</td>
                  <td v-for="val in [1, 5, 10, 50, 100, 500, 1000]" :key="val" class="text-center">{{ val }}</td>
                </tr>
              </tbody>
            </v-table>

            <v-alert type="info" variant="tonal" border="start" class="mb-4">
              <strong>หลักการเขียนที่สำคัญ:</strong> สัญลักษณ์แต่ละตัวเขียนติดกันได้ไม่เกิน 3 ตัว และการเขียนจำนวนที่มีค่ามากให้ใช้เครื่องหมายขีด (-) บนสัญลักษณ์เพื่อให้มีค่าเป็น 1,000 เท่า
            </v-alert>
          </v-card-text>
        </v-card>

        <v-row class="mb-6">
          <v-col cols="12" md="6">
            <v-card variant="tonal" color="green-lighten-4" class="pa-3 h-100">
              <div class="text-subtitle-1 font-weight-bold text-green-darken-3 mb-2">หลักการเพิ่ม (Addition)</div>
              <p class="text-body-2 mb-2 text-green-darken-3">เขียนสัญลักษณ์เรียงกันไปจากค่ามากไปหาน้อย</p>
              <ul class="pl-4 text-body-2">
                <li class="text-green-darken-3">III = 1+1+1 = 3$</li>
                <li class="text-green-darken-3">XXII = 10+10+1+1 = 22$</li>
                <li class="text-green-darken-3">DCCLXXVII = 500+100+100+50+10+10+5+1+1 = 777$</li>
              </ul>
            </v-card>
          </v-col>

          <v-col cols="12" md="6">
            <v-card variant="tonal" color="red-lighten-4" class="pa-3 h-100">
              <div class="text-subtitle-1 font-weight-bold text-red-darken-3 mb-2">หลักการลด (Subtraction)</div>
              <p class="text-body-2 mb-2 text-red-darken-3">เขียนตัวเลขที่มีค่าน้อยไว้หน้าตัวเลขที่มีค่ามาก</p>
              <ul class="pl-4 text-body-2">
                <li class="text-red-darken-3">IV = 5-1 = 4</li>
                <li class="text-red-darken-3">IX = 10-1 = 9</li>
                <li class="text-red-darken-3">XL = 50-10 = 40</li>
                <li class="text-red-darken-3">CD = 500-100 = 400</li>
              </ul>
              <div class="text-caption mt-2 text-red-darken-4">* ตัวเลขลบมีเพียง I, X, C เท่านั้น</div>
            </v-card>
          </v-col>
        </v-row>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="8. แบบฝึกหัดทบทวน (Exercises)">
            <template v-slot:prepend>
              <v-icon color="indigo">mdi-clipboard-list-outline</v-icon>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <div class="text-subtitle-1 font-weight-bold mb-3">จงเติมคำตอบให้ถูกต้อง:</div>
            
            <v-row>
              <v-col cols="12" md="6">
                <v-list density="compact">
                  <v-list-subheader>เขียนเลขฮินดูอาราบิกเป็นเลขโรมัน</v-list-subheader>
                  <v-list-item v-for="(q, i) in ['238', '953', '5,738', '34,639']" :key="i">
                    <template v-slot:prepend><v-icon size="small">mdi-pencil</v-icon></template>
                    <v-list-item-title class="text-blue">{{ i+1 }}. เปลี่ยน {{ q }} เป็นเลขโรมัน</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-col>

              <v-col cols="12" md="6">
                <v-list density="compact">
                  <v-list-subheader>เขียนเลขโรมันเป็นเลขฮินดูอาราบิก</v-list-subheader>
                  <v-list-item v-for="(q, i) in ['MMDXLVII', 'VMDXCIX', 'XDCXCI', 'CDXXVDCL']" :key="i">
                    <template v-slot:prepend><v-icon size="small">mdi-pencil</v-icon></template>
                    <v-list-item-title class="text-blue">{{ i+5 }}. เปลี่ยน {{ q }} เป็นเลขฐานสิบ</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="9. ศึกษาเพิ่มเติม (Further Study)">
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
              href="/lessons/RealNm.pdf" 
              target="_blank"
              color="red-darken-1" 
              size="large" 
              prepend-icon="mdi-file-pdf-box"
              elevation="2"
              class="mb-4"
            >
              เปิดดูเอกสารประกอบ(จำนวนจริง) (PDF)
            </v-btn>
            &nbsp;&nbsp;
            <v-btn 
              href="/lessons/คณิตศาสตร์คอมฯ_01.pdf" 
              target="_blank"
              color="red-darken-1" 
              size="large" 
              prepend-icon="mdi-file-pdf-box"
              elevation="2"
              class="mb-4"
            >
              เปิดดูเอกสารประกอบ(เลขโรมัน) (PDF)
            </v-btn>
            <br>
            <v-btn 
              href="/lessons/คณิตคอม.pdf" 
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
              href="https://youtu.be/6_heJQ7nsrQ?si=gES5_2n__fHOkdQG" 
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
// ไม่ต้องตั้งค่าเพิ่มเติมหากใช้ vite-plugin-vuetify
</script>

<style scoped>
.v-card-text {
  line-height: 1.8;
}
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