## Hướng dẫn sử dụng Adflex Publisher
### Lấy đường dẫn API 
Trước tiên bạn cần có một tài khoản trên [https://pub.adflex.vn/](https://pub.adflex.vn/), sau khi đăng nhập, di chuyển đến menu API để lấy đường dẫn API của bạn.
## Sử dụng API
Bạn có thể dùng bất kỳ ngôn ngữ lập trình nào để gọi đến đường dẫn API này, hệ thống sẽ trả về một danh sách các Offer. Bạn có thể đưa thêm một số tham số để lọc lấy các Offer theo ý muốn

Các tham số lọc:
1. type: Lọc theo loại Offer
2. geo: Lọc theo Geo của Offer 
3. platform: Lọc theo Platform của Offer

### Lọc theo Type
Giá trị có thể truyền lên:
1. cpi: Dùng để lấy ra các Offer loại CPI 
2. cpa: Dùng để lấy ra các Offer loại CPA 
3. all: Không phân biệt loại Offer

Nếu bạn không truyền tham số **type**,hệ thống mặc định trả về tất cả các loại Offer

Đường dẫn ví dụ:

`https://api.adflex.link/v1/ywKwMrw_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?type=cpa`
### Lọc theo Geo
Giá trị có thể truyền lên:
1. **auto**: Tự động detect vị trí của người dùng và trả về các Offer tương ứng
2. **vn**: Việt Nam
3. **id**: Indonesia
4. **th**: Thái Lan 
5. **my**: Myanmar 
6. **br**: Brazil 
7. **in**: Ấn Độ 
8. **other**: Ngoại trừ các nước trên 
9. **all**: Không phân biệt GEO của các Offer 

**Chú ý:** Hệ thống nhận biết vị trí của người dùng thông qua IP, giá trị **auto** chỉ có giá trị nếu bạn dùng Javascript hoặc jQuery để gọi lên API. Nếu bạn dùng PHP hay JAVA thì vị trí hệ thống nhận được sẽ là vị trí server web của bạn

Nếu bạn không truyền lên tham số **geo**, hệ thống mặc định nhận **geo=auto**

Đường dẫn ví dụ:

`https://api.adflex.link/v1/ywKwMrw_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?type=cpa&**geo=vn**`
