<template>
    <v-app>
        <v-app-bar color="blue-darken-4" class="pa-1">
            <v-app-bar-nav-icon @click="drawer = !drawer" variant="text"></v-app-bar-nav-icon>
            <v-toolbar-title>Mathematics for Computer</v-toolbar-title>
            <v-btn icon="mdi-home" variant="text" to="/"></v-btn>&nbsp;&nbsp;
        </v-app-bar>

        <ClientOnly>
            <v-navigation-drawer v-model="drawer" width="260" color="#e6e6e6" app :temporary="isMobile" :permanent="!isMobile">
                <v-list density="compact">
                    <template v-for="item in roles" :key="item.title">
                        
                        <v-list-group v-if="item.children" :value="item.title">
                            <template v-slot:activator="{ props }">
                                <v-list-item v-bind="props" :title="item.title"></v-list-item>
                            </template>

                            <v-list-item
                                v-for="child in item.children"
                                :key="child.title"
                                :title="child.title"
                                :to="child.to"
                            ></v-list-item>
                        </v-list-group>

                        <v-list-item v-else :title="item.title" :to="item.to"></v-list-item>

                    </template>
                </v-list>
            </v-navigation-drawer>
        </ClientOnly>

        <v-main>
            <v-container fluid>
                <NuxtPage />
            </v-container>
        </v-main>
    </v-app>
</template>

<script setup lang="ts">
import { useDisplay } from 'vuetify';
import { ref, computed } from 'vue'; // อย่าลืม import ref และ computed

const { mdAndDown } = useDisplay()
const isMobile = computed(() => mdAndDown.value)
const drawer = ref(false)

// กำหนด Type ให้ชัดเจน (Optional แต่ดีสำหรับ TypeScript)
interface RoleItem {
    title: string;
    to?: string;
    children?: RoleItem[];
}

const roles: RoleItem[] = [
    // Main
    { title: 'หน้าหลัก', to: '/' },

    // lessons (มี children)
    {
        title: 'บทเรียน',
        children: [
            // Real-Number-System
            { title: 'หน่วยที่ 1 ระบบจำนวนจริง', to: '/lessons/unit1-real-number' },

            // Number-Base-Systems
            { title: 'หน่วยที่ 2 ระบบเลขฐาน', to: '/lessons/unit2-number-systems' },

            // Number-Base-Calculation
            { title: 'หน่วยที่ 3 การคำนวณเลขฐาน', to: '/lessons/unit3-calculation' },

            // Logic
            { title: 'หน่วยที่ 4 ตรรกศาสตร์', to: '/lessons/unit4-logic' },

            // Boolean-Algebra
            { title: 'หน่วยที่ 5 พีชคณิตบูลีน', to: '/lessons/unit5-boolean' },

            // Matrix
            { title: 'หน่วยที่ 6 เมทริกซ์', to: '/lessons/unit6-matrix' },
        ]
    },

    // Using-Songs
    { title: 'เทคนิคการจำด้วยบทเพลง', to: '/Using-Songs' },
    
    // Quiz
    { title: 'แบบทดสอบ', to: '/Quiz' },
    
    // Creators
    { title: 'ผู้จัดทำ', to: '/creators' },
]
</script>

<style scoped>
/* 1. นำเข้าฟอนต์ Prompt จาก Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500&display=swap');

/* 2. ปรับแต่งตัวหนังสือในเมนู */
:deep(.v-list-item-title) {
    font-family: 'Prompt', sans-serif !important; /* เปลี่ยนฟอนต์ที่นี่ */
    color: black !important; /* สีดำตามที่ขอ */
    font-size: 16px !important; /* เพิ่มขนาดนิดหน่อยให้ดูเต็มตาสวยขึ้น */
    letter-spacing: 0.5px; /* ระยะห่างตัวอักษรนิดนึงเพื่อให้ดูโปร่ง */
}

/* แถม: ปรับฟอนต์ตรงหัวข้อใหญ่ด้านบนด้วยก็ได้ครับ */
.v-toolbar-title {
    font-family: 'Prompt', sans-serif !important;
}
</style>