# BBCode

**BBCode** là một [ngôn ngữ đánh dấu](https://en.wikipedia.org/wiki/Markup_language) được sử dụng trong diễn đàn osu! và rộng hơn là phần lớn các diễn đàn trên Internet. Dùng để tạo định dạng văn bản phong phú, nó được cấu thành từ các thẻ (tag) bao quanh văn bản để biểu thị định dạng, thuộc tính, nhúng nội dung, v.v. Nó được sử dụng ở nhiều nơi trên website osu!, như bài đăng diễn đàn, chữ ký, trang cá nhân người dùng và mô tả beatmap.

![Trình chỉnh sửa bài đăng diễn đàn với các nút của nó](img/editor.jpg?1 "Ô chỉnh sửa trong diễn đàn")

## Hành vi

Nhấn vào một nút markup mà không chọn đoạn văn bản nào sẽ tạo ra một cặp thẻ mở và đóng tại vị trí con trỏ trong trình chỉnh sửa bài viết. Nếu bôi đen văn bản trước khi nhấn nút markup, đoạn văn bản đó sẽ được bao quanh bởi các thẻ.

Người dùng muốn kết hợp nhiều định dạng lên cùng một đoạn văn bản có thể làm điều đó bằng cách lồng các thẻ BBCode vào nhau. Tuy nhiên, thứ tự và cách lồng các thẻ này **phải được tuân thủ** khi kết hợp. Nếu không, định dạng sẽ bị lỗi.

Ví dụ đúng và sai về việc lồng thẻ:

- `[centre][b]text[/b][/centre]` là đúng  
- `[b][centre]text[/b][/centre]` là sai  

## Thẻ

BBCode, giống như nhiều ngôn ngữ đánh dấu khác, định dạng văn bản bằng hệ thống thẻ, được biểu thị bằng dấu ngoặc vuông (`[]`). Các thẻ này được chia thành thẻ "mở" và "đóng", phân biệt bằng dấu gạch chéo (`/`). Cụ thể, thẻ đóng có dấu `/` ngay sau dấu ngoặc mở, còn thẻ mở thì không.

Cũng cần lưu ý rằng thẻ mở đôi khi chứa dấu bằng (`=`) để chỉ URL, kích thước font, và các yếu tố khác.

Các thẻ BBCode được hỗ trợ trên osu! được liệt kê và mô tả chi tiết bên dưới.

### In đậm
```
[b]text[/b]
```
Thẻ `[b]` dùng để nhấn mạnh mạnh mẽ văn bản bằng cách in đậm. In đậm trong BBCode không ảnh hưởng đến kích thước font.

Nút thanh công cụ: ![Nút Bold](img/bold.png "Bold")

### In nghiêng
```
[i]text[/i]
```
Thẻ `[i]` dùng để nhấn nhẹ văn bản bằng cách làm nghiêng (italic).

Nút thanh công cụ: ![Nút Italic](img/italic.png "Italic")

### Gạch chân
```
[u]text[/u]
```
Thẻ `[u]` dùng để nhấn mạnh bằng cách kẻ một đường ngang bên dưới văn bản. Đường này có thể bị ảnh hưởng bởi các thẻ khác như in đậm hoặc in nghiêng.

### Gạch ngang
```
[s]text[/s]
```
Thẻ `[s]` dùng để biểu thị việc xoá nội dung bằng cách kẻ ngang qua chữ. `[strike]` cũng là alias hợp lệ.

Nút thanh công cụ: ![Nút Strike](img/strike.png "Strikethrough")

### Màu sắc
```
[color=#HEXCODE]text[/color]
```
*Danh sách tên màu: xem [X11 color names](https://en.wikipedia.org/wiki/X11_color_names#Color_name_chart)*

Thẻ `[color]` dùng để tô màu văn bản. Nó sử dụng mã [HEX](https://en.wikipedia.org/wiki/Web_colors#Hex_triplet), hoặc tên màu HTML như "red", "green".

Không dùng dấu ngoặc kép (`"`). Nếu thiếu tham số hoặc dùng dấu `"`, thẻ sẽ không hoạt động.

### Kích thước chữ
```
[size=NUMBER]text[/size]
```
Thẻ `[size]` thay đổi kích thước chữ.

`NUMBER` là phần trăm so với mặc định (100%). Ví dụ:  
- `50` = nhỏ bằng nửa  
- `150` = lớn gấp rưỡi  

Chấp nhận:
- Số nguyên từ 30 đến 200  
- Từ khoá: "tiny", "small", "normal", "large" tương ứng 50, 85, 100, 150  

Sai giá trị nó sẽ không hiển thị.

Nút thanh công cụ: ![Font size](img/font-size.png "Font size")

### Spoiler

*Không nhầm với [Spoilerbox](#spoilerbox).*
```
[spoiler]text[/spoiler]
```
Ẩn nội dung bằng nền đen, chỉ hiện khi bôi đen. Dùng nhiều để tránh spoil phim, game, v.v.

### Hộp

*Không nhầm với [Spoilerbox](#spoilerbox).*
```
[box=NAME]
text
[/box]
```
Ẩn nội dung trong một khung có thể bấm mở ra (giống dropdown).

`NAME` là tiêu đề. Không có → box không có tiêu đề.

Dùng để giấu các đoạn text dài (FAQ, skin release,...).

Nút thanh công cụ: ![Box](img/spoilerbox.png "Box")

### Hộp Spoiler
```
[spoilerbox]text[/spoilerbox]
```
Giống hộp nhưng tên luôn là `SPOILER`.

### Trích dẫn
```
[quote="NAME"]
text
[/quote]
```
Hiển thị trích dẫn dạng block với indent, màu, đường kẻ hồng.  
`NAME` là tác giả (tuỳ chọn nhưng phải có dấu `" "`).

Nút reply: ![Quote reply](img/quotereply.png)

### Mã Inline
```
[c]text[/c]
```
Highlight mã inline bằng font monospace, có nền xám.

### Mã block
```
[code]
text
[/code]
```
Tạo mã block, giữ nguyên nội dung.

### Căn giữa
```
[centre]text[/centre]
```
Căn giữa nội dung.

### URL (Dường link)
```
[url=LINK]text[/url]
```
Tạo link nhấn được.

Phải có:
- LINK (không dấu `"`)  
- text hiển thị  

URL phải hợp lệ (`http://`, `https://`, `www.`)

Nút: ![URL](img/url.png "URL")

### Hồ sơ
```
[profile=userid]username[/profile]
```
Link tới hồ sơ osu! kèm thẻ khi di chuột vào.

Nên dùng cả ID với tên người dùng để tránh lỗi khi đổi tên.

### Danh sách
```
[list] LIST_NAME
[]item 1
[]item 2
[/list]
```
hoặc
```
[list=TYPE] LIST_NAME
[*]item 1
[/list]
```
- Mặc định: list chấm  
- Có `TYPE`: list số  
- `LIST_NAME`: tiêu đề  

Nút: ![List](img/list.png "List") ![Numbered](img/list-numbered.png "Numbered list")

### Email
```
[email=ADDRESS]text[/email]
```
Tạo đường dẫn email, nhấn để mở ứng dụng mail mặc định.

### Ảnh
```
[img]ADDRESS[/img]
```
Chèn ảnh từ link trực tiếp. Không dùng đường dẫn cục bộ như `C:\Users\Name\Pictures\image.jpg`

Lưu ý: Địa chỉ URL của trang web không giống với địa chỉ hình ảnh.

Để lấy địa chỉ hình ảnh, bạn cần truy cập trang web chứa hình ảnh đó, di chuột qua hình ảnh, nhấp chuột phải vào hình ảnh và chọn Copy image address. Sau đó, sao chép địa chỉ và dán vào giữa các thẻ.

Khuyên dùng [ImgBB](https://imgbb.com/).  
Imgur không còn hoạt động với osu!.

Nút: ![Image](img/image.png "Image")

### Imagemap
```
[imagemap]
IMAGE_URL
X Y WIDTH HEIGHT REDIRECT TITLE
[/imagemap]
```
Tạo vùng click trong ảnh.

### YouTube
```
[youtube]VIDEO_ID[/youtube]
```
Nhúng video YouTube (chỉ cần ID sau `v=`).

### Audio
```
[audio]URL[/audio]
```
Nhúng audio HTML5 từ URL.

### Heading (v1)
```
[heading]text[/heading]
```
Tạo tiêu đề to màu hồng.

Nút: ![Heading](img/heading.png "Heading")

### Notice
```
[notice]
text
[/notice]
```
Tạo khung thông báo lớn.

## Legacy

Các thẻ cũ không còn dùng:

### Google
```
[google]search query[/google]
```
### Lucky
```
[lucky]search query[/lucky]
```
### Heading (v2)
```
[text]
```
## Công cụ

| Tên | Người làm | Mô tả |
| :-: | :-: | :-- |
| [OSUWME](https://osu.ppy.sh/community/forums/topics/2029947) | ::{ flag=ID }:: [rezzvy](https://osu.ppy.sh/users/8804560) | Trình chỉnh sửa BBCode với tính năng xem trước thời gian thực cho hồ sơ osu! |
| [osu! BBCode Editor](https://github.com/NoelleTGS/osu-bbcode-editor) | ::{ flag=CA }:: [HonokaKousakaTV](https://osu.ppy.sh/users/18595366) | Trình chỉnh sửa BBCode với tính năng xem trước thời gian thực cho hồ sơ osu! (Đã lưu trữ) |
| [osu-gradient](https://osu-gradient.jgroup.top/) | ::{ flag=RU }:: [[_____________]](https://osu.ppy.sh/users/12036908) | Tạo hiệu ứng chuyển màu cho hồ sơ osu! |
| [osu-web enhanced](https://osu.ppy.sh/community/forums/topics/1361818) | ::{ flag=DE }:: [RockRoller](https://osu.ppy.sh/users/8388854) | Tiện ích mở rộng trình duyệt bổ sung thêm các nút BBCode và các tính năng khác cho trang web osu! |
| [textcolorizer](https://www.stuffbydavid.com/textcolorizer/) | david | 	Tô màu văn bản BBCode và HTML |

## Trivia

- Bài này dựa trên thread ["HOW TO: Forum BBCodes"](https://osu.ppy.sh/community/forums/topics/445599) của [Stefan](https://osu.ppy.sh/users/626907).
- Từng có bug cho phép text trong suốt bằng "transparent".
- Trước khi có `imagemap`, phải cắt ảnh để gắn nhiều link.

## Tham khảo

[^imgur-blocked-ip]: [Tweet của @ppy (2023-06-29)](https://twitter.com/ppy/status/1674439849749913602)
