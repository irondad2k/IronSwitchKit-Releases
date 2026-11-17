# IronSwitchKit

**Quản lý tài khoản, chuyển phiên và theo dõi hạn mức Codex Desktop cùng Antigravity trên Windows.**

IronSwitchKit tập hợp các tài khoản đã lưu vào một giao diện desktop, giúp bạn chọn phiên cần dùng, xem quota và theo dõi thông tin qua cửa sổ mini hoặc khay hệ thống.

**[Tải ứng dụng trong Releases](https://github.com/irondad2k/IronSwitchKit-Releases/releases)** · **[Báo lỗi / góp ý](https://github.com/irondad2k/IronSwitchKit-Releases/issues)**

Đây là repo phân phối bộ cài, bản portable và ghi chú phát hành. Mã nguồn ứng dụng được quản lý riêng.

## Tính năng

| Tính năng | Bạn có thể làm gì? |
| --- | --- |
| Quản lý tài khoản | Lưu nhiều tài khoản Codex Desktop và Antigravity; đổi nhãn để dễ phân biệt. |
| Thêm tài khoản linh hoạt | Dùng OAuth, nhập file JSON, dán JSON hoặc lưu phiên hiện tại. |
| Chuyển phiên | Chọn tài khoản đã lưu và thực hiện theo hộp thoại xác nhận chuyển. |
| Theo dõi quota | Xem hạn mức còn lại, mốc reset và trạng thái dữ liệu; kiểm tra từng tài khoản khi cần. |
| Cửa sổ mini & tray | Theo dõi nhanh khi cửa sổ chính đang ẩn; tùy chỉnh kiểu hiển thị và chế độ chạy nền. |
| Cảnh báo hạn mức | Đặt ngưỡng cảnh báo và nơi hiển thị trong Cài đặt. |
| Nhập / xuất JSON | Nhập tài khoản từ JSON được hỗ trợ hoặc xuất tài khoản để tự lưu trữ. |
| Thông báo cập nhật | Kiểm tra phiên bản mới, xem thông báo, nhắc sau hoặc bỏ qua một phiên bản. |

Thông tin quota và gói phụ thuộc vào dữ liệu nhà cung cấp trả về. Khi thiếu dữ liệu hoặc dữ liệu đã cũ, app hiển thị trạng thái tương ứng. App không tự chuyển tài khoản theo quota.

## Chọn gói tải xuống

Vào [Releases](https://github.com/irondad2k/IronSwitchKit-Releases/releases), chọn bản stable đã được phát hành và mở phần **Assets**.

| Tệp | Dùng khi nào? |
| --- | --- |
| `IronSwitchKit-Setup-<version>-x64.exe` | Cài đặt hoặc nâng cấp ứng dụng bằng bộ cài Windows. |
| `IronSwitchKit-<version>-win-x64.zip` | Dùng bản portable: giải nén đầy đủ rồi chạy `IronSwitchKit.exe`. |
| `SHA256SUMS.txt` | Đối chiếu SHA256 của các tệp tải xuống. |
| `IronSwitchKit-manifest.json` | Xem phiên bản, kích thước và hash của các gói phát hành. |

Các mục **Source code (zip)** và **Source code (tar.gz)** do GitHub tạo từ repo này không phải gói ứng dụng. Hãy chọn file Setup hoặc ZIP portable có tên IronSwitchKit.

## Yêu cầu

- Windows x64.
- Microsoft Edge WebView2 Runtime. Bộ cài kiểm tra runtime và tải/cài từ Microsoft nếu máy chưa có; bước này cần Internet.
- Kết nối Internet cho đăng nhập OAuth, truy vấn quota và kiểm tra phiên bản.
- Codex Desktop hoặc Antigravity được cài đặt nếu bạn sử dụng chức năng chuyển phiên cho ứng dụng tương ứng.

Gói phát hành đã kèm .NET runtime; không cần cài .NET SDK riêng. Với portable, cần chuẩn bị WebView2 Runtime trên máy.

## Cài đặt

### Bộ cài Windows

1. Tải file `IronSwitchKit-Setup-<version>-x64.exe` trong Assets.
2. Kiểm tra hash nếu cần bằng `SHA256SUMS.txt` của cùng bản phát hành.
3. Chạy bộ cài và chọn thư mục ứng dụng.
4. Mở IronSwitchKit sau khi cài xong.

Không chọn `%LOCALAPPDATA%\IronSwitchKit` làm thư mục cài ứng dụng: đây là nơi chứa dữ liệu của bạn.

### Bản portable

1. Tải file `IronSwitchKit-<version>-win-x64.zip`.
2. Giải nén **toàn bộ** ZIP vào một thư mục app riêng.
3. Chạy `IronSwitchKit.exe` trong thư mục đã giải nén.

Giữ các tệp và thư mục đi kèm cùng executable; không chỉ chép riêng file `.exe`. Bản portable vẫn dùng thư mục dữ liệu theo user Windows như bản cài đặt.

## Bắt đầu sử dụng

1. Mở trang **Codex Desktop** hoặc **Antigravity App**.
2. Chọn **Thêm tài khoản** và phương thức bạn muốn dùng: OAuth, nhập file JSON, dán JSON hoặc lưu phiên hiện tại.
3. Hoàn tất các bước hiển thị và kiểm tra tài khoản trong danh sách.
4. Xem quota trên thẻ tài khoản hoặc chủ động bấm kiểm tra khi cần.
5. Khi chuyển phiên, lưu công việc đang mở và làm theo hộp thoại xác nhận đóng ứng dụng đích.

Bạn có thể thay đổi chủ đề, cửa sổ mini, lịch quota, cảnh báo và cách đóng cửa sổ trong **Cài đặt**. Các thay đổi cần bấm **Lưu thiết lập** mới có hiệu lực.

Một số phương thức thêm tài khoản có điều kiện riêng; ví dụ luồng OAuth Codex có thể yêu cầu chọn Codex CLI. Bạn cũng có thể dùng một phương thức JSON hoặc lưu phiên phù hợp với tài khoản đang có.

## Nâng cấp và kiểm tra phiên bản

- App tự kiểm tra bản stable khi đến lịch, với chu kỳ 12 giờ khi đang chạy. Có thể bật/tắt trong **Cài đặt → Phiên bản & cập nhật**.
- Bạn luôn có thể bấm **Kiểm tra cập nhật**, hoặc dùng menu kiểm tra phiên bản trong khay hệ thống.
- Khi có bản mới, chọn **Xem bản cập nhật**, **Nhắc sau 24 giờ** hoặc **Bỏ qua phiên bản này**. Có thể hiện lại thông báo trong Cài đặt.
- Thông báo khay phụ thuộc thiết lập thông báo của Windows; thông tin cập nhật vẫn xem được trong app.

Để nâng cấp:

1. Tải bộ cài hoặc portable của bản mới từ Releases.
2. Chọn **Thoát hoàn toàn** trong menu khay hệ thống của IronSwitchKit. Chỉ đóng cửa sổ chính có thể vẫn để app chạy nền.
3. Với installer, cài vào thư mục app hiện có. Với portable, giải nén toàn bộ bản mới vào thư mục app riêng.
4. Mở lại IronSwitchKit.

Tài khoản và cài đặt được lưu theo user Windows tại `%LOCALAPPDATA%\IronSwitchKit`. Giữ nguyên thư mục này khi nâng cấp. App chỉ kiểm tra và thông báo; bạn chủ động tải và cài bản mới.

Chỉ các release đã được Publish mới xuất hiện công khai và được app dùng để kiểm tra phiên bản.

## Dữ liệu tài khoản

Thông tin đăng nhập đã lưu được bảo vệ cục bộ bằng Windows DPAPI, gắn với user Windows đang sử dụng. Bản portable và bản cài đặt dùng chung dữ liệu theo user trên máy.

**File xuất JSON chứa thông tin đăng nhập dạng rõ.** Chỉ lưu ở nơi bạn kiểm soát; không gửi file này, `auth.json`, token hoặc nội dung đăng nhập vào Issues hay ảnh chụp màn hình.

## Kiểm tra SHA256

Tải `SHA256SUMS.txt` từ cùng bản phát hành, rồi tính hash của file đã tải bằng PowerShell. Ví dụ với bản 0.12.1:

```powershell
Get-FileHash .\IronSwitchKit-Setup-0.12.1-x64.exe -Algorithm SHA256
```

Đối chiếu kết quả với đúng tên file trong `SHA256SUMS.txt`. Các bản hiện tại chưa ký Authenticode; checksum dùng để kiểm tra tính toàn vẹn, không thay thế chữ ký xác minh nhà phát hành.

## Báo lỗi và góp ý

Tạo [Issue](https://github.com/irondad2k/IronSwitchKit-Releases/issues) kèm:

- Phiên bản IronSwitchKit và Windows; đang dùng installer hay portable.
- Ứng dụng liên quan: Codex Desktop hay Antigravity.
- Các bước tái hiện, kết quả mong đợi và kết quả thực tế.
- Ảnh chụp thông báo lỗi đã che thông tin cá nhân và đăng nhập.

Không cần tài khoản GitHub để tải một release công khai hoặc kiểm tra phiên bản trong app.

---

Phát triển bởi **irondad2k**.
