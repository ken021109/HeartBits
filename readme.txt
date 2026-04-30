# Stroke Alert VN

Ứng dụng Streamlit hỗ trợ sàng lọc nguy cơ đột quỵ. Công cụ này chỉ dùng để tham khảo ban đầu, không thay thế chẩn đoán hoặc hướng dẫn điều trị của bác sĩ.

## I. YÊU CẦU HỆ THỐNG

1. Windows 10/11.
2. Python 3.9 trở lên, khuyến khích Python 3.11.
3. Khi cài Python, nên chọn `Add Python to PATH`.

## II. CÁCH CÀI ĐẶT

Chạy file:

```bat
setup.bat
```

Script này sẽ:

- Tạo môi trường ảo `venv`.
- Cập nhật `pip`.
- Cài các thư viện trong `requirements.txt`.

## III. CHẠY ỨNG DỤNG

Chạy file:

```bat
run.bat
```

Ứng dụng sẽ mở bằng Streamlit, thường tại:

```text
http://localhost:8501
```

## IV. HUẤN LUYỆN LẠI MÔ HÌNH

Mô hình đã có sẵn trong dự án. Nếu cần huấn luyện lại, chạy:

```bat
train.bat
```

Script này sẽ chạy:

```bat
python training_logicstic.py
```

Sau khi train xong, dự án sẽ tạo/cập nhật:

- `stroke_final_model.pkl`
- `preprocessor_meta.pkl`

## V. CẤU TRÚC DỰ ÁN

```text
HeartBits v2/
├── app.py                              Ứng dụng Streamlit chính
├── training_logicstic.py               Pipeline huấn luyện Logistic Regression
├── requirements.txt                    Danh sách thư viện Python
├── readme.txt                          Tài liệu hướng dẫn
├── healthcare-dataset-stroke-data.csv  Dataset dùng để huấn luyện
├── stroke_final_model.pkl              Model đã huấn luyện
├── preprocessor_meta.pkl               Metadata tiền xử lý và thông tin feature
├── setup.bat                           Script cài đặt môi trường
├── run.bat                             Script chạy ứng dụng
├── train.bat                           Script huấn luyện mô hình
└── venv/                               Môi trường ảo, không đưa vào Git
```

## VI. XỬ LÝ LỖI THƯỜNG GẶP

### 1. Python không được tìm thấy

Cài lại Python và đảm bảo đã chọn `Add Python to PATH`.

### 2. Không chạy được ứng dụng

Chạy `setup.bat` trước, sau đó chạy lại `run.bat`.

### 3. Thiếu file model

Nếu ứng dụng báo thiếu `stroke_final_model.pkl`, hãy chạy `train.bat` để tạo lại model.

### 4. Muốn dừng ứng dụng

Quay lại cửa sổ lệnh đang chạy Streamlit và nhấn `Ctrl + C`.
