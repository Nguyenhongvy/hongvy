![Diagram](https://www.planttext.com/api/plantuml/png/V99D2i8m48NtESNWlbSGVxeH54JTYOinZX9DapADGX5Fvi8ZUGLR5RLnTFlovdsPbrpFbquHaCC-iqhbg7Uu8MZrhI4NO8WbSGkE2c0-Cnbfv1KCN21UewP5BO-np6fhKvrGxZaOj_dKJn-0RfvRep4OxsJAcBscegWY6fX8VdEcn0SJKr8C25rTJpGeLHfxQo7jnTkmtv8EqK4SkSI2vBpdOIDhXAwQlDy-xTt3f2uXITe_rXSwVhYbKiJg7tQXB2KIN-b2IHBqh_-R-i-kP3qQUTKiFzZJBVUlEkHMzM-_0G00__y30000)
**Lý do chọn đề tài**

• Biểu đồ lớp và sequence giúp mô tả rõ ràng các đối tượng chính và cách chúng tương tác với nhau trong hệ thống. Điều này giúp cho việc phân tích và phát triển hệ thống trở nên dễ dàng hơn.

• Các lớp được tổ chức theo chức năng riêng biệt, giúp tách biệt rõ ràng các nhiệm vụ khác nhau như quản lý thẻ thời gian .

• Thiết kế này cho phép dễ dàng mở rộng và thêm mới các chức năng mà không cần thay đổi cấu trúc hiện có

• Cách tiếp cận này cho phép tích hợp dễ dàng với các hệ thống hiện có, như cơ sở dữ liệu Quản lý Dự án hiện tại.

**Ý nghĩa từng thành phần trong kiến trúc**

•  Client Layer (Lớp giao diện người dùng) là lớp mà người dùng (nhân viên) sẽ trực tiếp tương tác

•  Application Layer (Lớp ứng dụng) Lớp này chịu trách nhiệm xử lý các logic nghiệp vụ cốt lõi của hệ thống.

•  Data Access Layer (Lớp truy cập dữ liệu)  Lớp này đảm nhiệm vai trò trung gian giữa lớp ứng dụng và cơ sở dữ liệu.

•  Database Layer (Lớp cơ sở dữ liệu) là nơi lưu trữ tất cả dữ liệu của hệ thống, bao gồm thông tin nhân viên, thẻ thời gian, phương thức thanh toán và các mã số dự án. 


**2 .Cơ chế phân tích**

Quản lý giao diện người dùng

•	Lý do: Cần có giao diện Windows-based dễ sử dụng cho nhân viên để nhập thông tin thẻ thời gian, chọn phương thức thanh toán và tạo báo cáo.

•	Cơ chế: Sử dụng công cụ lập trình như .NET để phát triển giao diện người dùng.

Kiểm tra tính hợp lệ của dữ liệu đầu vào

•	Lý do: Đảm bảo rằng dữ liệu nhập vào là chính xác và hợp lệ, từ đó tránh sai sót trong quá trình tính toán lương.

•	Cơ chế: Áp dụng các kiểm tra và ràng buộc trên các trường nhập liệu (như số giờ làm việc, số tài khoản ngân hàng).
Tích hợp cơ sở dữ liệu hiện có

•	Lý do: Hệ thống mới cần truy cập thông tin từ cơ sở dữ liệu Quản lý Dự án (DB2 trên mainframe IBM).

•	Cơ chế: Sử dụng JDBC hoặc các giao thức tương tự để truy cập cơ sở dữ liệu DB2.
Bảo mật dữ liệu

•	Lý do: Bảo vệ thông tin cá nhân của nhân viên và đảm bảo chỉ những người có quyền mới có thể truy cập hoặc thay đổi dữ liệu.

•	Cơ chế: Sử dụng các giao thức bảo mật (SSL/TLS) và quản lý quyền truy cập dựa trên vai trò.

Tính toán lương tự động

•	Lý do: Đảm bảo rằng các tính toán lương được thực hiện chính xác và không cần can thiệp thủ công.

•	Cơ chế: Xây dựng các thuật toán tính toán giờ làm việc, lương và hoa hồng bán hàng.

Gửi thông tin thanh toán

•	Lý do: Đảm bảo rằng các phương thức thanh toán mà nhân viên chọn được thực hiện chính xác và kịp thời.

•	Cơ chế: Kết nối với hệ thống ngân hàng để gửi thông tin thanh toán hoặc chuẩn bị phiếu lương để gửi qua thư.

Báo cáo và kiểm tra

•	Lý do: Cung cấp khả năng tra cứu thông tin cho nhân viên và đảm bảo tính đúng đắn của hệ thống.

•	Cơ chế: Xây dựng các chức năng báo cáo và công cụ kiểm tra để quản trị viên có thể kiểm tra và xác nhận thông tin.

Danh sách cơ chế phù hợp

•	Quản lý giao diện người dùng

•	Kiểm tra tính hợp lệ của dữ liệu đầu vào

•	Tích hợp cơ sở dữ liệu hiện có

•	Bảo mật dữ liệu

•	Tính toán lương tự động

•	Gửi thông tin thanh toán

•	Báo cáo và kiểm tra

**3 Các lớp phân tích cho ca sử dụng Payment**

Biểu đồ mô tả hành vi thông qua biểu đồ sequence cho ca sử dụng Payment: 
![Diagram](https://www.planttext.com/api/plantuml/png/R951RiCW44Ntd09bdmjuKKKENNXHoGhA0IRuMqKouCBOKiwMHOxKAnGdSQtMtY7cyUTzyNsx7n9JvC5rWWo7ADzTtuKh8FfyROtjoRFSrNHro8VACs9B1Zj9ITRL9gKHHpiZ-Y-YYEb2wJbKfH3pFhb_otc5rEXWMCuBFy2VeH5rzPZhGjOn6AIq0lG4gBAG9t2q6F7R94kt8JfY6xnGvHoauPjjvfaroPpmDI0jDWfCjaihwImrsWOhRj7MmyNPTT2YVUuROcpNcbOSWszjTF-0rpDno6McFnJY1m00__y30000)
Employee
o	Thuộc tính: employeeID, name, paymentMethod
o	Nhiệm vụ: Cung cấp thông tin của nhân viên và lựa chọn phương thức thanh toán.
PaymentMethod
o	Thuộc tính: methodType, address, bankName, accountNumber
o	Nhiệm vụ: Xác định phương thức thanh toán cho nhân viên (pick-up, mail, direct deposit).
PaymentService
o	Nhiệm vụ: Xử lý các yêu cầu liên quan đến thanh toán và lưu trữ thông tin phương thức thanh toán.
Database
o	Nhiệm vụ: Lưu trữ và truy xuất thông tin về nhân viên và phương thức thanh toán.

Biểu đồ mô tả của các lớp phân tích 
![Diagram](https://www.planttext.com/api/plantuml/png/X99BJiCm48RtFiKiGMekm09rqIwwe48g5vZO0qJ43pcJI17goRheaNe571FdOIgndDVtpp_sxNBTDeoUMrqBMMFJm5wxslP4y2q02g0nFEpW2Ih3CMbGKmXFx2lp4JCEUqs6NuW_hGgbrsKipcA4hzAZWex1M-yo92hbASoiaYMQh-CVTPJIjeQFhIx9pwLSzaI-g-IlCm3dhGpyrKeFizteTZDkbv2F0TxPQk5eXumbDWdgAVHHH-cA1_DkS-W0IVKur3g5JFSNcLkNsjCZ5SLpTklCwz0mYTsf_JkS38h9wGgv9QE6poF43m000F__0m00)

**4. Phân tích ca sử dụng Maintain Timecard**

Biểu đồ mô tả hành vi thông qua biểu đồ sequence cho ca sử dụng Maintain Timecard :
![Diagram](https://www.planttext.com/api/plantuml/png/R94nRiCm34LtdeB8tWjuA09N6RmLbNC0Lc9GeRPaKBGBdwr3ZzGhr4hg88sxyZz-FaZVdr_xh2GwzXsGqoHuw8SkpSmmBEFWma1HSTU6dXs9noOgouaSxv0ojit_c6MPmihOlumXfLVAbz3K0Ej5V7XS2Yiyb1FubaR9-97adJsqpJcq5JvBSfmpwYh4KMM6rXR0r1M-i4hWYT6D8aju9S7KQudbwBVvfQCOc927ZkOjid4z3fwKRpgkefOclkykVdSR62BwtnUvCNXAyHIan_5CmtuHBby4y0C00F__0m00)

Employee (Nhân viên)

o	Thuộc tính: employeeID, name, timecards

o	Nhiệm vụ: Quản lý thông tin của nhân viên và các thẻ thời gian của họ.

Timecard (Thẻ thời gian)

o	Thuộc tính: timecardID, startDate, endDate, hoursWorked, chargeNumbers, status

o	Nhiệm vụ: Lưu trữ thông tin về số giờ làm việc của nhân viên trong một khoảng thời gian cụ thể.

ChargeNumber (Số dự án)

o	Thuộc tính: chargeNumberID, description

o	Nhiệm vụ: Định nghĩa các số dự án mà nhân viên có thể ghi nhận số giờ làm việc.

TimecardService (Dịch vụ thẻ thời gian)

o	Nhiệm vụ: Xử lý các yêu cầu liên quan đến thẻ thời gian, như tạo mới, cập nhật và xác nhận thẻ thời gian.

Database (Cơ sở dữ liệu)

o	Nhiệm vụ: Lưu trữ và truy xuất thông tin thẻ thời gian, số dự án và nhân viên.

