# Subdomain

Subject: Software Design

# Subdomain

> ***Problem-space concept***
> 

## Khi Domain vượt ngoài tầm kiểm soát

Với một hệ thống lớn như (Netflix chẳng hạn), việc Domain Model trở nên cực kì phực tạp là chuyển hiển nhiên. Và dù cho có nổ lực refactor, có chắt lọc tới đâu thì Model cũng vẫn sẽ phức tạp

Lúc đó, ta cần phải cấu trúc lại Domain Model, với những Subdomain nhỏ hơn. Ta cần xác định được cái **Core**, là trái tim của Domain, là cái tạo nên sự khác biệt của hệ thông với những hệ thống khác. Cùng với **Core**, ta phải phân biệt nó với các Subdomain khác, tránh các sự phức tạp, rối rắm không cần thiết. 

Vậy ngoài **Core** ra, chúng ta sẽ có những Subdomain nào? Xác định sẽ cho ta:

1. Core Subdomain
2. Generic Subdomain
3. Supporting Subdomain

Hãy cùng đi vào 3 loại Subdomain này

## Core Domain

Trong một hệ thống, để có thể trở nên khác biệt, có thể kiếm được lợi nhuận, ta cần phải xác định được thành phần chính của hệ thống đó. Cái mà có thể bao hàm những Business Logics trực tiếp sinh lời cho doanh nghiệp và thể hiện được sự khác biệt của hệ thống cùng với đó trực tiếp đóng góp vào sự cạnh tranh. Đó chính là Core Subdomain. 

Trong quá trình phân tích Domain và Design hệ thống, nó nên dần được hình thành. Qua các công đoạn xác định model, ta nên nhìn ra được những Components nào có thể đóng vai trò là lực lượng nòng cốt của hệ thống và đưa vào Module riêng. Với những Objects khác cũng vậy sẽ có những Module khác chứa những Objects đó. 

Còn khi bước tới quá trình implementation, Core Subdomain nên được giao cho một người Developer trình độ cao. Họ thường sẽ không quá mặn mà với Business Logic, mà thứ hấp dẫn họ sẽ phần infrastructure như những công nghệ mới hay ngôn ngữ mới.

Một cây làm chẳng nên lon, 3 cây chụp lại ra Domain Model

### Generic Domain & Supporting Domain

1. Generic Domain
    
    Hmm, mình cũng không biết nói như nào về cái này. Nó đơn giản là “lời giải có sẵn cho một vấn đề”. Mình có cần nó không? Ye sure. Nhưng nó có phải Central không? Nah.
    
    Các bạn có thể hình dung nó như việc xuất hóa đơn, xử lý payment, hay authentication. Chúng ta có cần, và những thứ này ngoài kia có rất nhiều solution cho nó rồi. Tóm lại nó chỉ là common functionalities
    
2. Supporting Domain
    
    Được giới thiệu trong cuốn **https://www.google.com.vn/books/edition/Implementing_Domain_Driven_Design/X7DpD5g3VP8C?hl=en&gbpv=0 by Vaughn Vernon.** Ban đầu chỉ có hai Domain là Core và Generic
    
    Ông đã mở rộng hơn khái niệm về Subdomain của **Erec Evans**, với Supporting Domain là:
    
    > The business creates a **Supporting Subdomain** because ***it is somewhat specialized***. Being Supporting or Generic doesn’t mean unimportant. These kinds of Subdomains are ***important to the success of the business***, yet there is ***no need for the business to excel in these areas***.
    > 
    
    Supporting Subdomain được doanh nghiệp implement bởi vì nó không có sẵn ở ngoài, và nó cần để Core Subdomain hoạt động ổn định cũng hệ thống.
    

## Take-away

- Core Subdomain: Trái tim của hệ thống, trực tiếp tạo nên sự khác biệt và đóng góp và sự cạnh tranh của doanh nghiệp.
- Generic Subdomain: Có quan trọng, không central, có sẵn solution ⇒ Common functionalities.
- Supporting Subdomain: Core Subdomain vẫn cần những Business Logic khác để hoạt động hiệu quả, và nó ở đây. Có quan trọng, không central, không có sẵn solutions ⇒ Doanh nghiệp phải tự làm nhưng không cần quả ‘wow’.