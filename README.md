# 🚀 Go Thailand Monorepo Project

ยินดีต้อนรับสู่ Monorepo ของทีม **Go Thailand** สำหรับจัดการ HTML & CSS โปรเจกต์ร่วมกันสำหรับสมาชิกในทีม 5 คน

---

## 📁 โครงสร้างโปรเจกต์ (Project Structure)

```text
go-thailand/
├── apps/                          # รวมแอปพลิเคชัน / หน้าเว็บแต่ละส่วน
│   ├── main-website/              # [โปรเจกต์ 1] เว็บไซต์หลัก
│   │   ├── index.html
│   │   ├── about.html
│   │   └── css/
│   │       └── page-style.css
│   ├── admin-dashboard/           # [โปรเจกต์ 2] หน้าระบบจัดการหลังบ้าน
│   │   ├── index.html
│   │   └── css/
│   │       └── dashboard-style.css
│   └── landing-page/              # [โปรเจกต์ 3] หน้าการตลาด / โปรโมชัน
│       └── index.html
│
├── shared/                        # ศูนย์รวมทรัพยากรกลางที่ทุกคนดึงไปใช้ร่วมกัน
│   ├── styles/                    # Core Design System
│   │   ├── variables.css          # ค่าตัวแปรสี, ฟอนต์, Spacing
│   │   ├── reset.css              # ล้างค่าสไตล์ดั้งเดิมของ Browser
│   │   └── components.css         # UI Components กลาง (ปุ่ม, การ์ด, Navbar, Form)
│   ├── assets/
│   │   ├── images/                # โลโก้, แบนเนอร์กลาง
│   │   └── icons/                 # SVG ไอคอนต่างๆ
│   └── js/
│       └── main.js                # JavaScript Helper ฟังก์ชันกลาง
│
├── .gitignore
└── README.md
```

---

## 👥 การแบ่งหน้าที่รับผิดชอบในทีม (Team Responsibilities)

1. **Design System Owner**: ดูแล `shared/styles/` (`variables.css`, `components.css`)
2. **Main Website Developer**: ดูแล `apps/main-website/`
3. **Dashboard Developer**: ดูแล `apps/admin-dashboard/`
4. **Landing Page Developer**: ดูแล `apps/landing-page/`
5. **Assets & QA Integration**: ดูแล `shared/assets/` และช่วยตรวจ Code Review (PR)

---

## 🛠️ วิธีการดึง Design System กลางไปใช้ใน HTML

ในไฟล์ HTML ของแต่ละแอป ให้เรียกใช้ไฟล์ใน `shared/styles/` ผ่าน Relative Path ดังนี้:

```html
<!-- 1. โหลด Design System กลางก่อนเสมอ -->
<link rel="stylesheet" href="../../shared/styles/variables.css">
<link rel="stylesheet" href="../../shared/styles/reset.css">
<link rel="stylesheet" href="../../shared/styles/components.css">

<!-- 2. โหลดสไตล์เฉพาะของหน้านั้นๆ -->
<link rel="stylesheet" href="css/page-style.css">
```

---

## 🌿 Git & Branching Strategy

1. **ห้าม Push ตรงเข้า `main`**: ให้สลับไป `develop` เสมอ
2. **แตก Branch ใหม่ทุกครั้ง**: `git checkout -b feature/your-feature-name`
3. **ส่ง Pull Request (PR)**: เปิด PR เข้า `develop` และให้เพื่อนในทีมช่วยตรวจ Approve ก่อน Merge
