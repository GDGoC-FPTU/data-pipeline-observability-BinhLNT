[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23572413&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** AI20K-0447
**Student Email:** thanhbinh.lenguyen.1208@gmail.com
**Name:** Lê Nguyễn Thanh Bình

---

## Mo ta

Trong bai lab nay, toi da xay dung mot ETL pipeline don gian bang Python de xu ly du lieu tu file JSON. Pipeline bao gom 4 buoc chinh: Extract, Validate, Transform va Load.

- O buoc Extract, du lieu duoc doc tu file `raw_data.json`.
- O buoc Validate, cac record khong hop le (gia <= 0 hoac category rong) se bi loai bo.
- O buoc Transform, toi tinh gia sau khi giam 10% (`discounted_price`), chuan hoa `category` ve dang Title Case, va them cot `processed_at` de danh dau thoi gian xu ly.
- Cuoi cung, du lieu da duoc lam sach se duoc luu vao file CSV (`processed_data.csv`).

Ngoai ra, toi cung thuc hien logging de theo doi so luong record hop le va bi loai, giup tang tinh minh bach (observability) cua pipeline.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
# Mo ta cach ban chay thi nghiem Clean vs Garbage data
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

(Tom tat ket qua: bao nhieu records da xu ly, bao nhieu bi loai, v.v.)

Sau khi chay pipeline voi du lieu dau vao (`raw_data.json`), ket qua thu duoc nhu sau:

- Tong so record dau vao: 5
- So record hop le sau validation: 3
- So record bi loai: 2

Du lieu sau khi xu ly duoc luu trong file `processed_data.csv` voi cac truong:

- id: Ma san pham
- product: Ten san pham
- price: Gia goc
- category: Danh muc (da duoc chuan hoa Title Case)
- discounted_price: Gia sau khi giam 10%
- processed_at: Thoi gian xu ly du lieu

### Vi du output:

```csv
id,product,price,category,discounted_price,processed_at
1,Laptop,1200,Electronics,1080.0,2026-04-15T11:44:07.939335
2,Chair,45,Furniture,40.5,2026-04-15T11:44:07.939335
5,Monitor,300,Electronics,270.0,2026-04-15T11:44:07.939335
