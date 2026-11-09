# Doc → HTML · Công cụ tạo bài Reading tương tác (Ms Yen English)

Website tĩnh 100%: toàn bộ việc đọc file .docx và tạo file HTML chạy ngay trong trình duyệt của người dùng.
Không có server, không có database, file Word không được tải lên máy chủ nào cả.

## Cách deploy lên Vercel (miễn phí)

### Cách A — qua GitHub (ổn định, cập nhật dễ)
1. Tạo 1 repo mới trên GitHub (ví dụ tên `doc-to-reading-html`), chọn Public.
2. Upload toàn bộ file trong thư mục này lên repo (`index.html`, `vercel.json`, thư mục `mau/`, `README.md`) — trên trang repo: **Add file → Upload files**, kéo thả vào, bấm **Commit changes**.
3. Vào https://vercel.com → **Sign Up / Log In** bằng tài khoản GitHub → **Add New… → Project**.
4. Chọn repo vừa tạo → **Import**. Ở phần cấu hình giữ nguyên mặc định (Framework Preset: **Other**, không cần Build Command, không cần Output Directory) → **Deploy**.
5. Đợi khoảng 30 giây → Vercel cho 1 đường link dạng `https://doc-to-reading-html-xxx.vercel.app`. Mở link đó là dùng được ngay: thả file .docx vào → xem trước → tải file HTML.

### Cách B — bằng Vercel CLI trên máy tính (không cần GitHub)
1. Cài Node.js (https://nodejs.org) nếu chưa có.
2. Mở Terminal/CMD trong thư mục này, chạy: `npm i -g vercel`
3. Chạy: `vercel deploy --prod` → đăng nhập theo hướng dẫn, trả lời các câu hỏi bằng Enter (mặc định), ở câu "Want to modify these settings?" chọn **N**.
4. CLI in ra đường link Production — đó là website của bạn.

## Cách nhanh hơn nữa — Netlify Drop (không cần tài khoản Git, ~1 phút)
1. Vào https://app.netlify.com/drop
2. Kéo thả **file zip** `doc-to-html-website.zip` (hoặc cả thư mục này) vào trang.
3. Netlify cho ngay 1 link `https://xxx.netlify.app` dùng được luôn. Đăng ký tài khoản miễn phí để giữ link cố định và đổi tên miền con.

## Cloudflare Pages (miễn phí, Direct Upload)
1. Vào https://dash.cloudflare.com → **Workers & Pages → Create → Pages → Upload assets**.
2. Đặt tên project, tải lên file zip, bấm **Deploy site** → nhận link `https://ten-project.pages.dev`.

## Cập nhật website sau này
- Vercel/GitHub: upload lại file `index.html` mới lên repo (ghi đè) — Vercel tự deploy lại trong ~30 giây.
- Netlify: vào **Deploys → Drag and drop** thả lại file zip mới.

## Cấu trúc thư mục
- `index.html` — toàn bộ công cụ (chỉ phụ thuộc thư viện mammoth.js qua CDN để đọc .docx).
- `mau/` — file Word mẫu + HTML demo, website phục vụ luôn để người dùng tải về.
- `vercel.json` — cấu hình tối thiểu cho Vercel (có thể xoá, không bắt buộc).
