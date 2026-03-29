# Tutor Support System (TSS) - Frontend Application

Tutor Support System là ứng dụng web trực tuyến được phát triển bằng Next.js, thiết kế để kết nối quy trình học tập giữa Sinh viên và Gia sư. Dự án tập trung vào việc xử lý các luồng giao diện phức tạp, áp dụng kiến trúc App Router nhằm quản lý định tuyến và tối ưu hóa việc tái sử dụng UI Component giữa các phân hệ người dùng khác nhau.

## Công nghệ sử dụng
* **Core:** Next.js (App Router), React
* **Styling:** Tailwind CSS
* **Thư viện tích hợp:** @fullcalendar/react (xử lý lịch trình)
* **Kiến trúc UI:** Component-driven, Role-based Route Groups, Dynamic Routing

## Điểm nhấn Kỹ thuật & Tính năng

Dự án được cấu trúc thành hai luồng giao diện chính. Bằng cách sử dụng Route Groups của Next.js, hệ thống tách biệt hoàn toàn URL và Layout cho từng vai trò người dùng nhưng vẫn đảm bảo khả năng tái sử dụng các component cốt lõi.

### Phân hệ Sinh viên
* **Bảng điều khiển (Dashboard):** Hiển thị dữ liệu học tập và lịch trình tổng quan trong ngày.
* **Bộ lọc Tìm kiếm:** Giao diện tìm kiếm gia sư tích hợp các form tiêu chí linh hoạt.
* **Lịch học tương tác:** Tích hợp và tùy biến FullCalendar để render lịch cá nhân theo nhiều góc nhìn (Tháng/Tuần/Ngày).
* **Quản lý Lớp học (Dynamic Routing):** Xử lý định tuyến động cho chi tiết từng lớp học. Giao diện áp dụng cấu trúc Tab để chuyển đổi mượt mà giữa các nhóm nội dung (Bài giảng, Bài kiểm tra, Lịch hẹn) mà không làm gián đoạn trải nghiệm người dùng.

### Phân hệ Gia sư
* **Bảng quản trị:** Theo dõi số liệu học viên, giờ dạy và các yêu cầu đăng ký đang chờ xử lý.
* **Quản lý Form & Dữ liệu:** Xây dựng hệ thống form và modal phức tạp phục vụ các nghiệp vụ quản lý: tạo lớp học mới, tải lên tài liệu giảng dạy, và thiết lập ca học.
* **Không gian làm việc chuyên sâu:** Giao diện quản lý chi tiết lớp học được thiết kế tối ưu cho việc điều hướng, tích hợp Action Sidebar để thực hiện nhanh các thao tác quản trị.

### Giao diện Nhắn tin dùng chung (Shared Chat UI)
* **Kiến trúc Component:** Cấu trúc layout chat hai cột linh hoạt (danh sách hội thoại và khung chat chi tiết).
* **Tối ưu mã nguồn (DRY):** Tách biệt tầng UI và luồng xử lý dữ liệu để tái sử dụng toàn bộ giao diện chat này cho cả hai phân hệ. Trạng thái và nội dung của từng luồng hội thoại được quản lý chặt chẽ thông qua hệ thống Dynamic Routes của Next.js.

## Cấu trúc thư mục nền tảng

Dự án tuân thủ nguyên tắc phân tách rõ ràng giữa định tuyến, giao diện dùng chung và các module chức năng:

```text
src/
├── app/
│   ├── Sinhvien/               # Route Group xử lý định tuyến cho Sinh viên
│   │   ├── layout.tsx          # Shared layout: Sidebar, Header
│   │   ├── my-classes/
│   │   │   └── [classId]/      # Dynamic routing cho chi tiết lớp
│   │   └── tin-nhan/
│   ├── Tutor/                  # Route Group xử lý định tuyến cho Gia sư
│   │   ├── layout.tsx
│   │   └── my-classes/
├── components/                 # Reusable UI Components
│   ├── layout/                 # Các thành phần dàn trang (Sidebar, Dropdown)
│   ├── shared/                 # Các component chức năng dùng chung (FullCalendar, ChatWindow)
│   └── modals/                 # Hệ thống thao tác nhanh (Tạo lớp, Đăng ký)
