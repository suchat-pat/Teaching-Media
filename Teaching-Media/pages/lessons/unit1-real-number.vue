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
          <v-card-item title="7. แบบฝึกหัดทบทวน: ระบบตัวเลขฐาน (Number Systems Review)">
            <template v-slot:prepend>
              <v-icon color="primary">mdi-pencil-box-multiple</v-icon>
            </template>
            <template v-slot:append>
               <v-chip size="small" color="primary" label>ชุดที่ 4</v-chip>
            </template>
          </v-card-item>
          <v-divider></v-divider>
          <v-card-text>
            <v-row>
              <v-col cols="12" md="6">
                <v-card variant="tonal" class="h-100">
                  <v-card-title class="text-subtitle-1 font-weight-bold bg-primary text-white">
                    A. จงเขียนเป็นเลขฐานสิบ
                  </v-card-title>
                  <v-table density="compact">
                    <thead>
                      <tr>
                        <th class="text-left" width="50">ข้อ</th>
                        <th class="text-left">โจทย์</th>
                        <th class="text-left text-grey">คำตอบ (พื้นที่ว่าง)</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr><td>1</td><td>11110<sub>2</sub></td><td>...................................</td></tr>
                      <tr><td>2</td><td>0000<sub>2</sub></td><td>...................................</td></tr>
                      <tr><td>3</td><td>22110<sub>3</sub></td><td>...................................</td></tr>
                      <tr><td>4</td><td>30010<sub>4</sub></td><td>...................................</td></tr>
                      <tr><td>5</td><td>11100<sub>2</sub></td><td>...................................</td></tr>
                      <tr><td>6</td><td>122<sub>3</sub></td><td>...................................</td></tr>
                      <tr><td>7</td><td>11200<sub>3</sub></td><td>...................................</td></tr>
                      <tr><td>8</td><td>11010<sub>2</sub></td><td>...................................</td></tr>
                      <tr><td>9</td><td>000<sub>2</sub></td><td>...................................</td></tr>
                    </tbody>
                  </v-table>
                </v-card>
              </v-col>

              <v-col cols="12" md="6">
                <v-card variant="tonal" class="h-100">
                  <v-card-title class="text-subtitle-1 font-weight-bold bg-teal-darken-1 text-white">
                    B. จงเขียนเป็นเลขฐานต่างๆ
                  </v-card-title>
                  <v-table density="compact">
                    <thead>
                      <tr>
                        <th class="text-left" width="50">ข้อ</th>
                        <th class="text-left">โจทย์ (ฐานสิบ)</th>
                        <th class="text-left text-grey">เป้าหมาย</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr><td>1</td><td>34</td><td>เป็น ฐาน 5</td></tr>
                      <tr><td>2</td><td>73</td><td>เป็น ฐาน 4</td></tr>
                      <tr><td>3</td><td>82</td><td>เป็น ฐาน 6</td></tr>
                      <tr><td>4</td><td>97</td><td>เป็น ฐาน 8</td></tr>
                      <tr><td>5</td><td>131</td><td>เป็น ฐาน 7</td></tr>
                      <tr><td>6</td><td>147</td><td>เป็น ฐาน 8</td></tr>
                      <tr><td>7</td><td>250</td><td>เป็น ฐาน 9</td></tr>
                      <tr><td>8</td><td>347</td><td>เป็น ฐาน 12</td></tr>
                      <tr><td>9</td><td>467</td><td>เป็น ฐาน 11</td></tr>
                    </tbody>
                  </v-table>
                </v-card>
              </v-col>
            </v-row>
            
            <div class="mt-4 text-caption text-grey text-center">
              <v-icon icon="mdi-lightbulb-on-outline" size="small" class="mr-1"></v-icon>
              Tips: การแปลงฐาน 10 ให้ใช้วิธีหารสั้นเอาเศษ ส่วนการแปลงเป็นฐาน 10 ให้ใช้การกระจายค่าประจำหลัก
            </div>
          </v-card-text>
        </v-card>

        <v-card class="mb-6" variant="outlined">
          <v-card-item title="8. ศึกษาเพิ่มเติม (Further Study)">
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
              เปิดดูเอกสารประกอบ (PDF)
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