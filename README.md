[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/LiEKMyvY)

# CSC4005 Lab 1 – NEU MLP Starter

**Họ tên:** Trần Việt Vinh  
**MSSV:** 1771040030  
**Lớp:** KHMT 17-01

---

## 📌 Tổng quan

Starter kit này dùng cho **Lab 1 – Training & Regularization** của CSC4005.

**Mục tiêu:** So sánh ít nhất 3 cấu hình huấn luyện, phân tích learning curves, tránh dùng test set để chọn mô hình, và kết luận cấu hình tốt nhất dựa trên validation set.

**Dataset:** NEU Surface Defect Database (6 loại lỗi bề mặt thép):
- Crazing
- Inclusion
- Patches
- Pitted Surface
- Rolled-in Scale
- Scratches

**Link W&B Dashboard:** https://wandb.ai/vinhviettran955-no/csc4005-lab1-neu-mlp

**Báo cáo chi tiết:** [REPORT_TEMPLATE.md](REPORT_TEMPLATE.md)

---

## 📁 Cấu trúc repo

```text
csc4005-lab1-neu-mlp-TRAN-VIET-VINH-1771040030-1/
├── .github/workflows/validate-lab1.yml
├── README.md                      # File hướng dẫn này
├── REPORT_TEMPLATE.md             # Báo cáo đầy đủ 8 yêu cầu
├── requirements.txt               # Các thư viện cần cài đặt
├── configs/
│   └── baseline.json              # Cấu hình baseline
├── docs/
│   ├── LAB_GUIDE_LAB1.md
│   └── WANDB_GUIDE.md
├── notebooks/
│   └── lab1_demo.ipynb
├── outputs/                       # Kết quả huấn luyện
│   ├── baseline_adamw/            # Config 1: Baseline (AdamW)
│   │   ├── best_model.pt
│   │   ├── curves.png
│   │   ├── confusion_matrix.png
│   │   └── metrics.json
│   ├── sgd_test/                  # Config 2: SGD
│   │   └── ...
│   └── high_reg/                  # Config 3: Regularization mạnh
│       └── ...
├── ci/
│   ├── check_structure.py
│   └── smoke_train.py
└── src/
    ├── __init__.py
    ├── dataset.py                 # Load và xử lý dữ liệu NEU
    ├── model.py                   # Định nghĩa mô hình MLP
    ├── train.py                   # Script huấn luyện chính
    └── utils.py                   # Hàm tiện ích

🚀 Cài đặt
1. Clone repository

git clone https://github.com/FFT-DNU-CS-16-01/csc4005-lab1-neu-mlp-TRAN-VIET-VINH-1771040030-1.git
cd csc4005-lab1-neu-mlp-TRAN-VIET-VINH-1771040030-1
2. Tạo môi trường ảo (khuyến nghị)


# Sử dụng conda
conda create -n csc4005-dl python=3.9
conda activate csc4005-dl

# Hoặc sử dụng venv (Windows)
python -m venv venv
venv\Scripts\activate

# Hoặc venv (Linux/Mac)
python -m venv venv
source venv/bin/activate

3. Cài đặt các thư viện
bash
pip install --upgrade pip
pip install -r requirements.txt
Nội dung file requirements.txt:

text
torch>=1.9.0
torchvision>=0.10.0
numpy>=1.19.0
matplotlib>=3.3.0
scikit-learn>=0.24.0
wandb>=0.12.0
tqdm>=4.62.0
Pillow>=8.3.0
