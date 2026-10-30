\# Green-Tech: không gian cộng tác dự án trang trại thông minh



\## Cấu trúc folder



green-tech/

&#x20; sensors/           code cảm biến (repo Git)

&#x20; reports/           báo cáo tiến độ, tài chính, hiệu quả cho nhà đầu tư

&#x20; partner-docs/      thông số kỹ thuật thiết bị của đối tác

&#x20; .env               mật khẩu cảm biến, chỉ nằm trên máy dev và secret manager

&#x20; .env.example       mẫu khai báo biến, không chứa giá trị thật



\## Hybrid Workflow cho đội Dev



Mỗi dev làm trên bản local, commit thường xuyên, rồi push lên GitHub (repo private). Nhánh main bật branch protection, mọi thay đổi phải qua Pull Request và có một người duyệt. Cuối ngày, repo được đồng bộ một bản sao lên cloud (Google Drive) để có thêm một lớp lưu trữ độc lập với GitHub.



\## Cấu trúc channel (Slack)



\#dev-general     trao đổi hằng ngày của đội kỹ thuật

\#sensor-bugs     báo lỗi cảm biến, mỗi lỗi một thread

\#partner-feedback  góp ý từ đối tác thiết bị



\## Phân quyền



| Đối tượng | sensors | reports | partner-docs |

|---|---|---|---|

| Trưởng dự án | Owner | Owner | Owner |

| Dev | Editor | Viewer | Viewer |

| Nhà đầu tư | Không có | Viewer | Không có |

| Đối tác thiết bị | Không có | Không có | Commenter |



Với nhà đầu tư, tắt tùy chọn tải xuống, in và sao chép. Chỉ Owner được đổi quyền chia sẻ.



\## Bảo vệ file .env



File .env nằm trong .gitignore nên không bao giờ được commit. Mật khẩu thật lưu trong GitHub Secrets, dev lấy từ đó. Nếu cần để file trên Drive, đặt chế độ Restricted và chỉ thêm đúng tên người cần dùng, không dùng link chia sẻ.



\## Biến thảo luận lỗi thành Task



Khi có lỗi trong #sensor-bugs, bấm vào tin nhắn, chọn tạo Task (Slack Lists hoặc Teams Planner). Mỗi Task có người phụ trách, deadline 48 giờ kể từ lúc tạo, nhãn mức độ (Cao, Trung bình, Thấp) và link về thread gốc. Xử lý xong thì đổi trạng thái sang Done.



\## Bàn giao khi kết thúc



Trưởng dự án dùng Transfer Ownership để chuyển quyền Owner của folder Drive và repo GitHub cho người nhận (giảng viên hoặc trưởng nhóm kế nhiệm). Người nhận phải được thêm làm Editor trước thì mới chuyển được. Sau khi chuyển, kiểm tra lại danh sách quyền và gỡ các tài khoản không còn cần.

