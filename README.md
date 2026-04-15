[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574052&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600442
**Student Email:** vuquangdung71104@gmail.com
**Name:** Vũ Quang Dũng

---

## Mo ta

Trong bai lab nay, toi da hoan thanh ETL pipeline gom 4 buoc Extract, Validate, Transform, Load trong file solution.py. Du lieu dau vao duoc doc tu JSON, loai bo cac ban ghi khong hop le (price <= 0 hoac category rong), tinh discounted_price = price * 0.9, chuan hoa category ve Title Case va them cot processed_at truoc khi luu ra processed_data.csv. Ngoai ra, toi da chay stress test voi du lieu clean va garbage, sau do ghi nhan ket qua va phan tich trong experiment_report.md.

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
python solution.py; python generate_garbage.py; python agent_simulation.py
```

Ket qua stress test mong doi:
- CLEAN data: Agent chon Laptop gia $1200.
- GARBAGE data: Agent chon Nuclear Reactor gia $999999 (bi anh huong boi outlier).

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

- ETL pipeline chay thanh cong, tao file `processed_data.csv`.
- Validation: Valid = 3 records, Errors = 2 records.
- Agent Simulation voi CLEAN data: "Agent: Based on my data, the best choice is Laptop at $1200."
- Agent Simulation voi GARBAGE data: "Agent: Based on my data, the best choice is Nuclear Reactor at $999999."
