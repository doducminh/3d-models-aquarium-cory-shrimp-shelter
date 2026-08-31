# Hang trú ẩn cho cá chuột — nửa hang áp mặt kính

Một **nửa hang động** áp thẳng vào mặt kính hồ. Mặt kính làm "thành thứ tư" của
hang, nên nhìn qua kính thấy đúng một mặt cắt hang động — và thấy con cá đang
làm gì bên trong. Toàn thân chôn dưới nền, chỉ **cửa hang và chỏm đá** nhô lên.

In bằng **PETG** (ngâm nước lâu dài; PLA thuỷ phân, giòn dần theo tháng).
**Không một cọng support** — đó là hệ quả hình học, không phải may: toàn vật mô
tả bằng hai trường độ sâu, mặt đá ngoài luôn hướng lên, còn trần hang dựng bằng
hàm khoảng cách nên nghiêng đúng 42° ở mọi chỗ.

> ## ⚠️ TẠM DỪNG IN — bộ STL hiện tại KHÔNG LẮP ĐƯỢC (31/08/2026)
>
> Đo lại trên chính sáu file trong repo này: **thân hang và khung chắn đất trong
> cùng một thư mục không lồng vào nhau được.** Thân hang của `goc-be-phai` chỉ lồng
> khít vào khung của `goc-be-trai` và ngược lại; với khung cùng thư mục thì hai vật
> nằm **hai đầu bể**. Bản `doc-kinh-truoc` gần đối xứng nên vẫn *gần* khớp, nhưng
> đo ra **208 mm³ đâm nhau** thay vì khe hở 2,0 mm như thiết kế.
>
> Nguyên nhân: hai bộ dựng xuất mesh theo hai quy ước tay ngược nhau, nên phép biến
> đổi duy nhất lồng được chúng là một phép **phản chiếu** — mà vật rắn thì không
> phản chiếu được. Mọi phép kiểm từng-chi-tiết đều sạch (kín khối, không support,
> gcode đúng) vì không phép nào chạy **hai chi tiết cùng lúc**.
>
> **Đừng in bộ này cho tới khi cảnh báo này biến mất.** Trang xem 3D bên dưới vẫn
> đúng — nó dựng hình bằng JS, không đọc STL.


**[Xem mô hình 3D →](viewer/index.html)**

---

## Chọn MỘT thư mục, in CẢ thư mục

Mỗi thư mục là một **bộ hoàn chỉnh**: một thân hang + một khung chắn đất.

| thư mục | đặt ở đâu | thân hang | khung chắn đất | cả bộ |
|---|---|---|---|---|
| **`doc-kinh-truoc/`** | giữa mặt kính trước | 114 × 70 × 48 mm · 41 g · 4h04 | 127 × 60 × 35 mm · 33 g · 3h20 | 74 g · 7h24 |
| **`goc-be-phai/`** | góc bể bên phải, nhìn được từ **hai** mặt kính | 100 × 71 × 48 mm · 33 g · 3h30 | 107 × 60 × 35 mm · 24 g · 2h17 | 57 g · 5h47 |
| **`goc-be-trai/`** | góc bể bên trái, nhìn được từ **hai** mặt kính | 100 × 71 × 48 mm · 33 g · 3h31 | 107 × 60 × 35 mm · 24 g · 2h17 | 57 g · 5h48 |

Bộ góc trái là **ảnh gương** của bộ góc phải — hộp bao trùng khớp tới 0,01 mm ở
cả ba chiều. Chọn theo góc bể bạn định đặt, đừng in cả hai rồi lật.

> **Đừng trộn các thư mục với nhau.** Lòng khung suy ra từ *vết quét* của chính cái thân
> hang cùng bộ; ghép khung của bộ này với thân của bộ kia thì khe nhấc sai và
> hang không rút lên được. Chép **cả thư mục** sang USB là chắc nhất.

`.gcode` slice sẵn cho Elegoo Neptune 4 nằm trong `gcode/<cùng tên thư mục>/`.
`.3mf` đi kèm để mở lại sửa tại chỗ nếu tới nơi mới phát hiện phải chỉnh.

---

## Hai bộ phận làm gì

**Thân hang** — cái hang. In **úp mặt áp kính xuống bàn**; lớp đầu chính là mặt
cắt hang mà người xem nhìn thấy, nên hiệu chuẩn z-offset trước khi in bản thật.

**Khung chắn đất** — một vách mỏng chôn sẵn trong nền, ôm dáng ngầm của hang. Nó
**ở lại** khi nhấc hang lên vệ sinh, nên hạt nền không đổ ập vào chỗ trống. In
**đứng**, vành chân là lớp đầu. Từ bản này nó gánh thêm việc thứ hai: làm **vách
sau** của hang, nhờ đó bụng hang thông suốt và chỗ nằm cho cá rộng gấp 2,6 lần.

### Vành chân là một MÁNG DẰN — phải đổ sỏi vào

Vành chân không phải một tấm phẳng: nó là **máng hở nóc, sâu 18 mm**, chạy dọc
mặt ngoài khung, có một hàng lỗ để nền hai bên nối liền qua.

Lý do nó tồn tại là một con số. Khung nặng 24 g khô, nhưng PETG chỉ nặng hơn nước
27% nên **dưới nước nó chỉ còn 5 gf** — bản đầu tiên đã đổ thật trong hồ, và tính
ra chỉ cần **0,36 gf** đẩy ngang là lật. Nới vành chân rộng ra không cứu được:
cánh tay đòn vốn đã đủ, thứ gần bằng không là **trọng lượng**. Đổ đầy sỏi/nền vào
máng thì lực giữ lên **13 gf**, gấp ba, và trọng tâm hạ từ 15,3 xuống 12,3 mm.

Máng nằm **hoàn toàn bên trong** hình bao cũ — bề sâu vẫn đúng 59,8 mm như bản đã
in vừa chỗ, không phải đo lại gì.

## Cài đặt in

Vòi **0,4** · lớp **0,2** · **PETG** · **không support** (đo được 0% trong cả sáu
file gcode) · **brim 5 mm** cho cả hai chi tiết — đã khai sẵn trong `.gcode`.

Brim không phải cho chắc ăn thừa. Thân hang có lớp đầu là một **vành rộng 9 mm,
chu vi ~330 mm**: nó không chênh vênh và không lật, nó **bong mép** — mà mép ấy
chính là mặt người xem nhìn vào. Khung thì là một bức tường cao gấp 12 lần bề dày,
dài hơn 200 mm, cong vênh theo chiều dài khi PETG co ngót.

Cả hai chi tiết **đã ở đúng tư thế in trong file** — đừng để slicer tự xoay, và
đừng in hai chi tiết cùng một tư thế.

## Lắp

1. **Rải một lớp nền mỏng xuống trước**, rồi mới đặt khung và ấn cho vành chân
   lún vào. Đặt khung lên mặt kính trơn thì nó chưa có gì giữ.
2. **Đổ sỏi/nền đầy máng dằn** ở vành chân — đây là bước dễ quên nhất và là bước
   quyết định khung có đứng vững không.
3. Lấp nền quanh khung, ngoài khung, cho ngập qua máng.
4. Thả **thân hang** thẳng từ trên xuống vào lòng khung — khe hở 2 mm, không cần lực.
5. Vun nền cho ngập tới chân cửa hang; ngưỡng cửa cao hơn mặt nền 6 mm nên hạt
   không tràn vào.

**Lúc nhấc hang ra vệ sinh:** giữ một tay lên mép khung, tay kia rút hang thẳng
lên. Ma sát khi hang trượt qua khe 2 mm là đủ để kéo theo cả cái khung.

Ngâm nước **48 giờ** xả mùi trước khi thả vào hồ đang có cá.

---

## Xem trước

`viewer/index.html` — mở thẳng bằng trình duyệt, không cần máy chủ web. Trang
dựng hình bằng JS nên chỉnh được kiểu hang, hướng cửa, cỡ in… và xem số đo đổi
theo ngay.

## Trạng thái

✅ **Đã in thật bộ `doc-kinh-truoc/` và bộ `goc-be-phai/`** — lắp vào hồ đạt, chủ
dự án nghiệm thu ổn. Đó là hai bộ đã đi hết vòng: thiết kế → in → ướm vào chỗ thật.

⚠️ **Khung của cả ba bộ đã được dựng lại** sau khi bản in đầu **đổ trong hồ**: vành
chân giờ là máng dằn (mục trên). Thân hang **không đổi một milimét nào** — file
`than-hang.stl` của bạn vẫn dùng được, chỉ cần in lại `khung-chan-dat.stl`.
Máng dằn thì mới, **chưa qua bản in thật**.

⚠️ Bộ `goc-be-trai/` **chưa in** — nhưng nó là ảnh gương đúng nghĩa của bộ góc
phải đã in đạt, dựng từ cùng bộ script, cùng cỡ, cùng seed.

Bảng số trong README này là số đo trên mô hình và trên gcode, không phải cân đo
vật in ra; lệch vài phần trăm khối lượng là bình thường.

---

## Bản quyền

Cả sáu file đều mang dấu **`doducminh`** khắc chìm trên vật. Trên thân hang
dấu nằm ở mặt áp kính và khắc **soi gương** — đọc đúng chiều khi nhìn từ ngoài
hồ vào.

Giấy phép: **CC BY-NC-SA 4.0** cho file thiết kế.
