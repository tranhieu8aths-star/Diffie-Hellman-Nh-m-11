<img width="468" height="661" alt="image" src="https://github.com/user-attachments/assets/24f63636-08c5-4d1f-9a1d-f6c616cced31" /># Diffie-Hellman-GROUP11
ATBMTT- DIFFIE HELLMAN
1. Tổng quan dự án
Dự án này triển khai thuật toán trao đổi khóa Diffie-Hellman bằng ngôn ngữ lập trình Python. Thuật toán cho phép hai bên thiết lập một khóa bí mật chung thông qua một kênh truyền thông không an toàn mà không cần truyền trực tiếp khóa riêng tư của mình.
Dự án được phát triển qua 10 phiên bản. Mỗi phiên bản bổ sung các chức năng mới, cải thiện khả năng kiểm tra dữ liệu đầu vào và hoàn thiện chương trình để hoạt động đầy đủ, đáng tin cậy hơn.
2. Mục tiêu dự án
- Hiểu nguyên lý hoạt động của thuật toán trao đổi khóa Diffie-Hellman.
- Triển khai thuật toán bằng ngôn ngữ lập trình Python.
- Tạo khóa công khai từ khóa riêng tư.
- Mô phỏng quá trình trao đổi khóa công khai giữa hai bên.
- Tính toán và xác minh khóa bí mật chung.
- Kiểm tra dữ liệu đầu vào và các tham số công khai.
- Xây dựng chương trình hoàn chỉnh, có cấu trúc rõ ràng.
3. Cơ sở lý thuyết và công thức toán học
Thuật toán Diffie-Hellman sử dụng các tham số sau:
- q: Một số nguyên tố.
- α (alpha): Một căn nguyên thủy modulo q.
- xA: Khóa riêng tư của bên A.
- xB: Khóa riêng tư của bên B.
- yA: Khóa công khai của bên A.
- yB: Khóa công khai của bên B.
Tạo khóa công khai
Bên A tính khóa công khai:
[
y_A=\alpha^{x_A}\bmod q
]
Bên B tính khóa công khai:
[
y_B=\alpha^{x_B}\bmod q
]
Tính toán khóa bí mật chung
Bên A tính:
[
K_A=y_B^{x_A}\bmod q
]
Bên B tính:
[
K_B=y_A^{x_B}\bmod q
]
Cả hai bên thu được cùng một khóa bí mật chung:
[
K_A=K_B
]
4. Quá trình phát triển – 10 phiên bản
Version 1: Diffie-Hellman cơ bản
- Triển khai thuật toán Diffie-Hellman cơ bản.
- Sử dụng các tham số công khai được thiết lập sẵn (q = 353, α = 3).
- Sử dụng khóa riêng tư được thiết lập sẵn cho bên A và bên B.
- Tính toán khóa công khai và khóa bí mật chung.
 -Hiển thị kết quả tính toán.
Version 2: Nhập dữ liệu từ người dùng
- Thay thế khóa riêng tư được thiết lập sẵn bằng dữ liệu do người dùng nhập.
- Cho phép người dùng nhập khóa riêng tư của bên A và bên B.
- Tính toán khóa công khai và khóa bí mật chung dựa trên các giá trị đã nhập.
Version 3: Kiểm tra kiểu dữ liệu đầu vào
- Bổ sung cơ chế xử lý ngoại lệ try-except.
- Kiểm tra xem khóa riêng tư có được nhập dưới dạng số nguyên hay không.
-  Hiển thị thông báo lỗi khi người dùng nhập sai kiểu dữ liệu.
- Ngăn chương trình bị dừng đột ngột do dữ liệu đầu vào không hợp lệ.
Version 4: Kiểm tra tính hợp lệ của khóa riêng tư
- Bổ sung chức năng kiểm tra giá trị khóa riêng tư.
- Đảm bảo khóa riêng tư thỏa mãn điều kiện:
1 <= private_key < q - 1
-Hiển thị thông báo lỗi khi khóa riêng tư nằm ngoài phạm vi hợp lệ.
Version 5: Tạo khóa công khai
-Xây dựng hàm calculate_public_key().
-Tách riêng chức năng tạo khóa công khai khỏi chương trình chính.
-Cải thiện cách tổ chức mã nguồn và khả năng tái sử dụng hàm.
Version 6: Trao đổi khóa công khai
-Mô phỏng quá trình trao đổi khóa công khai giữa bên A và bên B.
-Bên A gửi khóa công khai cho bên B.
-Bên B gửi khóa công khai cho bên A.
-Hiển thị các khóa công khai được gửi và nhận bởi cả hai bên.
Version 7: Tính toán khóa bí mật chung
-Xây dựng hàm calculate_shared_key().
-Sử dụng khóa công khai nhận được và khóa riêng tư của mỗi bên để tính toán khóa bí mật chung.
-Tính toán khóa bí mật độc lập tại bên A và bên B.
Version 8: Xác minh khóa bí mật chung
-Bổ sung bước xác minh để so sánh hai khóa bí mật.
-Kiểm tra xem khóa được tính toán bởi hai bên có giống nhau hay không.
-Hiển thị thông báo thành công nếu hai khóa trùng khớp.
-Hiển thị thông báo thất bại nếu hai khóa không trùng khớp.
Version 9: Kiểm tra tính hợp lệ của tham số công khai
-Bổ sung hàm is_prime() để kiểm tra xem q có phải là số nguyên tố hay không.
-Bổ sung hàm prime_factors() để tìm các thừa số nguyên tố phân biệt của q - 1.
-Bổ sung hàm is_primitive_root() để xác minh α có phải là căn nguyên thủy modulo q hay không.
-Cho phép người dùng nhập các tham số công khai.
-Kiểm tra tính hợp lệ của các tham số trước khi thực hiện quá trình tạo khóa.
Version 10: Phiên bản hoàn thiện cuối cùng
-Tích hợp tất cả các chức năng của những phiên bản trước vào một chương trình hoàn chỉnh.
-Tổ chức chương trình bằng các hàm riêng biệt.
-Bổ sung hàm main() để điều khiển quá trình thực thi chương trình.
-Kiểm tra tính hợp lệ của các tham số công khai (q và α).
-Kiểm tra tính hợp lệ của khóa riêng tư của cả hai bên.
-Tạo và trao đổi khóa công khai.
-Tính toán khóa bí mật chung độc lập tại mỗi bên.
-So sánh hai khóa bí mật để xác minh kết quả.
-Cải thiện cấu trúc chương trình và khả năng xử lý lỗi.
-Bổ sung câu lệnh if __name__ == "__main__": để kiểm soát quá trình thực thi chương trình.
5. Các chức năng chính
Phiên bản cuối cùng bao gồm những chức năng sau:
Chức năng	Mô tả
Kiểm tra số nguyên tố	Kiểm tra xem q có phải là số nguyên tố hay không.
Kiểm tra căn nguyên thủy	Kiểm tra α có phải là căn nguyên thủy hợp lệ modulo q hay không.
Kiểm tra khóa riêng tư	Đảm bảo khóa riêng tư nằm trong phạm vi hợp lệ.
Tạo khóa công khai	Tính toán khóa công khai cho cả hai bên.
Trao đổi khóa công khai	Mô phỏng quá trình trao đổi khóa công khai.
Tính toán khóa bí mật	Tính toán khóa bí mật chung độc lập tại mỗi bên.
Xác minh khóa bí mật	Kiểm tra xem hai bên có thu được cùng một khóa hay không.
Xử lý lỗi	Xử lý trường hợp người dùng nhập dữ liệu không phải số nguyên.
6. Công nghệ sử dụng
-Ngôn ngữ lập trình: Python.
-Môi trường phát triển: Python IDE hoặc Visual Studio Code.
-Quản lý phiên bản: Git và GitHub.
-Thư viện: Các hàm có sẵn của Python (không yêu cầu cài đặt thư viện bên ngoài).
7. Hướng dẫn cài đặt và chạy chương trình
Bước 1: Sao chép kho lưu trữ (Repository)
git clone <repository-url>
Bước 2: Truy cập thư mục dự án
cd <project-folder>
Bước 3: Chạy chương trình
python diffie_hellman.py
Bước 4: Nhập các tham số cần thiết
Chương trình yêu cầu người dùng nhập:
1.	Số nguyên tố q.
2.	Căn nguyên thủy α.
3.	Khóa riêng tư của bên A.
4.	Khóa riêng tư của bên B.
Sau đó, chương trình kiểm tra tính hợp lệ của dữ liệu đầu vào và thực hiện quá trình trao đổi khóa Diffie-Hellman.
8. Quy trình hoạt động của chương trình
Bắt đầu
   |
   v
Nhập tham số công khai (q, alpha)
   |
   v
Kiểm tra tính hợp lệ của q và alpha
   |
   v
Nhập khóa riêng tư (xA, xB)
   |
   v
Kiểm tra khóa riêng tư
   |
   v
Tạo khóa công khai
   |
   v
Trao đổi khóa công khai
   |
   v
Tính toán khóa bí mật chung
   |
   v
Xác minh khóa bí mật
   |
   v
Hiển thị kết quả
   |
   v
Kết thúc
9. Cấu trúc dự án
Ví dụ về cách tổ chức thư mục trong Repository:
Diffie-Hellman/
│
├── README.md
├── diffie_hellman.py
│
└── versions/
    ├── version_1.py
    ├── version_2.py
    ├── version_3.py
    ├── version_4.py
    ├── version_5.py
    ├── version_6.py
    ├── version_7.py
    ├── version_8.py
    ├── version_9.py
    └── version_10.py
10. Kết luận
Thông qua 10 phiên bản phát triển, dự án thể hiện quá trình xây dựng và hoàn thiện dần thuật toán trao đổi khóa Diffie-Hellman.
Bắt đầu từ phiên bản triển khai cơ bản, dự án lần lượt bổ sung các chức năng nhập dữ liệu, kiểm tra dữ liệu đầu vào, xây dựng các hàm riêng biệt, trao đổi khóa công khai, tính toán khóa bí mật chung và xác minh kết quả.
Phiên bản cuối cùng tích hợp tất cả các chức năng trên thành một chương trình Python có cấu trúc rõ ràng, giúp người dùng hiểu cách hai bên có thể thiết lập cùng một khóa bí mật chung mà không cần trực tiếp chia sẻ khóa riêng tư của mình.


