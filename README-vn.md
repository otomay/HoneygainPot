<h1 align="center">Honeygain Pot</h1>
<h4 align="center">🐝Một con bot giúp bạn nhận lucky pot của Honeygain mỗi ngày🍯</h4>
<h4 align="center">Dưới sự hỗ trợ của GitHub Actions và Python</h4>
<p align="center">
<img src="https://img.shields.io/github/forks/gorouflex/HoneygainPot?style=flat">
<img src="https://img.shields.io/github/stars/gorouflex/HoneygainPot?style=flat">
<img src="https://img.shields.io/github/contributors/gorouflex/HoneygainPot?style=flat">
<p align="center">
<img alt="CodeQL status" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/codeql.yml/badge.svg">
<img alt="Daily trigger status" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/daily.yml/badge.svg">
<img alt="Manual trigger status" src="https://github.com/gorouflex/HoneygainPot/actions/workflows/manual.yml/badge.svg"> (*)
<p align="center">
  <a href="https://github.com/gorouflex/HoneygainPot/">English 🇺🇸</a>
  •
  <a href="README-vn.md">Tiếng Việt 🇻🇳</a>
<p align="center">
  <a href="Debug.md">Sửa các lỗi thường gặp</a>     
  •
  <a href="#tính-năng">Tính năng</a>
  •
  <a href="#cách-sử-dụng">Cách sử dụng</a>
  •
  <a href="#xem-trước">Xem trước</a>
  •
  <a href="FAQ.md">FAQ</a>  
</p>
<p align="left">
<img src="Img/Logo.png"               
     width="170" 
     height="170"></p>

  ### [Honeygain](https://r.honeygain.me/BADBO762DE)  là một nền tảng trực tuyến sử dụng các thiết bị mạng của bạn như một cánh cổng để giúp các nhà doanh nghiệp hay các nhà phân tích dữ liệu để thực hiện các chiến dịch SEO, nghiên cứu thị trường, bảo vệ thương hiệu....

> [!WARNING]
> - Script/Bot này **KHÔNG** có liên kết hay được xác nhận bởi Honeygain
> - **Tôi GorouFlex và MrLolf** **không có trách nhiệm** cho bất kỳ hậu quả mà có thể phát sinh trong quá trình dùng Script/Bot này
> - Nếu Honeygain muốn chúng tôi xoá con bot này thì chúng tôi sẽ làm

> [!NOTE]
> - Luôn cập nhật repo của các bạn theo repo gốc này để nhận được những bản cập nhật và vá lỗi mới nhất, và tôi GorouFlex sẽ không hỗ trợ nếu phát hiện repo của bạn đã lỗi thời và không được cập nhật theo repo chính.
> - Nếu bạn gặp lỗi khi sử dụng GitHub Actions, hãy kham khảo lỗi tại [Debug.md](Debug.md).
> - (*) Không được fork repo nếu bạn thấy cả 2 ( không phải chỉ có 1 và không bao gồm cả CodeQL ) trạng thái của GitHub Actions đều chuyển sang đỏ, hãy chờ cho đến khi 1 trong 2 hoặc cả 2 chuyển sang màu xanh thì có thể fork.
> - 'Daily claim' sẽ luôn luôn tự động chạy vào lúc 14:00 giờ UTC +0 tức là 9:00 tối theo giờ UTC +7, nếu muốn chỉnh thì tham khảo tại [đây](https://github.com/gorouflex/HoneygainPot/blob/main/README-vn.md#l%C3%A0m-th%E1%BA%BF-n%C3%A0o-%C4%91%E1%BB%83-ch%E1%BB%89nh-l%E1%BA%A1i-th%E1%BB%9Di-gian-t%E1%BB%B1-%C4%91%E1%BB%99ng-ch%E1%BA%A1y-m%E1%BB%97i-ng%C3%A0y).
> <img src="https://i.imgur.com/htGeFlY.jpg">
  
# Tính năng

- Giúp bạn nhận lucky pot của Honeygain mỗi ngày mà không cần treo máy với sự hỗ trợ của GitHub Actions, tăng thêm thu nhập cho bạn🔥
- Kiểm tra được số dư tài khoản Honeygain của bạn.

# Cách sử dụng

  1. [Fork repo này](https://github.com/gorouflex/HoneygainPot/fork)  
  2. Đến repo mà bạn đã fork
  3. Vào `Settings > Secrets and Variables > Actions`, và ấn nút `New Repository secret`
  4. Đặt tên secrets đầu tiên tên là `MAIL_JWD` và điền mail Honeygain của bạn vào, sau đó tạo thêm secrets thứ 2 tên là `PASS_JWD` rồi nhập pass của bạn vào
  5. Trở lại repo của bạn đã fork, vào Actions trên thanh công cụ repo rồi ấn `I understand my workflows, go ahead and enable them`

![GitSettings](https://github.com/gorouflex/HoneygainPot/assets/98001973/d8d33621-5717-488d-9a80-6db395c8ac9d)

## Làm thế nào để chỉnh lại thời gian tự động chạy mỗi ngày?

> [!IMPORTANT]
File tự động chạy mỗi ngày ở ( mặc định là 14:00 UTC +0 ): `.github/workflows/daily.yml`

GitHub sử dụng giờ UTC quốc tế (UTC +0) để đặt lịch trình chạy GitHub Actions, nên chúng ta phải đổi sang múi giờ của mình

Ví dụ: Nếu tôi muốn đặt lịch để cho GitHub Actions chạy vào lúc 9:00 tối ( múi giờ UTC +7) thì tôi phải chuyển thành là 2 giờ chiều theo múi giờ UTC +0, vì 2+7 là 9!
Lưu ý là phải sử dụng định dạng 24 giờ để đặt lịch: 
```
name: Daily claim
on:
  schedule:
    - cron: '0 14 * * *' # <- UTC Time
```
Nên nếu tôi muốn đặt vào lúc 5h sáng theo giờ UTC +7 thì tôi phải đặt thành 10h tối theo giờ UTC +0, và phải sử dụng định dạng 24 giờ

```
name: Daily claim
on:
  schedule:
    - cron: '0 22 * * *' # UTC Time
```

> [!NOTE]
> GitHub Actions có thể bị delay hơn so với giờ dự kiến đã đặt khoảng từ 3p đến 15p vì do nhu cầu chạy đang cao nên đừng lo lắng vì sao nó không chạy đúng giờ nhé!

# Xem trước

<p align="center">
  <img src="Img/preview (1).jpeg">
  <img src="Img/preview.jpeg">
</p>

## Cảm ơn
- [MrLolf](https://github.com/MrLoLf/) cho [HoneygainAutoClaim](https://github.com/MrLoLf/HoneygainAutoClaim)
- [rfoal](https://github.com/rfoel/) x [duolingo](https://github.com/rfoel/duolingo) cho ý tưởng
