HỌ VÀ TÊM : BÙI MINH HOÀNG

LỚP : HCM_CNTT1

BÀI thiết kế hệ thống giám sát nhiệt độ cho chuỗi cung ứng lạnh tại FastShip


I.XÁC ĐỊNH CẤU TRÚC
 1. Mô hình IPO của hệ thống cảm biến nhiệt độ
   Input (Đầu vào) : Số đo nhiệt độ từ cảm biến; mã xe/thùng hàng; thời gian ghi nhận; ngưỡng nhiệt độ an toàn
   Process (Xử lý) : Gắn số đo với xe và thời gian; kiểm tra dữ liệu; so sánh với ngưỡng; phát hiện xu hướng tăng nhiệt; gửi cảnh báo
   Output (Đầu ra) : Nhiệt độ hiện tại trên bảng giám sát; cảnh báo khi vượt ngưỡng; lịch sử nhiệt độ và báo cáo


 2. Vai trò của BA và SE ở giai đoạn đầu
  Business Analyst (BA): Tìm hiểu nhu cầu của vận hành và khách hàng; xác định yêu cầu như ngưỡng an toàn cho từng loại hàng, ai nhận cảnh báo, và cần xử lý ra sao khi nhiệt độ bất thường.

  Software Engineer (SE): Đánh giá và đề xuất cách xây dựng hệ thống: kết nối cảm biến, truyền dữ liệu, xử lý cảnh báo, lưu trữ và bảo mật dữ liệu; đồng thời ước tính tính khả thi và công sức triển khai.

  
II,XỬ LÝ TÌNH HUỐNG
 3. Áp dụng DIKW
 
    - Các số đo 2°C, 3°C thu liên tục là Data (Dữ liệu): những giá trị thô chưa có nhiều ngữ cảnh.
    
    - “Thùng xe số 5 đang tăng nhiệt độ quá mức an toàn” là Information (Thông tin): các số đo đã được gắn với xe, xu hướng và ngưỡng an toàn để có ý nghĩa.
    
    Từ thông tin đó, hệ thống có thể áp dụng Knowledge (Tri thức), chẳng hạn quy trình xử lý khi nhiệt độ vượt ngưỡng; người vận hành dùng tri thức để quyết định hành động phù hợp — đó là Wisdom (Minh triết).
 4.Tính dung lượng dữ liệu
        Một ngày có:
    24 × 60 × 60 = 86.400 giây
    Giả sử dùng đơn vị thập phân (1 MB = 1.000 KB; 1 GB = 1.000 MB):
    - 1 xe tải: 86.400 giây × 1 KB = 86.400 KB = 86,4 MB/ngày
    - 1.000 xe tải: 86,4 MB × 1.000 = 86.400 MB = 86,4 GB/ngày
    Đây là dung lượng log thô, chưa tính phần dữ liệu phụ trợ, bản sao lưu hay mức tăng do định dạng lưu trữ.
