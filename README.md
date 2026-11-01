# 🪷 Chùa Linh Ứng Online — TikTok Live RPC (9:16 Interactive Buddhist Sanctuary)

Hệ thống phát trực tiếp tương tác tâm linh (**Interactive TikTok Live Stream & JSON-RPC 2.0**) chuẩn khung hình dọc **9:16 (`1080×1920`)** dành cho **OBS Studio / TikTok Live Studio**, chạy mượt mà trên cả **Node.js** lẫn **Bun.js**, tích hợp mô hình AI giọng đọc tiếng Việt **ZeroTTS (Giọng Mai Chi 48kHz)** và nhạc thiền thanh tịnh (`music2.mp3`) có cơ chế tự động giảm âm lượng thông minh (Auto-Ducking).

---

## ✨ Tính Năng Nổi Bật

* 🔥 **Thắp Hương & Đảnh Lễ Tam Bái (8-Frame Sprite)**: Người xem bình luận `thắp hương` hoặc tặng hoa, nhân vật Phật tử mặc áo lam sẽ bước đi từng bước dọc thảm đỏ hoa sen lên trước Lư Hương Đỉnh Đồng, quỳ gối đảnh lễ 3 lạy trước Tam Bảo.
* 🏮 **Thả Đèn Hoa Đăng / Sớ Cầu Nguyện**: Lời cầu chúc bình an bay lên thành Đèn Hoa Đăng tỏa sáng giữa chánh điện kèm giọng đọc AI đọc lời cầu nguyện của thí chủ.
* 🎋 **Gieo Quẻ / Xin Xăm Linh Ứng**: Lắc ống xăm vật lý và mở Tờ Giải Quẻ (Thượng Thượng Cát, Đại Cát, Thượng Cát...) đúng thời điểm giọng đọc Mai Chi giải quẻ.
* 🪵 **Gõ Mõ & 🔔 Thỉnh Đại Hồng Chung**: Thả tim tự động gõ mõ tích điểm Công Đức; chia sẻ/follow thỉnh chuông đồng ngân vang kèm sóng âm lan tỏa và hiệu ứng vái lạy đồng loạt của 40+ Phật tử trong hội chúng.
* 🎵 **Nhạc Nền Thanh Tịnh (`music2.mp3`) & Auto-Ducking**: Nhạc nền tự động hạ nhỏ âm lượng khi có lời khấn hoặc đọc quẻ, sau đó tự phục hồi mượt mà.
* 🎙️ **Giọng Đọc AI Mai Chi Chuẩn 48kHz**: Sử dụng ZeroTTS đọc tên thí chủ, lời khấn và giải quẻ tự nhiên, không dùng giọng robot máy móc.
* 📜 **Bảng Vàng Công Đức (`TẤM LÒNG THÀNH` & 6 Đệm Quỳ VIP)**: Tự động ghi nhận và vinh danh Top thí chủ có điểm công đức cao nhất trên 6 đệm quỳ gấm đỏ.

---

## 📸 Giao Diện Trực Quan

| Màn hình Live 9:16 OBS (`?obs=1`) | Bảng Điều Khiển Admin & RPC (`/admin`) |
| :---: | :---: |
| ![OBS 9:16 Mode](docs/demo/demo-obs-9x16.png) | ![Admin JSON-RPC Panel](docs/demo/demo-admin-panel.png) |

---

## 🛠️ Yêu Cầu Hệ Thống (Prerequisites)

1. **Node.js** (Khuyên dùng bản `>= 18.x` hoặc `20.x` / `24.x`) hoặc **Bun.js** (`>= 1.1`).
2. **Python 3.10** hoặc **3.11** (Để chạy mô hình AI giọng đọc Mai Chi).  
   *⚠️ Khi cài Python trên Windows, nhớ tích vào ô vuông: **☑️ Add python.exe to PATH**.*

---

## 🚀 Hướng Dẫn Cài Đặt Chi Tiết Cho Người Mới

### Bước 1: Tải mã nguồn về máy
```bash
git clone https://github.com/your-username/tiktok-live-temple-rpc.git
cd tiktok-live-temple-rpc
```

### Bước 2: Cài đặt thư viện Node.js
```bash
npm install
# Hoặc nếu dùng Bun:
bun install
```

### Bước 3: Cài đặt thư viện AI cho giọng Mai Chi
Mở Terminal / PowerShell và chạy lệnh sau:
```bash
pip install zerotts numpy
```
*(Lần đầu tiên khởi động, hệ thống sẽ tự động tải mô hình AI ZeroTTS khoảng 1 GB từ Hugging Face về máy và lưu vào bộ nhớ cache).*

---

## ▶️ Cách Khởi Động Dự Án

### 1. Chạy với cổng mặc định (`3000`):
* **Bằng Node.js:**
  ```powershell
  node server.js
  ```
* **Bằng Bun:**
  ```powershell
  bun run server.js
  ```

### 2. Chạy với cổng tùy chọn (Ví dụ cổng `3001` hoặc `8080`):
* **Trên Windows PowerShell:**
  ```powershell
  $env:PORT=3001; node server.js
  ```
* **Trên CMD:**
  ```cmd
  set PORT=3001 && node server.js
  ```
* **Trên macOS / Linux:**
  ```bash
  PORT=3001 node server.js
  ```

### 3. Tùy chọn đặt sẵn tài khoản TikTok Live khi bật server:
```powershell
$env:TIKTOK_USER="ntwzai200"; node server.js
```

---

## 🌐 Các Đường Dẫn Sau Khi Chạy

| Trang | URL | Mục đích sử dụng |
| :--- | :--- | :--- |
| **Màn hình Live 9:16** | `http://localhost:3000` | Màn hình tương tác chính kèm bảng điều khiển nhanh bên phải |
| **Màn hình OBS 9:16 (Sạch)** | `http://localhost:3000/?obs=1` | Màn hình không chứa nút bấm, dành riêng để nhúng vào OBS Studio |
| **Bảng Điều Khiển Admin** | `http://localhost:3000/admin` | Quản lý kết nối TikTok, kích hoạt nghi thức, nghe thử và xoá cache giọng đọc |
| **Cổng JSON-RPC 2.0** | `http://localhost:3000/rpc` | Endpoint nhận lệnh từ TikFinity, Streamer.bot hoặc cURL |

---

## 📺 Cấu Hình Đưa Lên OBS Studio (Livestream TikTok 9:16)

1. Mở **OBS Studio**, tại khung **Sources (Nguồn)** bấm dấu **`+`** ➔ Chọn **Browser (Trình duyệt)**.
2. Đặt tên (Ví dụ: `Chùa Online 9:16`).
3. Cấu hình các thông số:
   * **URL:** `http://localhost:3000/?obs=1`
   * **Width (Chiều rộng):** `1080`
   * **Height (Chiều cao):** `1920`
   * ☑️ Tích chọn: **Control audio via OBS** (Điều khiển âm thanh qua OBS).
4. Bấm **OK**. Màn hình Chánh Điện sẽ hiển thị trọn vẹn khung hình dọc 9:16 sắc nét.

---

## 🎮 Bảng Quy Tắc Tự Động Nhận Diện Tương Tác TikTok Live

| Sự kiện trên TikTok Live | Từ khóa nhận diện | Hành động trên Chánh Điện | Công Đức |
| :--- | :--- | :--- | :---: |
| **Thả tim (Like)** | Thả tim màn hình | Gõ mõ nhịp nhàng + Đạo tràng phật tử vái lạy | `+1` / tim |
| **Follow / Share** | Bấm Theo dõi hoặc Chia sẻ | Thỉnh Đại Hồng Chung ngân vang + Sóng âm vàng lan tỏa | `+10` |
| **Bình luận Thắp hương** | `thắp hương`, `dâng hương`, `bái phật`, `lạy phật` | Bước lên đảnh lễ 3 lạy trước Lư Hương + Giọng Mai Chi cảm tạ | `+15` |
| **Bình luận Cầu nguyện** | `cầu ...`, `nguyện ...`, `nam mô`, `bình an`, `tài lộc` | Thả Đèn Hoa Đăng bay lên trời mang theo lời khấn + Đọc lời cầu nguyện | `+10` |
| **Bình luận Xin xăm** | `xin xăm`, `gieo quẻ`, `rút quẻ`, `quẻ` | Lắc ống xăm tre + Mở tờ Giải Quẻ đồng bộ theo giọng đọc Mai Chi | `+10` |
| **Tặng quà nhỏ (1–4 xu)** | Hoa hồng, Heart Me... | Bước lên dâng Đài Hoa Sen Vàng + Thắp 3 nén hương thơm | `+20` / xu |
| **Tặng quà vừa (5–99 xu)** | Mâm ngũ quả, Đèn lưu ly... | Dâng Mâm Ngũ Quả Cát Tường + Thỉnh Đại Hồng Chung chúc phúc | `+30` / xu |
| **Tặng quà lớn (≥ 100 xu)** | Rồng vàng, Quà VIP... | **Đại Lễ Kim Long Chầu Phật**: Mưa hoa sen rơi, hào quang phát sáng vạn trượng | `+50` / xu |

---

## 🗑️ Cách Xoá Cache Giọng Nói (WAV) Khi Cần

* **Cách 1 (Nhanh nhất):** Mở trang Admin `http://localhost:3000/admin` ➔ Bấm nút **`🗑️ Xoá Cache TTS`**.
* **Cách 2 (PowerShell):**
  ```powershell
  Remove-Item -Path "data\tts-cache\*" -Force
  ```
* **Cách 3 (CMD):**
  ```cmd
  del /q /s "data\tts-cache\*"
  ```

---

## 🔌 Tích Hợp JSON-RPC 2.0 (TikFinity / Streamer.bot / cURL)

Bạn có thể gửi yêu cầu HTTP POST tới `http://localhost:3000/rpc`:

```bash
# Thắp 3 nén hương:
curl -X POST http://localhost:3000/rpc \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc": "2.0",
    "id": 1,
    "method": "temple.burnIncense",
    "params": {
      "user": "Thí Chủ Minh Tâm",
      "count": 3,
      "wish": "Cầu gia đạo bình an, vạn sự cát tường"
    }
  }'

# Xin xăm / Gieo quẻ:
curl -X POST http://localhost:3000/rpc \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc": "2.0",
    "id": 2,
    "method": "temple.drawFortune",
    "params": {
      "user": "Thí Chủ Minh Tâm",
      "topic": "Cầu tài lộc đầu năm"
    }
  }'
```

---

## 📁 Cấu Trúc Mã Nguồn

```text
├── server.js               # Máy chủ Node.js/Bun, WebSocket JSON-RPC & TikTok Live Connector
├── tts_worker.py           # Daemon Python ZeroTTS AI (Giọng Mai Chi 48kHz, xử lý I/O unbuffered)
├── data/
│   ├── merit-state.json    # Lưu trữ điểm Công Đức và Bảng Vàng của thí chủ thật
│   └── tts-cache/          # Bộ đệm file âm thanh .WAV đã tạo (tránh tổng hợp lại)
├── public/
│   ├── index.html          # Màn hình Chánh Điện 9:16 Đức Phật A Di Đà
│   ├── admin.html          # Bảng điều khiển Admin & kiểm thử RPC
│   ├── css/live.css        # Stylesheet & Animation 2.5D
│   ├── js/
│   │   ├── live.js         # Quản lý hoạt họa đảnh lễ Tam Bái, 40 ghế Đạo Tràng & WebSocket
│   │   ├── audio.js        # Nhạc nền music2.mp3 auto-ducking, Pháp khí chuông mõ Web Audio
│   │   └── particles.js    # Canvas Particles 30 FPS nhẹ CPU (khói nhang, hoa sen, sóng âm)
│   └── assets/             # Hình ảnh Chánh Điện 8K, 8 pose Phật tử và nhạc nền music2.mp3
```

---

## 📜 Giấy Phép (License)
Dự án được phân phối phi thương mại phục vụ mục đích tâm linh, thiện nguyện và giải trí tương tác trực tuyến. Chúc quý thí chủ vạn sự hanh thông, công đức vô lượng! 🙏
