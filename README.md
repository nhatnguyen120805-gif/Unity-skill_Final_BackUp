# Unity Skill — Unified Fullstack Monorepo

Hệ thống kết hợp trọn vẹn giữa **Backend (Spring Boot)** và **Frontend (Next.js)** trong cấu trúc Monorepo thống nhất, bảo toàn toàn bộ lịch sử commit Git gốc của cả 2 dự án.

---

## 🏗️ Cấu trúc Thư mục

```text
Unity-skill_Final_BackUp/
├── backend/                  # Java Spring Boot 3 + JDK 21 (API & WebSocket STOMP)
│   ├── src/
│   ├── pom.xml
│   ├── Dockerfile
│   └── bao cao dacs.docx    # Báo cáo Đồ án cơ sở
├── frontend/                 # Next.js 16 + React 19 + Tailwind v4 + TypeScript
│   ├── src/
│   ├── package.json
│   ├── Dockerfile
│   └── next.config.ts
├── docker-compose.yml        # Orchestration 1-lệnh chạy cả FE + BE
├── .gitignore                # Bộ lọc git kết hợp chuẩn Java + Node.js
└── README.md
```

---

## 🚀 Khởi chạy Nhanh

### Cách 1: Sử dụng Docker Compose (Khuyên dùng)
Yêu cầu cài đặt sẵn [Docker Desktop](https://www.docker.com/).

```bash
docker compose up --build
```
- **Backend API:** `http://localhost:8080`
- **Frontend Web UI:** `http://localhost:3000`

---

### Cách 2: Khởi chạy Cục bộ từng dịch vụ

#### 1. Backend (Spring Boot)
Yêu cầu: JDK 21+

```bash
cd backend
# Cấu hình biến môi trường nếu cần (.env / application.properties)
./mvnw spring-boot:run
```
Backend lắng nghe tại cổng `8080`.

#### 2. Frontend (Next.js)
Yêu cầu: Node.js 20+

```bash
cd frontend
npm install
npm run dev
```
Frontend lắng nghe tại `http://localhost:3000` và trỏ API tới `http://localhost:8080`.

---

## 🌐 Lưu ý khi Deploy Production

- **Vercel (Frontend):** Khi import repo này vào Vercel, hãy vào **Project Settings > General** và đặt **Root Directory** là `frontend`.
- **Render / Railway / VPS (Backend):** Đặt Root Directory hoặc Docker Context trỏ vào thư mục `backend`.
