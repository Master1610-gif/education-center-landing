# Plan — Landing Page Demo: Trung tâm giáo dục

## Intent

Demo landing page 1 trang cho trung tâm giáo dục, mục tiêu **không phải** hoàn thiện website mà chứng minh cho khách xem 4 thứ: **Visual** (cao cấp / hiện đại / thật), **Message** (nói đúng nhu cầu phụ huynh), **Structure** (section nối thành hành trình), **CTA** (đường dẫn tự nhiên tới tư vấn). Hành trình: **Hình dung → Nhận diện nhu cầu → Kiểm chứng → Hành động**.

Deliverable khi sang Design mode: **một file HTML** (`landing-page.html`), responsive desktop + mobile, animation nhẹ, không form/backend.

---

## 1. Đối tượng & thông điệp lõi

- **Đọc giả:** phụ huynh vừa vào trang lần đầu, đang so sánh trung tâm cho con.
- **Câu hỏi của họ theo thứ tự:** "Môi trường có tốt không?" → "Ở đây có lớp gì cho con tôi?" → "Họ nói có thật không?" → "Liên hệ thế nào?"
- **Thông điệp lõi:** Để con được học, thử và tự tin hơn. Giáo viên đồng hành, con chủ động khám phá.
- **Tone:** ấm, chắc, không PR rỗng — mỗi claim phải là thứ trung tâm thật sự có.

---

## 2. Page hierarchy (section chain)

| # | Section | Câu hỏi khách đang tự hỏi | Mức độ hoàn thiện |
|---|---------|---------------------------|-------------------|
| — | Header (sticky, trong suốt → đặc khi scroll) | Tôi đang ở đâu? | Hoàn chỉnh |
| 1 | Hero | "Con sẽ học ở đây như thế nào?" | Hoàn chỉnh nhất (40% effort) |
| 2 | Programs — 4 lớp | "Ở đây có lớp phù hợp với con không?" | Visual + copy cơ bản (25%) |
| 3 | Proof — Học thật, làm thật | "Những gì họ nói có thật không?" | Layout + ảnh (20%) |
| 4 | CTA — Tìm lớp cho bé | "Vậy mình tìm hiểu lớp cho bé." | Hoàn chỉnh (10%) |
| 5 | Footer | Liên hệ | Cơ bản (10% chia CTA/Footer/polish) |

Không thêm section giới thiệu/tầm nhìn — chuỗi trên đã là toàn bộ narrative.

---

## 3. Section spec

### Header
- Logo (tên trung tâm) trái · nav nhẹ (Các lớp · Học thật · Liên hệ) · CTA nhỏ "Tư vấn cho bé" phải.
- Desktop: trong suốt trên Hero, nền đặc sau khi scroll qua Hero. Mobile: logo + nút CTA, nav vào menu gọn (hoặc bỏ nav, chỉ giữ CTA — demo chấp nhận).

### 1. Hero — "Để con được học, thử và tự tin hơn."
- **Visual:** ảnh documentary full-screen, giáo viên + trẻ bên **phải**, negative space bên **trái** để đặt copy; nội thất premium, tranh trẻ vẽ trên tường. Không stock/AI-looking → ưu tiên ảnh thật của trung tâm.
- **Copy:**
  - H1: `Để con được học, thử và tự tin hơn.`
  - Support: `Giáo viên đồng hành, con chủ động khám phá.`
  - CTA: `[Tìm lớp cho bé →]` → anchor xuống #programs.
- **Animation (chuỗi duy nhất, không thêm):** image reveal → headline → supporting → CTA. Dùng CSS/GSAP one-shot on load; tôn trọng `prefers-reduced-motion`.
- **Layout:** text block ≤ ~52ch trên nền tối/overlay nhẹ để chữ đọc được trên ảnh; CTA ≥44px.

### 2. Programs — "Trung tâm có những gì phù hợp với con?"
- **Layout:** 4 card **không phải grid 2×2 đều nhau** — stagger/offset (card lùi/hở nhịp, ảnh cover khác tỉ lệ) để tránh nhàm chán; 2×2 skeleton chỉ là khung, xử lý lệch nhịp khi build. Mobile: stack 1 cột, giữ offset nhẹ.
- **Card mỗi cái:** tên lớp → 1 câu mô tả cực ngắn → ảnh nhỏ → link `Tìm hiểu →`.
- **4 nhóm (đúng dữ liệu khách cung cấp, không invent USP):**
  1. Lớp học vẽ
  2. Gia sư các cấp
  3. Tiền tiểu học & luyện chữ đẹp
  4. Tiếng Anh giao tiếp với người nước ngoài
- **Copy mô tả:** 1 câu ngắn mang tính mô tả chương trình, không thêm cam kết kết quả/điểm số/tỉ lệ. <!-- TODO: xác nhận câu mô tả từng lớp với khách -->

### 3. Proof — "Mỗi buổi học là một lần con được thực hành."
- **Layout:** 1 ảnh lớn (classroom thật) + 2–3 ảnh nhỏ (trẻ đang học / giáo viên tương tác / tranh trẻ vẽ / sản phẩm thực tế). Nhịp: ảnh lớn trên, dải ảnh nhỏ lệch dưới.
- **Copy:** headline trên + 2–3 proof point ngắn.
- **Proof points:** CHỈ dùng thứ trung tâm thật sự có. <!-- TODO: khách xác nhận — ví dụ: "Giáo viên theo sát" / "Hoạt động thực hành" / "Trao đổi với phụ huynh". Nếu chưa xác nhận → giữ placeholder có nhãn, KHÔNG claim -->

### 4. CTA — "Tìm lớp phù hợp cho bé"
- **Visual:** nền sáng, sạch hơn Hero (đảo sáng/tối so với Hero để đóng nhịp).
- **Copy:** H2 `Tìm lớp phù hợp cho bé` · support `Để được tư vấn chương trình phù hợp với độ tuổi và nhu cầu của con.` · CTA `[Tư vấn cho bé →]`.
- <!-- TODO: nếu trung tâm không có quy trình tư vấn như vậy → đổi copy theo thông tin khách xác nhận. CTA trỏ tới tel: hoặc Zalo (không có form/backend trong demo) -->

### 5. Footer — cơ bản
- Logo · địa chỉ · số điện thoại · Facebook/Zalo (nếu khách cung cấp) · danh sách 4 nhóm lớp (anchor về #programs) · 1 CTA liên hệ.
- <!-- TODO: cần khách cung cấp — logo, tên trung tâm, địa chỉ, SĐT, link FB/Zalo -->

---

## 4. Responsive

- **Desktop (≥1024):** Hero full-bleed 100vh (min-height an toàn), programs stagger 2 cột, proof mosaic.
- **Tablet (768–1023):** programs 2 cột đều (bớt offset), proof 1 ảnh lớn + dải 2 ảnh.
- **Mobile (<768):** **redesign, không siết desktop** — Hero stack (ảnh nửa trên / copy dưới hoặc overlay chữ lên ảnh có scrim), programs stack 1 cột, proof cuộn dọc ảnh, CTA full-width. Không horizontal scroll ở 360/390/430px. Touch target ≥44px.
- Type dùng `clamp()`; check ở 600/768/1024/1440/1920px.

---

## 5. Visual system (bound — không đổi khi build)

Direction: **human-approachable** (Airbnb/Duolingo — hợp education khi chưa có brand palette từ khách).

```css
:root {
  --bg:      oklch(98% 0.004 240);
  --surface: oklch(100% 0 0);
  --fg:      oklch(20% 0.02 240);
  --muted:   oklch(50% 0.018 240);
  --border:  oklch(90% 0.006 240);
  --accent:  oklch(56% 0.12 170);
  --font-display: 'Söhne', 'Avenir Next', -apple-system, BlinkMacSystemFont, system-ui, sans-serif;
  --font-body:    -apple-system, BlinkMacSystemFont, 'SF Pro Text', system-ui, sans-serif;
}
```

Posture: display sans tương phản weight mạnh; radius 12–18px; accent chính (teal) cho CTA, **một accent phụ/domain** tối đa cho nhãn chương trình; elevation nhẹ chỉ trên card tương tác; không gradient wash toàn trang; ảnh thật là texture chính.

<!-- TODO (option): nếu khách có brand spec / screenshot → thay palette này bằng giá trị thực từ brand-spec.md -->

---

## 6. Media & data needs

| Nhu cầu | Nguồn ưu tiên | Fallback |
|---|---|---|
| Hero: GV + trẻ, negative space trái | Ảnh thật của trung tâm (khách cung cấp) | Ảnh gen documentary 16:9 đúng brief, không stock-AI-cliché |
| 4 ảnh card chương trình | Ảnh chụp lớp thật / ảnh gen theo từng lớp | — |
| Proof: 1 large + 2–3 small | Ảnh thật: trẻ học, GV tương tác, tranh vẽ, sản phẩm | Ảnh gen classroom documentary |
| Logo, địa chỉ, SĐT, FB/Zalo | Khách cung cấp | <!-- TODO placeholder có nhãn --> |
| Tên câu mô tả 4 lớp, proof points | Khách xác nhận | Placeholder có nhãn, không claim |

---

## 7. Animation & tech scope

- Hero: đúng 1 chuỗi reveal (image → headline → support → CTA), CSS/GSAP one-shot. Không animation thêm cho section khác ngoài micro-hover/scroll-reveal rất nhẹ (optional, 5% polish).
- Không form, không backend, không CMS. Anchor scroll cho nav/CTA.
- File: `landing-page.html` standalone (inline CSS/JS), `data-od-id` cho các region/card/CTA.

---

## 8. Acceptance checks (P0)

- [ ] Hero có ảnh documentary, text bên trái, CTA scroll tới #programs.
- [ ] Đủ 4 section + header + footer, đúng thứ tự chain; không thêm section ngoài scope.
- [ ] 4 card đúng 4 nhóm lớp, không invent USP; mô tả ≤1 câu.
- [ ] Proof: 1 ảnh lớn + 2–3 ảnh nhỏ; mọi claim đều được khách xác nhận hoặc là placeholder có nhãn.
- [ ] CTA lặp ở Hero, cuối trang, footer; không có form.
- [ ] Không horizontal scroll ở 360/390/430px; không tràn/clip text ở 768/1024/1440/1920px.
- [ ] Chỉ 1 chuỗi animation Hero; tôn trọng `prefers-reduced-motion`.
- [ ] Palette bind đúng token human-approachable (hoặc brand spec nếu khách cung cấp).

---

## TODO / Open questions (cần khách trả lời trước khi build final)

1. **Brand:** có brand spec / tên trung tâm / logo chưa? (không có → dùng direction human-approachable ở trên)
2. **Ảnh thật:** khách có ảnh chụp tại trung tâm không? (Hero là tâm điểm "wow" — ảnh thật > ảnh gen)
3. **Contact:** địa chỉ, SĐT, Facebook/Zalo?
4. **Proof points:** 3 điểm nào khách xác nhận được? (GV theo sát / thực hành / trao đổi PH — hay khác)
5. **CTA đích:** "Tư vấn cho bé" trỏ tới đâu khi không có form — gọi SĐT, Zalo, hay Messenger?

Câu trả lời mặc định nếu khách không phản hồi trong lúc demo: dùng direction đã bind, ảnh gen documentary, placeholder có nhãn cho contact/proof, CTA trỏ `tel:`.

---

## Next step

1. Xem lại file này — sửa trực tiếp các mục cần đổi (copy, scope, direction) hoặc trả lời 5 open question ở trên.
2. Khi duyệt xong, chuyển sang Design mode với câu đại diện: **"Dùng landing-page-plan.md để build landing-page.html"**.
3. Agent build sẽ đọc plan này như source of truth, giữ nguyên palette/token và chain 5 phần đã chốt.
