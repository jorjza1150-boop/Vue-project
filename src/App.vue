<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
const closeMenu = () => { menuOpen.value = false }
const technologies = [
  { number: '01', name: 'Vue.js 3', tag: 'FRAMEWORK', description: 'สร้างส่วนติดต่อผู้ใช้ด้วย Component และ Composition API', icon: 'V', className: 'vue' },
  { number: '02', name: 'Bootstrap 5', tag: 'UI TOOLKIT', description: 'จัดวางหน้าเว็บด้วยระบบ Grid และปรับให้รองรับทุกขนาดหน้าจอ', icon: 'B', className: 'bootstrap' },
  { number: '03', name: 'Vite', tag: 'BUILD TOOL', description: 'เครื่องมือพัฒนาที่ช่วยให้เริ่มต้นและสร้างโปรเจกต์ได้อย่างรวดเร็ว', icon: 'ϟ', className: 'vite' },
]
</script>

<template>
  <header class="site-header">
    <nav class="navbar navbar-expand-md container" aria-label="เมนูหลัก">
      <a class="navbar-brand brand" href="#home" @click="closeMenu"><span class="brand-mark">cp<span>.</span></span><span class="brand-caption">Chatree<br>Puangpaachung</span></a>
      <button class="navbar-toggler" type="button" aria-label="เปิดหรือปิดเมนู" :aria-expanded="menuOpen" aria-controls="main-nav" @click="menuOpen = !menuOpen"><span class="navbar-toggler-icon"></span></button>
      <div id="main-nav" class="collapse navbar-collapse" :class="{ show: menuOpen }">
        <div class="navbar-nav ms-auto align-items-md-center gap-md-4">
          <a class="nav-link active" href="#home" aria-current="page" @click="closeMenu">หน้าแรก</a>
          <a class="nav-link" href="#about" @click="closeMenu">เกี่ยวกับฉัน</a>
          <a class="nav-link" href="#project" @click="closeMenu">เกี่ยวกับโปรเจกต์</a>
          <a class="student-badge" href="#about" @click="closeMenu"><span class="status-dot"></span> STUDENT · 69702075</a>
        </div>
      </div>
    </nav>
  </header>

  <main>
    <section id="home" class="hero container">
      <div class="row align-items-center gy-5">
        <div class="col-lg-7 hero-copy">
          <p class="eyebrow"><span class="short-line"></span> MY FIRST WEB PROJECT</p>
          <h1>เริ่มต้นเรียนรู้<br>สร้างสรรค์<span class="accent">สิ่งใหม่.</span></h1>
          <p class="hero-description">ยินดีต้อนรับสู่เว็บไซต์ของผม พื้นที่เล็ก ๆ สำหรับการเรียนรู้<br class="d-none d-xl-block"> และเริ่มต้นพัฒนาเว็บไซต์ด้วย Vue.js 3 และ Bootstrap 5</p>
          <div class="d-flex flex-wrap gap-3 hero-actions">
            <a class="btn btn-primary" href="#about">รู้จักผู้จัดทำ <span aria-hidden="true">↗</span></a>
            <a class="btn btn-outline-secondary" href="#project">สำรวจโปรเจกต์ <span aria-hidden="true">↓</span></a>
          </div>
          <div class="hero-note"><span class="note-symbol" aria-hidden="true">✳</span><span>ก้าวแรกของการเรียนรู้ เริ่มจากการลงมือทำ</span></div>
        </div>
        <div class="col-lg-5">
          <div class="visual-panel" aria-label="ภาพประกอบการพัฒนาเว็บไซต์">
            <div class="visual-top"><span>BUILD SOMETHING NEW</span><span aria-hidden="true">↗</span></div>
            <div class="orbit orbit-one"></div><div class="orbit orbit-two"></div>
            <div class="floating-tag tag-vue"><span class="mini-dot"></span> Vue.js 3</div>
            <div class="code-window">
              <div class="window-bar"><div class="window-dots"><i></i><i></i><i></i></div><span>Home.vue</span><span aria-hidden="true">⋯</span></div>
              <div class="code-content"><span class="code-muted">&lt;template&gt;</span><br><span class="code-indent">&lt;<span class="code-lime">hello-world</span>&gt;</span><br><span class="code-greeting">Hello, I'm</span><br><strong>Chatree<span>.</span></strong><br><span class="code-indent">&lt;/<span class="code-lime">hello-world</span>&gt;</span><br><span class="code-muted">&lt;/template&gt;</span></div>
              <div class="window-footer"><span><i class="status-dot"></i> Ready to create</span><span>UTF-8</span></div>
            </div>
            <div class="floating-tag tag-bootstrap"><b>B</b> Bootstrap 5</div>
            <div class="visual-bottom"><span>LEARN. BUILD. GROW.</span><span>001 / ∞</span></div>
          </div>
        </div>
      </div>
    </section>

    <section id="about" class="about-section container">
      <div class="profile-strip row align-items-center gy-4">
        <div class="col-lg-5 d-flex align-items-center gap-3"><div class="avatar">CP</div><div><p class="eyebrow mb-2">MEET THE CREATOR</p><h2 class="creator-name">Chatree Puangpaachung</h2><p class="mb-0 creator-subtitle">ผู้จัดทำเว็บไซต์ · นักศึกษา</p></div></div>
        <div class="col-sm-6 col-lg-3 profile-detail"><span>รหัสนักศึกษา</span><strong>69702075</strong></div>
        <div class="col-sm-6 col-lg-4 profile-detail"><span>สิ่งที่กำลังเรียนรู้</span><strong class="learning">Web Design & Development <span aria-hidden="true">↗</span></strong></div>
      </div>
    </section>

    <section id="project" class="project-section container">
      <div class="section-heading"><div><p class="eyebrow">THE FOUNDATION</p><h2>เบื้องหลังเว็บไซต์นี้</h2></div><p>เครื่องมือที่เปลี่ยนไอเดีย<br>ให้กลายเป็นเว็บไซต์ที่ใช้งานได้จริง</p></div>
      <div class="row g-4"><div v-for="technology in technologies" :key="technology.name" class="col-md-4"><article class="technology-card h-100"><div class="d-flex justify-content-between align-items-start"><div class="tech-icon" :class="technology.className">{{ technology.icon }}</div><span class="card-number">{{ technology.number }}</span></div><p class="tech-tag">{{ technology.tag }}</p><h3>{{ technology.name }}</h3><p class="tech-description">{{ technology.description }}</p></article></div></div>
      <div class="project-caption"><span class="status-dot"></span> ออกแบบให้รองรับ Desktop, Tablet และ Mobile <span class="caption-end">สร้างด้วยความตั้งใจ <span aria-hidden="true">✳</span></span></div>
    </section>
  </main>
  <footer class="site-footer"><div class="container d-flex flex-wrap justify-content-between gap-2"><p>© {{ new Date().getFullYear() }} Chatree Puangpaachung <span>· 69702075</span></p><p>Vue.js 3 <span>+</span> Bootstrap 5</p></div></footer>
</template>
