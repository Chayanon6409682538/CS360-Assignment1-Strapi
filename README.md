# Strapi
## assignment1

### Strapi คือ Headless CMS(Content Management System) ซึ่งเป็น opensource ที่พัฒนาด้วย JavaScript และ Node.js

วัตถุประสงค์ของ Strapi คือ Strapi ช่วยให้นักพัฒนาสามารถจัดการเนื้อหาผ่านอินเตอร์เฟซได้ง่าย ลดขั้นตอนในการเขียนโค้ด และเนื่องจาก Strapi เป็น opensource จึงทำให้สามารถปรับแต่งความสามารถได้ตามความต้องการของ Project Strapi ช่วยให้การจัดการเนื้อหาทำได้ง่ายและยืดหยุ่น โดยไม่ต้องกังวลเกี่ยวกับการจัดการการแสดงผลเนื้อหาหรือการสร้าง API ขึ้นมาจากศูนย์

สำหรับกรณีการใช้งาน (Use cases) ของ Strapi มีดังนี้
Website
- สามารถใช้จัดการเนื้อหาของเว็บไซต์ได้ เช่น บทความหรือเพจต่างๆ Strapi ช่วยให้จัดการเนื้อหาง่ายขึ้น
Mobile Applications
- ใช้ในการจัดการข้อมูลที่ mobile applications ต้องการเช่น ข้อมูลผู้ใช้หรือเนื้อหาต่างๆ โดยเชื่อมต่อแอปพลิเคชั่นผ่าน API
Omnichannel Projects (โปรเจกต์หลายช่องทาง)
- สามารถช่วยในการจัดการเนื้อหาที่จะเผยแพร่หลายช่องทาง เช่น เว็บไซต์, แอปพลิเคชั่นและแพลตฟอร์มอื่นๆ

องค์ประกอบของ Strapi
Content Types Builder
- ช่วยให้สามารถสร้างและจัดการ content types ได้
API Generator
- Strapi จะสร้าง API โดยอัตโนมัติหลังสร้าง content types เพื่อใช้ในการเข้าถึงหรือจัดการข้อมูลนั้นๆ
User Management
- Strapi มีระบบจัดการผู้ใช้ที่ช่วยควบคุมสิทธิ์ในการเข้าถึงและจัดการเนื้อหา
Plugins
- นักพัฒนาสามารถเพิ่ม plugin ต่างๆเพื่อขยายความสามารถของระบบเช่น ระบบการยืนยันตัวตนหรือการเชื่อมต่อกับบริการภายนอก

อ้างอิงจาก [document](https://docs.strapi.io/user-docs/content-manager)

### ขั้นตอนการติดตั้ง Strapi

แนะนำให้ทำผ่าน Linux หรือ WSL ดีที่สุด ในที่นี่จะเลือกใช้โดยทำผ่าน WSL

1.ตรวจสอบเวอร์ชั่น Node.js และ NPM ด้วยคำสั่ง

```
node -v
npm -v
```

หากยังไม่ได้ติดตั้งให้ใช้คำสั่งนี้เพื่อติดตั้ง
```
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
```

2.เมื่อติดตั้ง Node.js และ NPM และเช็คเวอร์ชั่นเรียบร้อยแล้ว ให้สร้างโปรเจกต์ใหม่สำหรับ Strapi ด้วยคำสั่งนี้
```
npx create-strapi-app@latest "ชื่อโปรเจกต์" --quickstart
หรือ
yarn create strapi-app "ชื่อโปรเจกต์"
```

คำสั่งนี้จะทำการดาวน์โหลด Strapi และสร้างโปรเจกต์ใหม่ในโฟลเดอร์ที่เราตั้งชื่อ

3.หลังจากที่โปรเจกต์ถูกสร้างขึ้นแล้ว ให้เข้าไปที่โฟลเดอร์ของโปรเจกต์โดยใช้คำสั่ง
```
cd my-project
```

4.จากนั้นให้เริ่มต้น Strapi ด้วยคำสั่ง
```
npm run develop
```
หรือ
```
yarn develop
```

5.เมื่อ Strapi เริ่มทำงานสามารถเข้าไปที่ http://localhost:1337/admin ในเว็บเบราว์เซอร์เพื่อสร้างบัญชีผู้ดูแลระบบและเริ่มใช้งาน Strapi ได้

6.หากต้องการหยุดการทำงานของ Strapi สามารถกด \\Ctrl + C\\ ใน Terminal ได้และหากอยากเริ่มการทำงานใหม่ให้ใช้คำสั่งในข้อ 4.

อ้างอิงข้อมูลจาก [document](https://docs.strapi.io/dev-docs/installation/cli)

### ไฟล์ .gitignore

ไฟล์ .gitignore เป็นไฟล์ที่มีความสำคัญในระบบควบคุมเวอร์ชัน (Version Control System) อย่าง Git โดยมีจุดประสงค์และความสำคัญคือ 

- ป้องกันการ commit ไฟล์ที่ไม่ต้องการ เช่น ไฟล์ชั่วคราว ไฟล์ที่สร้างโดยระบบปฏิบัติการ ไฟล์บันทึก (log files)
- เพื่อรักษาความปลอดภัย โดยละเว้นไฟล์ที่มีข้อมูลสำคัญ เช่น ไฟล์คอนฟิก .env ที่เก็บคีย์ API หรือรหัสผ่าน ป้องกันไม่ให้ข้อมูลสำคัญเหล่านี้ถูกเผยแพร่ใน repository สาธารณะ
- ช่วยให้ repository สะอาด มีแค่ไฟล์ที่สำคัญต่อการพัฒนา
- ช่วยให้การ deploy ทำได้ง่ายขึ้นด้วยการละเว้นไฟล์ที่ไม่จำเป็นในการ deploy 

อ้างอิงข้อมูลจาก [GitHub](https://docs.github.com/en/get-started/getting-started-with-git/ignoring-files?platform=linux)
[git](https://git-scm.com/docs/gitignore/en )
[Medium Blogs](https://medium.com/odds-team/gitignore-%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%AA%E0%B8%B2%E0%B8%A1%E0%B8%B2%E0%B8%A3%E0%B8%96%E0%B8%82%E0%B8%AD%E0%B8%87-git-version-control-a77d1677a9d3)

### ขั้นตอนในการนำเว็ปแอปพลิเคชันขึ้นให้บริการบน AWS

1. login เข้า aws account จากนั้น search หา ec2 กดเข้าไปและสร้าง instance โดย instance type คือ t2.small
2. ตั้งค่า inbound rules ให้เข้าถึงได้จากเครื่องใดๆในอินเทอร์เน็ตโดย 
\\set type เป็น all traffic
Protocol เป็น all 
Port range เป็น all 
และ source เป็น 0.0.0.0/0\\
3. จากนั้นใช้เครื่องของตัวเอง connect เข้าสู่เครื่องของ ec2 instance
4. เมื่อ connect สำเร็จให้ install node.js และ git
5. เมื่อ install สำเร็จให้ใช้คำสั่ง git clone เพื่อ clone repository ที่มี application มาไว้บนเครื่อง ec2
6. รัน npm install เพื่อทำให้โปรเจคสมบูรณ์
7. สร้างไฟล์ .env และคัดลอกข้อมูลข้างในมาใส่ เนื่องจากไฟล์ .env อยู่ใน .gitignore เพื่อป้องกันข้อมูลสำคัญทำให้ไม่ถูก push ลง git repository
8. ใช้คำสั่ง
```
 NODE_ENV=production npm run build
```
 
เพื่อ build
9. ใช้คำสั่ง 
```
NODE_ENV=production npm run start
```
เพื่อเริ่มรัน server
10. ใช้ Public IP ของ ec2 instance ที่เราใช้เพื่อเปิดหน้าเว็บแอปพลิเคชัน เช่น \\http://54.224.73.115:1337\\
- 54.224.73.115 คือ Public IP และตามด้วย Port 1337 เนื่องจากเปิดเซิฟเวอร์ที่ Port 1337

อ้างอิงจาก [document](https://docs.strapi.io/dev-docs/deployment)

