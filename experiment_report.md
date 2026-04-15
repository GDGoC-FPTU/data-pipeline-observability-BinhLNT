# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-E402
**Name:** Lê Nguyễn Thanh Bình
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu sach, hop le, agent dua ra ket qua chinh xac |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Du lieu bi nhieu (outlier gia rat lon), agent bi misleading | 

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

(Viet nhan xet cua ban o day — it nhat 50 tu)

(Hay phan tich cac van de nhu Duplicate IDs, wrong data types, outliers, null values
va giai thich tai sao chung anh huong den ket qua cua Agent.)

- Khi su dung garbage data, agent bi anh huong boi cac gia tri bat thuong (outliers), cu the la san pham "Nuclear Reactor" co gia len den $999999. Day la mot gia tri khong hop ly so voi cac san pham con lai, nhung vi khong co buoc validation hoac xu ly outlier trong du lieu nay, agent da coi day la lua chon tot nhat.

- Ngoai ra, garbage data co the chua cac van de khac nhu duplicate IDs, category khong dong nhat, hoac du lieu bi sai kieu. Nhung loi nay lam giam chat luong du lieu dau vao va dan den viec agent dua ra ket qua sai lech. Trong truong hop nay, agent khong du kha nang phan biet du lieu hop le va du lieu bi loi, nen bi “dan duong sai” boi mot gia tri cuc doan.

- Dieu nay cho thay rang neu khong co cac buoc lam sach du lieu (data cleaning) va kiem tra chat luong (validation), thi he thong AI se rat de bi anh huong boi du lieu xau va dua ra quyet dinh sai.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y

(Viet ket luan cua ban o day)
- Trong thi nghiem nay, cung mot agent va cung mot logic, nhung chi can thay doi chat luong du lieu dau vao da dan den ket qua hoan toan khac nhau. Du lieu sach giup agent dua ra ket qua hop ly, trong khi du lieu bi nhieu dan den quyet dinh sai lech nghiem trong. Do do, chat luong du lieu dong vai tro quan trong hon ca prompt trong cac he thong AI dua tren du lieu.
