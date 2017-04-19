## Hướng dẫn sử dụng Adflex Publisher
### Lấy đường dẫn API 
Trước tiên bạn cần có một tài khoản trên [https://pub.adflex.vn/](https://pub.adflex.vn/), sau khi đăng nhập, di chuyển đến menu API để lấy đường dẫn API của bạn.
## Sử dụng API
Bạn có thể dùng bất kỳ ngôn ngữ lập trình nào để gọi đến đường dẫn API này, hệ thống sẽ trả về một danh sách các Offer. Bạn có thể đưa thêm một số tham số để lọc lấy các Offer theo ý muốn.

Phương thức request hệ thống nhận: **GET**

Các tham số lọc:
1. type: Lọc theo loại Offer
2. geo: Lọc theo Geo của Offer 
3. platform: Lọc theo Platform của Offer

### Lọc theo Type
Giá trị có thể truyền lên:
1. cpi: Dùng để lấy ra các Offer loại CPI 
2. cpo: Dùng để lấy ra các Offer loại CPO 
3. all: Không phân biệt loại Offer

Nếu bạn không truyền tham số **type**,hệ thống mặc định trả về tất cả các loại Offer

Đường dẫn ví dụ:
`https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?type=cpo`

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
`https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?geo=vn`
### Lọc theo Platform
Giá trị có thể truyền lên:
1. **auto**: Tự động detect thiết bị của của người và trả về các Offer tương ứng
2. **ios**: iOS 
3. **android**: Android 
4. **all**: Không phân biệt thiết bị của người dùng 

**Chú ý:** Hệ thống nhận biết vị trí của người dùng thông qua User Agent, giá trị **auto** chỉ có giá trị nếu bạn dùng Javascript hoặc jQuery để gọi lên API. Nếu bạn dùng PHP hay JAVA thì bạn cần gửi User Agent của người dùng kèm theo request 

Nếu bạn không truyền lên tham số **platform**, hệ thống mặc định nhận **platform=auto**

Đường dẫn ví dụ:
`https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?platform=ios`

## Ví dụ đường dẫn API
- Lấy ra các Offer **loại CPA cho khu vực Thái Lan**
`https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?type=cpa&geo=th`
- Lấy ra các Offer **loại CPI cho khu vực Việt Nam và hệ điều hành Android**
`https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json?type=cpi&geo=th&platform=android`

## Ví dụ data trả về khi gọi đến API
```
{
  "status_code": 200,
  "meta": {
    "total": 2
  },
  "data": [
    {
      "id": "upsizevn",
      "name": "UpSize Vietnam",
      "type": "cpa",
      "traffic_type": "both",
      "categories": null,
      "tracking_link": "http://aff.mclick.mobi/upsizevn/hungnd4",
      "tracking_link_facebook": "http://hungnd4.etracking.link/upsizevn/hungnd4",
      "tracking_link_encrypted": "http://aff.mclick.mobi/v2/SHFzMAp3f3GyoLH0YJp0G7dYXBQIg_JugE_Ou0Thalg",
      "title": "UpSize VN",
      "description": "Ngày nay, rất nhiều chị em phụ nữ ao ước có được vòng một căng tròn, hoàn hảo. Đây là điều không lạ, khi đây chính là bộ phận thu hút ánh nhìn của cánh đàn ông. Và tôi đã đưa ra cho họ lời khuyên về sản phẩm Upsize\r\n\r\nNếu bạn dùng kem hàng ngày, kích cỡ vòng một sẽ nở nang hơn trong vòng 3-4 tuần, khuôn vòng một trở lên căng và chắc, làn da đàn hồi và mềm mịn hơn.\r\n\r\nSản phẩm trải qua những thử nghiệm lâm sàng được tiến hành bởi các chuyên gia của Tổ chức Y tế Thế giới tại 14 quốc gia trên toàn thế giới. Hàng nghìn phụ nữ đã thừa nhận tính hiệu quả của kem nâng vòng một này.",
      "images": {
        "750x1334": "http://img.adsoca.com/public/share/adflex/offers/banners/upsizevn/750x1334.jpg",
        "640x360": "http://img.adsoca.com/public/share/adflex/offers/banners/upsizevn/banner_upsizevn_640x360.jpg",
        "600x600": "http://img.adsoca.com/public/share/adflex/offers/banners/upsizevn/600x600.jpg",
        "600x480": "http://img.adsoca.com/public/share/adflex/offers/banners/upsizevn/600x480.jpg",
        "1200x628": "http://img.adsoca.com/public/share/adflex/offers/banners/upsizevn/1200x628.jpg",
        "480x250": "http://img.adsoca.com/public/share/adflex/offers/banners/upsizevn/480x250.jpg"
      },
      "icon": "http://cloudfront.adflex.vn/offers/icons/2017/01/1483601776_5182.png"
    },
    {
      "id": "greencoffevn",
      "name": "Green Coffee 3 (Vietnam)",
      "type": "cpa",
      "traffic_type": "both",
      "categories": null,
      "tracking_link": "http://aff.mclick.mobi/greencoffevn/hungnd4",
      "tracking_link_facebook": "http://hungnd4.etracking.link/greencoffevn/hungnd4",
      "tracking_link_encrypted": "http://aff.mclick.mobi/v2/eNRiULkSbzkdD5wVgNHbu925tYkXuq7jWlgKDfD_oJU",
      "title": "Green Coffee 3 VN",
      "description": "Green Coffee 3 VN",
      "images": {
        "1200x628": "http://img.adsoca.com/public/share/adflex/offers/banners/greencoffevn/1200x628.jpg",
        "750x1334": "http://img.adsoca.com/public/share/adflex/offers/banners/greencoffevn/750x1334.jpg",
        "640x360": "http://img.adsoca.com/public/share/adflex/offers/banners/greencoffevn/640x360.jpg",
        "600x600": "http://img.adsoca.com/public/share/adflex/offers/banners/greencoffevn/600x600.jpg",
        "600x480": "http://img.adsoca.com/public/share/adflex/offers/banners/greencoffevn/600x480.jpg"
      },
      "icon": "http://cloudfront.adflex.vn/offers/icons/2017/01/1484210566_4208.png"
    }
  ]
}
```
## Ví dụ sử dụng API 
Ví dụ sử dụng jQuery AJAX để gọi API lấy ra các Offer **loại CPA, khu vực tự động**

```
jQuery.ajax({
  url: "https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json",
  method: "GET",
  dataType: "JSON",
  data: {
    type: "cpa"
  },
  success: function (responseData) {
    var offerData = responseData.data;
    console.log(offerData);
  }
});
```

Ví dụ sử dụng PHP để gọi API lấy ra các Offer **loại CPI, khu vực Việt Nam, hệ điều hành iOS**
```
$APIURL = "https://api.adflex.link/v1/aWoIOz_WM1riG7ix2qrDNfb3rYL1B9xHyVKZ-o3Scc/offers.json";
$filters = array(
        "type" => "cpi",
        "geo" => "vn",
        "platform" => "ios",
);
$query_params = http_build_query($filters);
$ch = curl_init($APIURL . "?" . $query_params);
curl_setopt_array($ch, array(
        CURLOPT_RETURNTRANSFER => true,
        CURLOPT_SSL_VERIFYPEER => false,
        CURLOPT_HEADER => false,
));
$responseData = curl_exec($ch);
curl_close($ch);
$responseData = json_decode($responseData);
var_dump($responseData);
```

