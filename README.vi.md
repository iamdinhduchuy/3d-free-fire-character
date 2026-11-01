# Character 3D — Mô hình Nhân vật 3D Mặc định (OB55 PC)

<p align="center">
  <a href="./README.md"><strong>English</strong></a> · <strong>Tiếng Việt</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Characters-74-blue" alt="Characters: 74" />
  <img src="https://img.shields.io/badge/GLB_Models-148-success" alt="GLB Models: 148" />
  <img src="https://img.shields.io/badge/Format-glTF_2.0_(.glb)-orange" alt="Format: glTF 2.0" />
  <img src="https://img.shields.io/badge/Validation-0_Errors_%7C_0_Warnings-brightgreen" alt="Validation: 0 Errors | 0 Warnings" />
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" /></a>
</p>

---

## Tổng quan

Kho lưu trữ này bao gồm **74 thư mục nhân vật 3D mặc định** (tổng cộng **148 tệp `.glb`**, bao gồm cả **6 phiên bản Thức Tỉnh / Awakening**) được trích xuất và ghép hoàn chỉnh từ phiên bản **OB55 PC**.

Mỗi tệp `.glb` là một model glTF 2.0 độc lập, hoàn chỉnh với:
- **Bộ xương (Skeleton / Rig) đầy đủ** kèm theo trọng số biến dạng lưới (skin weights)
- **Texture được nhúng trực tiếp** và vật liệu glTF mô phỏng gần đúng shader trong game
- **Hai biến thể cho mỗi nhân vật**:
  - `Lobby`: Bản chi tiết cao dùng ở sảnh chờ và màn hình trưng bày nhân vật
  - `InGame`: Bản tối ưu hóa hiệu năng dùng trong trận đấu
- **Ảnh xem trước `2048 × 2048`** (`preview.png`) được kết xuất trực tiếp từ lưới 3D và texture gốc của tệp GLB
- **Kiểm định chất lượng glTF 2.0 tuyệt đối**: Toàn bộ 148 model đều đạt **0 lỗi (errors), 0 cảnh báo (warnings)** và đã được đối chiếu mã băm SHA-256

## Cấu trúc thư mục

Mỗi nhân vật được đặt trong một thư mục riêng theo tên nhân vật (ví dụ: `Kelly/`, `Alok/`, `Hayato_Awakening/`):

```text
character-3d/
├── Kelly/
│   ├── Kelly_Default_Lobby.glb                  # Model 3D bản Lobby (chi tiết cao)
│   ├── Kelly_Default_InGame.glb                 # Model 3D bản InGame (tối ưu trong trận)
│   ├── Kelly_Default_Lobby.json                 # Metadata xuất file & thông tin recipe (Lobby)
│   ├── Kelly_Default_InGame.json                # Metadata xuất file & thông tin recipe (InGame)
│   ├── Kelly_Default_Lobby.glb.validation.json  # Báo cáo kiểm tra chuẩn glTF (Lobby)
│   ├── Kelly_Default_InGame.glb.validation.json # Báo cáo kiểm tra chuẩn glTF (InGame)
│   └── preview.png                              # Ảnh dựng xem trước độ phân giải 2048 × 2048
├── ... (74 thư mục nhân vật)
├── characters.tsv                               # Bảng tra cứu tên, Avatar ID, đường dẫn & SHA-256
├── coverage.json                                # Thống kê độ phủ dữ liệu & kết quả kiểm tra
├── errors.json                                  # Danh sách các mục thiếu dữ liệu gốc
├── manifest.json                                # Manifest tổng hợp đường dẫn, cấu hình & SHA-256
├── organization.json                            # Số lượng tệp và trạng thái đối chiếu toàn vẹn
├── roster.json                                  # Dữ liệu cấu hình danh sách nhân vật gốc
├── README.md                                    # Tài liệu tiếng Anh
├── README.vi.md                                 # Tài liệu tiếng Việt
└── LICENSE                                      # Giấy phép MIT
```

## Hướng dẫn sử dụng

1. **Trong Blender**:
   - Mở Blender (khuyến nghị bản 3.0 trở lên), chọn **File → Import → glTF 2.0 (.glb/.gltf)**.
   - Chọn tệp `<Tên_Nhân_Vật>_Default_Lobby.glb` (nếu cần độ chi tiết cao để render/làm phim) hoặc `<Tên_Nhân_Vật>_Default_InGame.glb` (nếu cần model nhẹ).
   - Chuyển chế độ hiển thị Viewport sang **Material Preview** hoặc **Rendered** để xem đầy đủ texture.
2. **Trong Game Engine & Web (Unity / Unreal Engine / Godot / Three.js)**:
   - Kéo thả trực tiếp tệp `.glb` vào project hoặc tải qua `GLTFLoader` trên nền tảng web.
3. **Lưu ý về Shader & Animation**:
   - Bộ xương và skin weights đã có sẵn để tạo dáng (pose) hoặc gắn chuyển động (retarget animation).
   - Các tệp `.glb` này **chưa bao gồm animation**.
   - Shader chuyên biệt của game được xấp xỉ bằng hệ thống material tiêu chuẩn của glTF 2.0.

## Phạm vi dữ liệu & Ghi chú phục dựng

| Chỉ số | Giá trị |
| :--- | :--- |
| **Tổng số mục trong Roster** | 76 |
| **Số nhân vật đã xuất** | 74 (gồm 6 bản Thức Tỉnh / Awakening) |
| **Ghép theo Recipe gốc** | 73 |
| **Phục dựng từ Asset gốc** | 1 (`CricketGuy`) |
| **Chưa thể xuất** | 2 (`MMAFighter`, `Researcher`) |
| **Tổng số tệp GLB** | 148 (`243.885.124` bytes / ~232,6 MB) |
| **Kết quả kiểm tra glTF** | 0 Lỗi, 0 Cảnh báo |

- **Nhân vật phục dựng (`CricketGuy`)**: Được phục dựng từ các asset gốc do thiếu recipe mặc định trong bảng dữ liệu; bằng chứng và dữ liệu ánh xạ phục dựng nằm tại [`CricketGuy/cricketguy_recipe_recovery.json`](./CricketGuy/cricketguy_recipe_recovery.json) và [`CricketGuy/cricketguy_recovery_evidence.json`](./CricketGuy/cricketguy_recovery_evidence.json).
- **Mục thiếu dữ liệu (`Researcher`, `MMAFighter`)**: Chưa thể xuất do thiếu dữ liệu recipe trong bản build nguồn, chi tiết được ghi nhận tại [`errors.json`](./errors.json).

## Danh sách các tệp Metadata ở thư mục gốc

- [`characters.tsv`](./characters.tsv): Bảng tra cứu nhanh tên nhân vật, Avatar ID, biến thể (`Lobby`/`InGame`), trạng thái, đường dẫn tệp và mã SHA-256.
- [`manifest.json`](./manifest.json): Dữ liệu chi tiết theo từng thư mục nhân vật, cấu hình gốc, báo cáo kiểm định và SHA-256.
- [`coverage.json`](./coverage.json) & [`organization.json`](./organization.json): Thống kê số lượng model, dung lượng và kết quả kiểm tra tính toàn vẹn.
- [`roster.json`](./roster.json): Dữ liệu cấu hình danh sách nhân vật trích xuất từ game.
- [`errors.json`](./errors.json): Ghi nhận các mục không thể xuất do thiếu dữ liệu nguồn.

## Giấy phép & Tuyên bố miễn trừ trách nhiệm

- Cấu trúc kho lưu trữ, dữ liệu manifest, kịch bản tổ chức và tài liệu hướng dẫn được phát hành theo [Giấy phép MIT (MIT License)](./LICENSE).
- **Tuyên bố miễn trừ trách nhiệm**: Toàn bộ mô hình 3D, texture và tên nhân vật thuộc quyền sở hữu trí tuệ của chủ sở hữu bản quyền tương ứng (Garena). Kho dữ liệu này được chia sẻ nhằm mục đích học tập, nghiên cứu kỹ thuật 3D và tham khảo fan-art.
