# Bài Tập: Xây Dựng Cơ Sở Dữ Liệu Quản Lý Bán Hàng (QuanLyBanHang)

## 1. Giới thiệu
Cơ sở dữ liệu `QuanLyBanHang` được thiết kế để quản lý hoạt động bán hàng của siêu thị / cửa hàng, bao gồm việc lưu trữ thông tin khách hàng, các hóa đơn mua hàng, sản phẩm và chi tiết các mặt hàng trong từng hóa đơn.

## 2. Cấu trúc CSDL
Hệ thống gồm 4 bảng chính:
- **`Customer` (Khách hàng):** 
  - `cID`: Mã khách hàng (Khóa chính, tự tăng).
  - `cName`: Tên khách hàng.
  - `cAge`: Tuổi khách hàng.
- **`Order` (Hóa đơn):**
  - `oID`: Mã hóa đơn (Khóa chính, tự tăng).
  - `cID`: Mã khách hàng mua hàng (Khóa ngoại tham chiếu `Customer(cID)`).
  - `oDate`: Ngày mua hàng.
  - `oTotalPrice`: Tổng tiền hóa đơn.
- **`Product` (Sản phẩm):**
  - `pID`: Mã sản phẩm (Khóa chính, tự tăng).
  - `pName`: Tên sản phẩm.
  - `pPrice`: Giá bán sản phẩm.
- **`OrderDetail` (Chi tiết hóa đơn):**
  - `oID`: Mã hóa đơn (Khóa ngoại tham chiếu `Order(oID)`).
  - `pID`: Mã sản phẩm (Khóa ngoại tham chiếu `Product(pID)`).
  - `odQTY`: Số lượng sản phẩm mua.
  - Khóa chính tổng hợp: `(oID, pID)`.

## 3. Cách chạy kịch bản
1. Mở MySQL Workbench hoặc MySQL CLI.
2. Thực thi toàn bộ lệnh trong file `QuanLyBanHang.sql`.
