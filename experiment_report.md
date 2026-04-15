# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600442
**Name:** Vũ Quang Dũng
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Ket qua hop ly, do du lieu da duoc lam sach: bo gia am, category rong, category duoc chuan hoa. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent bi outlier thao tung, chon mat hang gia cuc cao nhung phi thuc te cho nhu cau thong thuong. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Trong bo Garbage Data, co nhieu loi chat luong du lieu cung luc nen Agent de bi dan den ket qua sai. Duplicate ID lam mat tinh nhat quan cua ban ghi, trong khi wrong data type (gia = "ten dollars") co the gay loi parse hoac buoc he thong bo qua logic phan tich binh thuong. Null values lam giam do tin cay cua bo loc category. Nghiem trong nhat la outlier "Nuclear Reactor" co gia 999999. Vi logic trong agent_simulation.py chon san pham electronics co gia cao nhat, outlier nay ap dao toan bo du lieu hop ly va tao ra cau tra loi vo ly. Truong hop nay cho thay prompt co tot den dau cung kho cuu duoc dau vao ban.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** (Dong y hay khong? Giai thich ngan gon.)

Dong y. Prompt giup huong dan cach tra loi, nhung chat luong du lieu moi quyet dinh gioi han cua su that ma Agent co the hoc va suy ra. Khi du lieu da duoc validate/transform tot, Agent cho ket qua dung va on dinh hon ro ret.
