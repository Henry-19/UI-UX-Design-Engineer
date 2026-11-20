# UI/UX Design Engineer Skill (Elite Edition)

Một bộ kỹ năng (Agent Skill) toàn diện dành cho các AI Coding Agent (Antigravity, Claude Code, Cursor, Copilot, Windsurf) giúp nâng tầm trải nghiệm người dùng, triệt tiêu hoàn toàn mã giao diện rập khuôn ("AI Slop"), và tự động hóa quy chuẩn Design System chuẩn công nghiệp.

---

## 1. Nguồn Gốc & Phân Tích Tổng Hợp Từ Các Repo Nổi Tiếng

Skill này được đúc kết từ việc phân tích chuyên sâu các repository về UI/UX agent skill hàng đầu trên GitHub:

| Repository / Nguồn | Điểm Mạnh | Điểm Yếu / Thiếu Sót | Đóng Góp Vào Skill Này |
|---|---|---|---|
| **`anthropics/skills`** (`frontend-design`) | • Tư duy "Anti-AI-Slop" xuất sắc<br>• Ép agent đóng vai Design Director<br>• Tránh bảng màu gradient pastel rập khuôn | • Mang tính định tính, thiếu hệ thống token toán học<br>• Thiếu chỉ dẫn a11y WCAG cụ thể<br>• Chưa có quy chuẩn 5 trạng thái màn hình | Kế thừa triết lý **Bespoke Design Persona** và quy tắc thanh trừng các cliché AI (xem `references/anti-slop-guidelines.md`). |
| **`nextlevelbuilder/ui-ux-pro-max-skill`** | • Cơ sở dữ liệu phong phú về bảng màu và font pairings<br>• Phủ rộng nhiều stack (React, Vue, SwiftUI) | • Quá cồng kềnh, tiêu tốn nhiều context token<br>• Thiếu xử lý micro-interactions & physics<br>• Phụ thuộc vào file tra cứu lớn | Chắt lọc các **Color Harmony Matrix** và **Typography Scales** cốt lõi, tối ưu gọn gàng cho context window. |
| **`wshobson/agents`** (`design-system-patterns`) | • Kiến trúc Design Token 3 tầng rất chặt chẽ (Primitive, Semantic, Component)<br>• Hỗ trợ CSS custom properties | • Thiên nặng về technical CSS, thiếu góc nhìn UX<br>• Chưa chú trọng luồng nhận thức người dùng (Cognitive Load) | Kế thừa chuẩn **3-Tier Token Architecture** và quy tắc phối màu **60-30-10**. |
| **`uxuiprinciples/agent-skills`** | • Checklist kiểm định giao diện rất bài bản | • Chỉ đóng vai trò hậu kiểm (post-flight audit), thiếu hướng dẫn kiến tạo từ đầu | Tích hợp thành bộ **Pre-flight Design Audit Checklist** (15 tiêu chí). |

---

## 2. Cấu Trúc Thư Mục Skill

```
D:\SkillAgent\UI-UX-Design-Engineer\
├── SKILL.md                                 # Tệp skill chính cho AI Agent
├── README.md                                # Tài liệu hướng dẫn & phân tích
├── references/
│   ├── anti-slop-guidelines.md              # Quy chuẩn loại bỏ AI cliché & định hình phong cách
│   ├── design-tokens-and-color.md           # Hệ thống Token 3 tầng, bảng màu & công thức WCAG
│   ├── typography-and-spacing.md            # Thước đo tỷ lệ font 1.200 & lưới không gian 8pt/4pt
│   └── interaction-and-states.md            # 5 trạng thái màn hình bắt buộc & chuyển động spring
└── checklists/
    └── preflight-design-audit.md            # Bảng kiểm tra 15 bước trước khi render giao diện
```

---

## 3. Cách Cài Đặt & Sử Dụng

### Dành cho Google Antigravity / Claude Code
Sao chép thư mục hoặc chỉ định đường dẫn vào cấu hình skill của dự án:
```bash
# Ví dụ copy vào thư mục skills của dự án
cp -r D:\SkillAgent\UI-UX-Design-Engineer .github/skills/ui-ux-design-engineer
# hoặc đưa vào thư mục .claude/skills
```

### Dành cho Cursor / Windsurf
Thêm vào file `.cursorrules` hoặc `.windsurfrules`:
```markdown
Always adhere to the UI/UX Design Engineer Skill located at D:\SkillAgent\UI-UX-Design-Engineer\SKILL.md.
Never output generic AI templates or low-contrast text. Enforce 5 screen states and WCAG AA compliance.
```

---

## 4. Các Nguyên Tắc Vàng (Core Invariants)

1. **Anti-Slop First:** Tuyệt đối không dùng gradient hero lặp lại, không bo tròn card vô tội vạ, không dùng chữ xám mờ trên nền trắng.
2. **5 Screen States:** Mọi view/component luôn phải có thiết kế cho: *Ideal (Dữ liệu đầy đủ), Loading (Skeleton khớp hình học), Empty (Khuyến khích hành động), Error (Thân thiện + nút Thử lại), Degraded (Lỗi cục bộ không chết toàn trang).*
3. **WCAG 2.1 AA:** Độ tương phản chữ tối thiểu 4.5:1. Kích thước vùng bấm tối thiểu 44x44px. Hỗ trợ đầy đủ phím Tab và `:focus-visible`.
4. **Motion Ergonomics:** Luôn hỗ trợ `@media (prefers-reduced-motion: reduce)`.
