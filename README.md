# Đồ án thạc sĩ — EarlyRisk-MOOC (LaTeX, chuẩn QĐ 199/QĐ-KHTN)

## Cách biên dịch trên TeXstudio

1. Mở `main.tex` trong TeXstudio.
2. Đặt trình biên dịch mặc định là **XeLaTeX**:
   `Options → Configure TeXstudio → Build → Default Compiler → XeLaTeX`
3. Đặt chuỗi build đầy đủ (để bibliography hiện ra):
   `Tools → Commands`, hoặc dùng phím tắt lần lượt:
   - **XeLaTeX** (F6 nếu đã đặt) → **BibTeX** → **XeLaTeX** → **XeLaTeX**
   - Hoặc đơn giản: bấm **Build & View (F5)** hai lần, xen giữa một lần **BibTeX (F8)**.

Trình tự chuẩn: `xelatex → bibtex → xelatex → xelatex`

## Font

File dùng **Times New Roman** (`\setmainfont{Times New Roman}` trong `main.tex`).
Trên Windows/macOS thường có sẵn nên chạy thẳng. Nếu báo lỗi "font not found",
mở `main.tex` và bỏ dấu `%` ở một trong hai dòng fallback:
```
% \setmainfont{TeX Gyre Termes}     % gần giống Times, có sẵn TeX Live
% \setmainfont{Liberation Serif}    % metric-compatible với Times
```

## Bibliography

Dùng `\bibliographystyle{IEEEtran}` (phong cách IEEE, phù hợp khối Khoa học Tự
nhiên & Kỹ thuật như QĐ 199 gợi ý). `IEEEtran.bst` có sẵn trong TeX Live đầy đủ
(MiKTeX/TeX Live). Nếu thiếu, cài gói `IEEEtran` qua trình quản lý gói, hoặc tạm
đổi sang `\bibliographystyle{unsrt}`.

## Thông tin cần điền

Mở `frontmatter/00-thongtin.tex` và sửa các `\newcommand`:
tên học viên, tên đề tài, ngành, mã số ngành, khóa, người hướng dẫn, năm bảo vệ.
Toàn bộ trang bìa và các trang thông tin sẽ tự cập nhật theo.

## Cấu trúc thư mục

```
main.tex                      — file chính (preamble + \input các phần)
references.bib                — 30 tài liệu tham khảo (IEEE)
frontmatter/
  00-thongtin.tex             — THÔNG TIN ĐỊNH DANH (sửa ở đây)
  01-biangoai.tex             — Mẫu 1: bìa ngoài
  02-biaphu.tex               — Mẫu 2: phụ bìa
  03-camdoan.tex              — Mẫu 3: lời cam đoan
  04-camon.tex                — lời cảm ơn
  05-vietat.tex               — danh mục từ viết tắt
  06-thongtindoan.tex         — Mẫu 4a (Việt) + 4b (Anh)
chapters/
  00-modau.tex                — MỞ ĐẦU
  01-tongquan.tex             — Chương 1: Tổng quan
  02-phuongphap.tex           — Chương 2: Phương pháp
  03-ketqua.tex               — Chương 3: Kết quả & thảo luận
  04-ketluan.tex              — Kết luận và kiến nghị
  05-phuluc.tex               — Phụ lục
```

## Quy cách đã áp dụng (theo QĐ 199/QĐ-KHTN)

- Khổ A4, một mặt; Times New Roman cỡ 13; giãn dòng 1,5.
- Lề: trên 3,5 cm; dưới 3 cm; trái 3,5 cm; phải 2 cm.
- Số trang ở giữa, cuối trang; phần chính đánh số Ả Rập, phần đầu số La Mã.
- Đầu đề bảng ở trên bảng, đầu đề hình ở dưới hình.
- Đánh số bảng/hình theo chương (Bảng 3.x, Hình 2.x).
- Tài liệu tham khảo theo phong cách IEEE.
