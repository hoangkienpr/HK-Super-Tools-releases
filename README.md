# HK Super Tools — All-in-One Android (Flutter + Kotlin)

> **All In One application** — hộp công cụ toàn diện cho Android. Hiện chỉ hỗ trợ **Android**.
> Các thư mục `ios/ linux/ macos/ windows/ web/` đã được xóa khỏi repo để giảm bảo trì.
> Muốn build đa nền tảng trở lại: `flutter create --platforms=ios,windows,web .`

<!-- SEO -->
**HK Super Tools** (tên package `supertools`) là ứng dụng All-in-One cho **Android**, tổng hợp
hàng chục tiện ích: **nén video, cắt video, đổi định dạng, tạo GIF, trình chiếu ảnh + nhạc, lồng nhạc,
tạo ringtone, phát ngược nhạc, chuyển đổi âm thanh**, chia sẻ file qua **WiFi Direct, FTP, HTTP, SSH, SMB,
DLNA, WebRTC, Mesh/P2P**, điều khiển **TV Remote, IR Remote, Bluetooth Remote**, công cụ **ADB, Fastboot, Odin, APK**,
**QR, NFC, OCR**, **YouTube Download**, **quản lý file, USB, ảnh, văn bản**, và nhiều hơn nữa.

English: a single **Flutter + native Kotlin** Android toolbox bundling media tools, networking servers,
device-control remotes, developer/system utilities, file management and creative apps into one app.

---

## Tổng quan (Overview)

| | |
|---|---|
| Tên app | **HK Super Tools** (`supertools`) |
| Nền tảng | **Android** (Flutter SDK ^3.12.2, Java 17, compileSdk 36) |
| Kiến trúc | Flutter (Dart) + native Kotlin qua `MethodChannel` |
| Media engine | Thuần **MediaCodec / MediaExtractor / MediaMuxer** (không ffmpeg) |
| Render | **GPU/EGL + OpenGL ES 2** (có fallback CPU) |
| Theme | Material 3, hỗ trợ sáng/tối |
| Quyền | Sideload (~56 quyền), không dành cho Play Store generic |
| Cập nhật | Sideload qua `version.json` (repo releases) |

---

## Tính năng (Features)

### 1. Media Tools — Xử lý ảnh, nhạc, video
- **Nén video** theo preset độ phân giải/bitrate; **cắt** theo khoảng thời gian chính xác.
- **Đổi định dạng** container (MP4/3GP/WebM), **đổi tốc độ**, **xoay** 0/90/180/270°, **lật ngang (mirror)**.
- **Trình chiếu ảnh + nhạc → video**: nhiều ảnh, Ken Burns, fade in/out, FPS tùy chọn, tỉ lệ khung
  (Gốc/9:16/1:1/16:9/3:4), chế độ **vừa khung** hoặc **đầy khung (crop)**, watermark (vị trí/độ scale/độ mờ),
  **overlay tên bài hát + logo studio**, hiệu ứng phủ (mưa, tuyết, sao, cánh hoa, lấp lánh).
- **Lồng nhạc** vào video: chọn bài, canh thời điểm bắt đầu/kết thúc, **fade âm thanh**, lặp/cắt theo độ dài.
- **Ghép nhiều video** thành một file.
- **Nhạc → Visualizer / Bìa đĩa**: theme hiệu ứng (still, vinyl, lofi_rain, heartbeat, cassette, spectrum,
  waveform, cyberpunk, halo), phông chữ, viền chữ, zoom nền, bass boost, volume.
- **Tạo GIF** từ video (chọn đoạn, kích thước 240p–720p).
- **Chuông nhạc** (ringtone/báo thức/thông báo) với chọn khoảng bằng thanh trượt.
- **Tách audio** từ video (.m4a), **chuyển đổi âm thanh** (m4a/mp3/wav/aac/ogg), **đổi âm lượng**.
- **Phát ngược nhạc** — đảo ngược toàn bộ bài (dạng .m4a).
- **Bộ lọc** cho ảnh/video.

### 2. Mạng & Chia sẻ (Networking)
- **Mesh / P2P** chia sẻ file trong mạng LAN.
- **SMB client** kết nối NAS; **FTP server** + FTP client; **HTTP server** + HTTP client.
- **SSH tunnel**; **WebDAV** server.
- **WiFi Direct** truyền file; **Wi-Fi heatmap** và **Wi-Fi passwords** (xem mật khẩu đã lưu).
- **DLNA**: Media Cast (sender) + DLNA Receiver; **WebRTC** phát màn hình/âm thanh LAN.
- **Network Tools** (ping, port, thông tin mạng…).
- **PC link**, **screen cast** qua foreground service.

### 3. Hệ thống & Nhà phát triển (System / Dev tools)
- **ADB / USB console**: shell, macro, touchpad, điều khiển, sửa chữa, freezer, fastboot.
- **Fastboot tool**, **Odin tool** (flash firmware Samsung).
- **APK Pro**: quản lý/backup APK, **APK analyzer**, **APK diff**, backup APK của chính app.
- **Root bypass**, **Shizuku**, **secret menu**, **khoá máy từ xa** (anti-theft qua SMS/webhook).
- **Quyền ứng dụng** (kiểm tra/cấp quyền hệ thống), **Thông tin thiết bị**, **Hardware diagnostics**, **Pro sensor kit**.
- **Recycle bin** (thùng rác), **duplicate file scanner**, **similar photo scanner**, **file integrity**.
- **System Lab**, **Tech console**, **Decompiler**, **Hex editor**, **Text editor**.

### 4. Điều khiển thiết bị (Remotes / IoT)
- **TV Remote** (Samsung/LG/Android TV, kể cả bàn phím, screenshot).
- **IR Remote** (kho mã IR), **Bluetooth HID Remote** (chuột/bàn phím), **Smart AC** (điều hòa thông minh).

### 5. Công cụ đa dạng (Utilities & Creativity)
- **QR Generator** + **QR Scanner**; **NFC Tools** (đọc/ghi thẻ).
- **Speech to text**, **String translator**, **OCR Edit**.
- **YouTube Download** + **YouTube Sniffer** (tìm/tải video, audio).
- **Image tool**, **Image metadata editor**, **Image viewer**, **Universal preview**, **Video library**.
- **Office viewer**, **HTML viewer**, **Web browser**, **Archive explorer**.
- **Call screen**, **Fake call** (AI), **Watch together** (đồng bộ xem), **Family hub / Party**, **Guitar**, **Piano**.
- **Bubble level**, **Color picker**, **Compass**, **Satellite/GPS**, **Fake GPS**.

### 6. Quản lý file & lưu trữ
- **File explorer** (hiện file ẩn, yêu thích, gần đây), **Transfer history**, **Cross clipboard**.
- **USB**: USB hub, USB device detail, USB camera, USB serial console, USB bootable creator.
- **Microcontroller flasher**, **thumbnail service**, **zip service**, **temporary cleanup**.

### 7. Trải nghiệm (UX)
- Dashboard **tìm kiếm** (hỗ trợ tiếng Việt có/không dấu), **Yêu thích**, **Thư mục/File gần đây**.
- **Cập nhật sideload** qua `version.json` + chuông thông báo; **Onboarding** hướng dẫn; **User guide**.
- **Bong bóng nổi** (overlay), **Thùng rác** (xóa có khôi phục), **Tăng tốc tìm kiếm** (indexing).

---

## Yêu cầu (Requirements)
- Flutter SDK ^3.12.2, Java 17, Android compileSdk 36.
- `flutter pub get`

## Chạy / Build
```bash
flutter analyze --no-pub --no-fatal-infos --fatal-warnings
flutter test
flutter run
flutter build apk --release                       # abiFilters bỏ x86_64 -> chỉ arm64-v8a + armeabi-v7a
flutter build apk --release --split-per-abi --target-platform=android-arm,android-arm64
```

## Signing release
`android/key.properties` + `*.jks` **KHÔNG commit** (đã gitignore).
```bash
# copy mẫu rồi tạo keystore
copy android\key.properties.example android\key.properties
keytool -genkey -v -keystore supertools-release.jks -alias supertools -keyalg RSA -keysize 2048 -validity 10000
# không có key.properties -> build release dùng debug key (chỉ dev/test)
```

## Quyền (runtime)
App chỉ xin `notification` khi khởi động. Các quyền camera/mic/location/storage/bluetooth do từng màn hình
xin tại chỗ; tổng hợp ở **AppPermissionsScreen**. Manifest ~56 quyền (SMS, CallLog, MANAGE_EXTERNAL_STORAGE,
QUERY_ALL_PACKAGES…) — xác định phân phối **sideload/doanh nghiệp**, không phải Play Store generic.

## Cấu trúc (Structure)
- `lib/screens/` ~85 màn hình, `lib/services/` ~81 service, `lib/widgets/`
- `android/app/src/main/kotlin/com/hk/supertools/` — bridge native
- `vendor/` fork: `dartssh2`, `flutter_overlay_window` (path dependency)
- `assets/web_ui/` — Web UI nội bộ

## Git
- Branch chính: `master`
- Quy ước commit: `feat|fix|chore|refactor: ...`
- Repo nguồn: `hoangkienpr/HK-Super-Tools` · Repo releases: `hoangkienpr/HK-Super-Tools-releases`

## Lưu ý phân phối (Disclaimer)
Ứng dụng dành cho người dùng nâng cao / sideload. Nhiều tính năng yêu cầu quyền hệ thống đặc biệt
(MANAGE_EXTERNAL_STORAGE, ADB, root) và không tuân thủ chính sách Play Store thông thường.
