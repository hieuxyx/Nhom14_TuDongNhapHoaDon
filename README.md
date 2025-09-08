[🎓 Faculty of Information Technology (DaiNam University)](https://github.com/UB-Mannheim/tesseract/wiki)

Triển khai ứng dụng AI, IoT
![z6917654370462_2817f81f026235364ef69cc6d6056fcc](https://github.com/user-attachments/assets/2468521f-38b0-4b43-a4b4-cd75490dfb1d)


# Hệ thống Tự động nhập liêu hóa đơn chứng từ, quét qr

🔹 1. Chuẩn bị môi trường
a. Cài Python (nếu chưa có)

Nên dùng Python 3.10 hoặc 3.11 (ổn định nhất cho thư viện).

Cài từ [python.org](https://www.python.org/downloads/)
 → nhớ tick Add to PATH khi cài.

b. Cài Tesseract OCR

Tải tại đây: [UB Mannheim Tesseract](https://github.com/UB-Mannheim/tesseract/wiki)
 (phiên bản ổn định cho Windows).

Cài đặt, mặc định sẽ nằm ở:

C:\Program Files\Tesseract-OCR\tesseract.exe


Thêm đường dẫn này vào PATH (Environment Variables).

Hoặc trong code đã có sẵn dòng:

pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"


thì không cần thêm PATH nữa.

c. Cài thư viện Python cần thiết

Mở CMD (hoặc Terminal) tại thư mục chứa app.py, chạy:

pip install streamlit opencv-python pytesseract pillow numpy pandas xlsxwriter

🔹 2. Chạy ứng dụng

Trong CMD (hoặc PowerShell), di chuyển vào thư mục chứa file app.py rồi chạy:

streamlit run app.py

🔹 3. Sử dụng ứng dụng

Khi app chạy, trình duyệt mở tại địa chỉ:

http://localhost:8501


Có 2 cách lấy ảnh:

📂 Upload ảnh hóa đơn (.jpg, .png, .jpeg)

📷 Dùng camera chụp trực tiếp (nếu đã thêm chức năng st.camera_input).

Hệ thống sẽ:

Tiền xử lý ảnh (lọc nhiễu, tăng tương phản, nhị phân hóa).

Chạy nhiều chế độ OCR (psm khác nhau) để chọn kết quả tốt nhất.

Hiển thị ảnh gốc + ảnh đã xử lý bên trái.

Hiển thị văn bản OCR bên phải.

Có thể tải kết quả xuống:

⬇️ CSV (hoadon_ocr.csv)

⬇️ Excel (hoadon_ocr.xlsx)
