# 🎬 SeriesHub (JeenReel)

แพลตฟอร์มดูซีรี่ย์ออนไลน์แบบ Full Stack\
พัฒนาโดยใช้ 
Next.js (App Router)
PostgreSQL
Prisma
NextAuth

------------------------------------------------------------------------

## 📌 Overview

SeriesHub คือแพลตฟอร์มสตรีมมิ่งซีรี่ย์ออนไลน์ที่มีระบบครบวงจร
ทั้งฝั่งผู้ใช้งานและผู้ดูแลระบบ

ฟีเจอร์หลัก: 
- 🎥 ดูซีรี่ย์พร้อม Custom Video Player
- ⏯ ดูต่อจากตอนที่ค้างไว้ (Watch History)
- 📢 ระบบโฆษณากั้นก่อนดู
- 💰เติมเงินด้วย QR PromptPay / SlipsPlus
- 👑 ระบบ VIP / Coin / Gift Code
- 🎁 เช็คอินรายวัน - 🛠 Admin Dashboard จัดการระบบทั้งหมด

------------------------------------------------------------------------

## 🛠 Tech Stack

-   Next.js (App Router)
-   React + TypeScript
-   PostgreSQL
-   Prisma ORM
-   NextAuth.js
-   Tailwind CSS
-   hls.js (HLS Streaming)
-   qrcode (QR PromptPay)
-   bcryptjs

------------------------------------------------------------------------

## 🧭 Routes Overview

### User

-   / หน้าแรก
-   /series/\[slug\] รายละเอียดซีรี่ย์
-   /series/\[slug\]/ep/\[ep\] ดูตอน
-   /history ประวัติการดู
-   /favorites รายการโปรด
-   /profile โปรไฟล์ / เช็คอิน
-   /topup เติมเงิน
-   /vip VIP
-   /gifcode แลก Gift Code

### Admin

-   /admin
-   /admin/series
-   /admin/ads
-   /admin/categories
-   /admin/tags
-   /admin/giftcodes
-   /admin/vip
-   /admin/users
-   /admin/site-settings
-   /admin/topup-settings
-   /admin/reports

------------------------------------------------------------------------

# 🚀 Installation Guide

## 1️⃣ Requirements

-   Node.js v18+
-   PostgreSQL v13+
-   npm
-   Git

## 2️⃣ Clone Project

``` bash
git clone <repository-url>
cd jeenreel
```

## 3️⃣ Environment Variables

สร้างไฟล์ `.env.local`

``` env
DATABASE_URL="postgresql://postgres:password@localhost:5432/serieshub?schema=public"
NEXTAUTH_SECRET="your-secret"
NEXTAUTH_URL="http://localhost:3009"
STREAM_TOKEN_SECRET="stream-secret"
TOPUP_QR_PREFIX="promptpay-payload"
CRON_TOKEN="cron-token"
```

## 4️⃣ Setup Database

``` bash
createdb serieshub
npm install
npx prisma migrate deploy
npx prisma generate
npx prisma studio
```

## 5️⃣ Run Development

``` bash
npm run dev
```

เปิด http://localhost:3009

## 6️⃣ Production

``` bash
npm run build
npm run start
```

## 7️⃣ Docker

``` bash
docker compose up -d --build
```

## 8️⃣ Admin Setup

-   สมัคร user
-   เปิด Prisma Studio
-   เปลี่ยน role เป็น admin
-   Login ใหม่
-   เข้า /admin

------------------------------------------------------------------------

## ⚙️ Core Systems

### 🎬 Video Player

-   รองรับ HLS (.m3u8)
-   Auto-hide controls
-   Fullscreen
-   Skip / Resume
-   Popup Ads

### ⏯ Watch History

-   บันทึก episode + เวลา
-   ใช้สำหรับดูต่อ

### 📢 Ads System

-   Non-VIP ต้องดูโฆษณา
-   VIP ข้ามโฆษณา

### 💰 Topup

-   สร้าง QR
-   ตรวจสลิป SlipsPlus
-   เติม Coin

### 👑 VIP

-   ไม่มีโฆษณา
-   มีวันหมดอายุ
-   บันทึกประวัติ

### 🎁 Gift Code

-   Coin
-   VIP
-   ดูฟรีเฉพาะเรื่อง

### 📅 Daily Check-in

-   เช็คอินวันละครั้ง
-   ได้ Coin / Point

------------------------------------------------------------------------

## ❗ Troubleshooting

-   Prisma ต่อ DB ไม่ได้ → ตรวจ DATABASE_URL
-   เข้า admin ไม่ได้ → ตรวจ role
-   Video ไม่เล่น → ตรวจ HLS URL

------------------------------------------------------------------------

## 🖥️ Demo
<img width="482" height="707" alt="image" src="https://github.com/user-attachments/assets/2105d381-b8d7-4d54-80bc-194d919e0d3c" />
<img width="485" height="708" alt="image" src="https://github.com/user-attachments/assets/0c1f5ed2-f5ea-479d-8edf-858b1159e59f" />
<img width="483" height="707" alt="image" src="https://github.com/user-attachments/assets/f5d94802-7e71-43c2-abe3-4312c4f9662f" />
<img width="480" height="707" alt="image" src="https://github.com/user-attachments/assets/75eb7334-3af6-47a9-9454-8d31d8fdcc6b" />
<img width="483" height="707" alt="image" src="https://github.com/user-attachments/assets/3d8d9e03-de6a-4d69-bb8a-77aa15074302" />
<img width="483" height="706" alt="image" src="https://github.com/user-attachments/assets/4078fa5c-f2c3-488b-acc8-a035c66a6b06" />
<img width="1577" height="733" alt="image" src="https://github.com/user-attachments/assets/2cdbe40f-c8c7-4d9e-b69e-03ff61d93141" />
<img width="1570" height="736" alt="image" src="https://github.com/user-attachments/assets/fcd95a0a-977d-4ca3-ba84-31c442f56b7a" />

------------------------------------------------------------------------

## 📄 License

Private / Internal Project

------------------------------------------------------------------------

## 💳 Price

- Project = 20,000 บาท
- DramaWave API = 5,000 บาท
- GoodShort API = 5,000 บาท
- StardustTV API = 5,000 บาท
- DramaBox API = 4,000 บาท
- FlickReels API = 4,000 บาท
- Melolo API = 4,000 บาท
- NetShort API = 4,000 บาท
