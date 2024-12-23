Thiết kế Hệ thống Con cho Ca Sử Dụng TimeCard

Bước 1: Phân phối hành vi của hệ thống con đến các phần tử

Thành phần và trách nhiệm:

TimecardForm:

Hiển thị thông tin thời gian làm việc hiện tại.

Nhận thông tin từ nhân viên về số giờ làm việc và ngày làm việc.

TimecardController:

Xử lý logic và liên kết giữa giao diện người dùng và cơ sở dữ liệu.

Cung cấp mã chi phí và lấy thông tin giờ làm việc hiện tại.

ProjectManagementDatabase:

Lưu trữ thông tin thời gian làm việc.
Timecard:

Đối tượng chứa thông tin về ngày và số giờ làm việc.

Bước 2: Tài liệu hóa các phần tử của hệ thống con

Dưới đây là danh sách các thành phần và phương thức tương ứng:

TimecardForm:

displayTimecard(): Hiển thị thông tin thời gian làm việc hiện tại.

saveTimecard(): Lưu thông tin giờ làm việc từ nhân viên.

TimecardController:

getChargeCodes(): Lấy mã chi phí để nhập số giờ.

getCurrentTimecard(): Trả về thông tin thời gian làm việc hiện tại.

updateTimecard(): Cập nhật thông tin giờ làm việc.

ProjectManagementDatabase:

saveTimecard(): Lưu thông tin thời gian vào cơ sở dữ liệu.

Timecard:

Chứa thuộc tính:

date: Ngày làm việc.

hours: Số giờ làm việc.

Bước 3: Mô tả các phụ thuộc của hệ thống con

Mối quan hệ giữa các thành phần:

Employee tương tác với TimecardForm để nhập thông tin thời gian làm việc.

TimecardForm gọi các phương thức trong TimecardController để lấy thông tin hoặc lưu dữ liệu.

TimecardController tương tác với:

ProjectManagementDatabase để lưu thông tin thời gian làm việc.

Timecard để cập nhật hoặc trả về thông tin giờ làm việc.

Bước 4: Kiểm tra (Checkpoints)

Họp thiết kế:

Tổ chức các buổi họp định kỳ với nhóm phát triển và khách hàng để xác minh thiết kế đáp ứng yêu cầu.

Kiểm thử đơn vị:

Thực hiện kiểm thử từng thành phần (TimecardForm, TimecardController, ProjectManagementDatabase) để đảm bảo hoạt động đúng.

Kiểm thử tích hợp:

Đảm bảo các mối quan hệ giữa các thành phần được triển khai đúng cách.

Thiết kế Hệ thống Con cho Ca Sử Dụng RunPayroll

Bước 1: Phân phối hành vi của hệ thống con đến các phần tử

Thành phần và trách nhiệm:

SystemClock:

Xác định xem có phải ngày trả lương không.

PayrollController:

Điều khiển logic chạy bảng lương và thực hiện các bước xử lý cho từng nhân viên.

BankSystem:

Thực hiện giao dịch ngân hàng (chuyển khoản lương).

Printer:

In phiếu lương cho nhân viên nhận lương bằng séc.

Timecard:

Lấy thông tin giờ làm việc của từng nhân viên.

PurchaseOrder:

Xử lý đơn đặt hàng liên quan đến lương.

Bước 2: Tài liệu hóa các phần tử của hệ thống con

SystemClock:

start(): Bắt đầu kiểm tra ngày trả lương.

isPayday(): Kiểm tra xem có phải ngày trả lương không.

PayrollController:

runPayroll(): Khởi chạy quy trình xử lý bảng lương.

getPayAmount(): Lấy số tiền phải trả cho nhân viên.

calculatePay(): Tính toán lương dựa trên thông tin giờ làm việc.

getPaymentMethod(): Lấy phương thức thanh toán của nhân viên (chuyển khoản/séc).

BankSystem:

getBankInfo(): Lấy thông tin ngân hàng của nhân viên.

sendBankTransaction(Paycheck, bankInfo): Chuyển khoản lương cho nhân viên.

Printer:

print(Paycheck): In phiếu lương cho nhân viên.

Timecard:

getTimecardInfo(): Lấy thông tin giờ làm việc của nhân viên.

Bước 3: Mô tả các phụ thuộc của hệ thống con

Mối quan hệ giữa các thành phần:

Employee khởi tạo quy trình trả lương thông qua PayrollController.

PayrollController kiểm tra ngày trả lương thông qua SystemClock.

Nếu là ngày trả lương:

Lấy thông tin giờ làm từ Timecard và tính lương.

Dựa trên phương thức thanh toán:

Nếu chuyển khoản: Thực hiện giao dịch thông qua BankSystem.

Nếu séc: In phiếu lương thông qua Printer.

Bước 4: Kiểm tra (Checkpoints)

Họp thiết kế:

Xác minh với các bên liên quan rằng hệ thống đáp ứng đầy đủ yêu cầu trả lương.

Kiểm thử đơn vị:

Kiểm thử độc lập từng thành phần:

PayrollController: Tính toán lương chính xác.

BankSystem: Xử lý giao dịch không lỗi.

Printer: In phiếu lương đúng định dạng.

Kiểm thử tích hợp: Đảm bảo các thành phần tương tác chính xác, quy trình không bị gián đoạn.
