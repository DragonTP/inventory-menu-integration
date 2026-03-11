# 🍱 Inventory & Menu Integration

## 📖 Project Overview

**Impact:** Saves **15+ hours/month** by automating the reconciliation between **Warehouse Issuance Logs** and **Daily Kitchen Menus**.

In high-volume **F&B operations**, staff manually filter thousands of rows to match **"What was issued"** with **"What was cooked."**  
This project replaces hours of manual cross-checking with a **seconds-long automated pipeline**.

![Overview image of Inventory & Menu Integration project](https://github.com/DragonTP/inventory-menu-integration/blob/9ed837000f852a8f61978ffda9e70d8d622f22e0/assets/comparison.jpg)

---

## ⚡ The Challenge

### Time Sink
Manual filtering and copy-pasting take **1–2 hours of productive time daily**.

### Complexity
Menus use **merged cells** and **inconsistent date formats**, which break standard Excel tools.

### Fragmentation
Inventory and menu data exist in **separate silos**, preventing a unified operational view.

---

## ⚙️ Automation Pipeline (The Logic)

The script follows a **3-step ETL process** to transform fragmented logs into a **unified, print-ready report**.

---

### 📑 Menu Parsing & Standardization

- Uses **`.ffill()` (Forward Fill)** to resolve merged cells.  
- Ensures every dish is **correctly categorized**.
- Maps cleaned data into a **`menu_dict` structure** for **instant date-based lookup**.

---

### 📦 Dynamic Inventory Slicing (Regex)

- Uses **Regex pattern matching** to detect **date markers**  
  *(e.g., "Ngày... tháng... năm...")*.
- Automatically **splits continuous master lists into daily blocks**.
- Works regardless of **row count or variations in data length**.

---

### 🔗 Smart Integration

- Performs a **Pandas horizontal concat** to align **Inventory and Menu** side-by-side.
- Generates a **multi-sheet `.xlsx` report** using **ExcelWriter**.

---

## 🛠 Tech Stack

- **Python**
- **Pandas**
- **Regex**
- **ExcelWriter**
