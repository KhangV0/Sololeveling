# Đề xuất chức năng cho Solo Leveling Quest System

Mục tiêu: biến ứng dụng thành một game rèn luyện có động lực lâu dài, dễ bắt đầu, thú vị khi quay lại mỗi ngày và vẫn chạy hoàn toàn trên trình duyệt/GitHub Pages.

## Ưu tiên P0: Nên làm trước

### 1. Hồ sơ người chơi mới

Khi bắt đầu, người chơi chọn:

- Mức hiện tại: chưa từng tập, thỉnh thoảng tập, đã có nền tảng.
- Thời gian mỗi buổi: 5, 10, 20 hoặc 30 phút.
- Mức tác động: không nhảy, ít tác động hoặc bình thường.
- Vùng cần tránh: cổ tay, đầu gối, lưng, vai hoặc không có.

Hệ thống dùng lựa chọn này để tạo quest phù hợp, thay vì đưa cùng một bài cho tất cả người chơi.

### 2. Quest có thể thay thế

Mỗi nhiệm vụ có nút **Đổi bài**. Ví dụ:

- Chống đẩy tường → chống đẩy bàn → chống đẩy gối.
- Squat ghế → squat thường → split squat có điểm tựa.
- Jumping jack → bước ngang → shadow boxing.
- Plank gối → dead bug → bird-dog.

Đổi bài không làm mất XP hoặc streak. Đây là tính năng quan trọng để người chơi không bị kẹt bởi đau nhẹ, không gian hẹp hoặc sở thích cá nhân.

### 3. Chế độ ngày hôm nay

Mỗi ngày hiển thị một mục tiêu rõ ràng:

- Thời lượng dự kiến.
- Số bài cần hoàn thành.
- Mức độ: nhẹ, vừa hoặc thử thách.
- Lý do bài tập được chọn.
- Nút hoàn thành nhanh cho người bận.

Trong 14 ngày đầu, chỉ cần hoàn thành 1 nhiệm vụ chính để duy trì thói quen.

### 4. Ngày hồi phục chủ động

Người chơi có thể chọn:

- Giãn cơ 5 phút.
- Thở chậm 3 phút.
- Đi lại nhẹ trong nhà.
- Nghỉ hoàn toàn nếu cơ thể mệt.

Ngày hồi phục hợp lệ giữ streak nhưng không cộng stat lớn. Hệ thống không nên khiến người chơi cảm thấy có lỗi khi nghỉ đúng lúc.

### 5. Thang RPE sau buổi tập

Sau mỗi quest, hỏi: "Mức gắng sức của bạn là bao nhiêu?"

- 1–3: quá nhẹ, có thể tăng rất ít.
- 4–6: phù hợp, giữ mức hiện tại.
- 7–8: nặng, không tăng vào ngày kế tiếp.
- 9–10: quá sức, đề xuất giảm độ khó và nghỉ hồi phục.

RPE được lưu trong LocalStorage và dùng để điều chỉnh quest tiếp theo.

## Ưu tiên P1: Tăng cảm giác game

### 6. Năng lượng và hồi phục

Thêm thanh năng lượng bên cạnh XP:

- Quest nhẹ tiêu hao ít năng lượng.
- Quest nặng tiêu hao nhiều năng lượng.
- Năng lượng hồi phục theo thời gian và ngày nghỉ.
- Không thể spam quest để lên cấp quá nhanh.

Năng lượng chỉ là cơ chế game, không được dùng để khuyến khích người chơi tập khi đang đau hoặc kiệt sức.

### 7. Nhiệm vụ combo

Khi hoàn thành nhiều ngày liên tiếp, mở combo nhỏ:

- 3 ngày: combo khởi động.
- 7 ngày: combo nền tảng.
- 14 ngày: combo ổn định.
- 30 ngày: combo kỷ luật.

Combo nên thưởng cosmetic, XP nhỏ hoặc hiệu ứng giao diện, không nên tăng khối lượng tập quá nhanh.

### 8. Thành tựu và danh hiệu

Danh sách đề xuất:

- Bước đầu: hoàn thành quest đầu tiên.
- Không bỏ cuộc: 3 ngày liên tiếp.
- Đều đặn: 7 ngày.
- Nền tảng vững: 30 ngày.
- Người xây thói quen: 90 ngày.
- Nhật ký sống: 365 ngày.
- Người trở lại: quay lại sau một lần nghỉ.
- Không cần hoàn hảo: hoàn thành ngày hồi phục đúng lúc.
- Chủ nhà: hoàn thành 100 quest tại nhà.

### 9. Sự kiện ngẫu nhiên tích cực

Mỗi ngày có thể xuất hiện một sự kiện nhỏ:

- **Cửa sổ cơ hội:** quest hôm nay được giảm độ khó.
- **Mạch năng lượng:** hoàn thành thêm một bài nhẹ nhận cosmetic.
- **Ngày cân bằng:** ngày hồi phục được cộng bonus streak.
- **Thử thách bí mật:** một quest tùy chọn trong 3 phút.

Sự kiện chỉ nên tạo bất ngờ vui vẻ, không phạt người chơi vì không tham gia.

### 10. Rương phần thưởng và bộ sưu tập

XP vẫn là phần thưởng chính. Ngoài ra mở khóa:

- Huy hiệu hồ sơ.
- Màu giao diện.
- Khung rank.
- Hiệu ứng âm thanh.
- Biểu tượng class.
- Chủ đề nền theo mốc streak.

Lưu toàn bộ collection ở client-side, không cần tài khoản.

### 11. Màn hình tổng kết sau buổi tập

Hiển thị ngắn gọn:

- Quest đã hoàn thành.
- XP nhận được.
- Chỉ số tăng.
- RPE hôm nay.
- Streak hiện tại.
- Gợi ý hồi phục cho ngày mai.

Màn hình này nên có cảm giác như kết thúc một nhiệm vụ trong game, nhưng không khoe thành tích quá mức.

## Ưu tiên P2: Tăng chiều sâu dài hạn

### 12. Cây kỹ năng thực sự

Mỗi class có 3 nhánh:

- **Sát thủ:** nhanh nhẹn, cardio nhẹ, phản xạ.
- **Đỡ đòn:** chân, thân giữa, sức mạnh ổn định.
- **Quân chủ:** cân bằng, hồi phục và streak.

Mỗi node chỉ mở khi đạt level và duy trì một hành vi cụ thể, ví dụ hoàn thành 10 ngày hồi phục đúng lịch.

### 13. Story mode theo chương

Chia hành trình thành các chương:

1. Tín hiệu thức tỉnh.
2. Xây nền móng.
3. Kỷ luật trong căn phòng.
4. Vượt qua giới hạn an toàn.
5. Người giữ nhịp sống.

Mỗi chương có văn bản ngắn, boss quest và một phần thưởng cosmetic. Không nên dùng story để gây áp lực hoặc hạ thấp người chơi.

### 14. Boss có nhiều cách đánh bại

Một boss có thể hoàn thành bằng các lựa chọn tương đương:

- 3 buổi sức mạnh.
- Hoặc 2 buổi sức mạnh + 1 buổi cardio.
- Hoặc 4 buổi nhẹ + 2 ngày hồi phục.

Cách này khuyến khích linh hoạt và phù hợp với người có lịch sinh hoạt khác nhau.

### 15. Calendar heatmap nâng cấp

Mỗi ngày dùng màu theo loại hoạt động:

- Xanh lá: hoàn thành quest.
- Xanh dương: ngày hồi phục.
- Vàng: vượt mục tiêu.
- Tím nhạt: ngày thử bài mới.
- Xám: chưa ghi nhận.

Có bộ lọc theo 3 tháng, 1 năm và toàn bộ 1.000 ngày.

### 16. Báo cáo tuần

Mỗi cuối tuần tạo báo cáo:

- Số buổi hoàn thành.
- Tổng thời gian vận động.
- Bài thường chọn nhất.
- RPE trung bình.
- Số ngày hồi phục.
- Gợi ý cho tuần tiếp theo.

Báo cáo không nên chỉ dựa vào XP; sự đều đặn và hồi phục cũng phải được ghi nhận.

### 17. Nhật ký cảm nhận

Cho phép ghi nhanh:

- Năng lượng hôm nay: thấp, vừa, cao.
- Giấc ngủ: kém, ổn, tốt.
- Đau/mỏi: không có, nhẹ, cần theo dõi.
- Ghi chú tự do tối đa 200 ký tự.

Dữ liệu này giúp người chơi hiểu cơ thể, đồng thời làm biểu đồ tiến bộ có ý nghĩa hơn.

## Ưu tiên P3: Tính năng cộng đồng không cần backend

### 18. Thẻ thành tích chia sẻ

Tạo ảnh hoặc file JSON nhỏ gồm:

- Tên hiển thị do người chơi tự đặt.
- Streak.
- Số ngày tập.
- Class.
- Danh hiệu.
- Không chứa thông tin cá nhân nhạy cảm.

Người chơi tự chia sẻ qua mạng xã hội; app không cần máy chủ.

### 19. Mã thử thách offline

Tạo mã challenge từ seed và thời hạn:

- Người chơi nhập mã để nhận cùng một thử thách.
- Không cần đăng nhập hoặc đồng bộ server.
- Có thể dùng trong nhóm bạn hoặc cộng đồng nhỏ.

### 20. Chế độ hai người trên cùng thiết bị

Cho phép tạo nhiều profile cục bộ:

- Mỗi người có save riêng.
- Chuyển profile bằng mã PIN tùy chọn.
- Không trộn dữ liệu, streak và biểu đồ.

## Tính năng an toàn và khả năng tiếp cận

- Nút **Giảm độ khó** luôn hiện khi quest bắt đầu.
- Nút **Tôi đang đau** chuyển ngay sang ngày hồi phục và hiện lời nhắc dừng tập.
- Chế độ không nhảy, không chống tay và ít tác động.
- Hướng dẫn ngắn bằng chữ, không chỉ dùng màu.
- Điều khiển lớn cho điện thoại.
- Hỗ trợ `prefers-reduced-motion`.
- Không tự động phát âm thanh.
- Không dùng streak để trừng phạt người đã báo đau hoặc cần nghỉ.

## Kiến trúc dữ liệu đề xuất

```js
{
  profile: {
    name: "Hunter",
    experience: "beginner",
    minutesPerSession: 10,
    impact: "low",
    avoid: []
  },
  readiness: {
    energy: 6,
    sleep: "okay",
    soreness: "none",
    rpeAverage: 5
  },
  settings: {
    sound: true,
    reducedMotion: false,
    language: "vi"
  },
  achievements: [],
  cosmetics: [],
  recoveryDays: {},
  questSwaps: {},
  rpeLog: {},
  moodLog: {}
}
```

## Lộ trình triển khai gợi ý

### Bản 1.1

- Hồ sơ người mới.
- Quest thay thế.
- Ngày hồi phục.
- RPE sau buổi tập.
- Thành tựu cơ bản.

### Bản 1.2

- Năng lượng và hồi phục.
- Combo streak.
- Rương cosmetic.
- Báo cáo tuần.
- Nhật ký cảm nhận.

### Bản 2.0

- Story mode.
- Boss nhiều cách hoàn thành.
- Cây kỹ năng có node nội tại.
- Thẻ thành tích chia sẻ.
- Nhiều profile trên cùng thiết bị.

## Nguyên tắc sản phẩm

Game nên khiến người chơi muốn quay lại vì họ cảm thấy tiến bộ, không phải vì sợ bị phạt. Mỗi tính năng mới cần trả lời được ít nhất một câu hỏi:

1. Nó giúp người mới bắt đầu dễ hơn không?
2. Nó giúp duy trì thói quen lâu hơn không?
3. Nó có ghi nhận hồi phục và những ngày khó khăn không?
4. Nó có chạy được client-side trên GitHub Pages không?
5. Nó có làm tăng nguy cơ tập quá sức không?
