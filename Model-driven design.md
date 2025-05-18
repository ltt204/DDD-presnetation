# Model-driven design [part-2]

Subject: Software Design

# Model-driven design [part-2]

Subject: Software Design

Phần trước:

[Model-driven design [Part-1]](https://www.notion.so/Model-driven-design-Part-1-1b373c4e46b8805692ddfa608e3b9649?pvs=21)

# Overview

Ở phần trước, chúng ta đã thấy được tầm quan trọng của việc tạo sự kết nối giữa các giai đoạn trong quá trình mô hình hóa domain. Trong phần này, chúng ta sẽ đi vào cấu trúc của Domain Model — hay còn gọi là **Structured Domain Model**, với các thành phần chính:

1. **Entity**
2. **Value Object**
3. **Domain Service**
4. **Aggregate**

## Entity

### Entity là gì?

Entity là object, ngoài các attributes mà object sở hữu, bạn thân nó được định danh (identity) và phân biệt với các entity khác.

Bạn đừng nhầm lẫn việc phân biệt objects thông qua địa chỉ vùng nhớ. Đúng là OOP thường sẽ lưu objects ở in-memory, mỗi instance sẽ được cấp một vùng nhớ với địa chỉ riêng biệt và phân biệt với các vùng nhớ khác. Nhưng với 2 objects, khác địa chỉ vùng nhớ, các attributes để như nhau, thì ta không thể biết được nó có thực sự là một hay không nếu đặt vào ngữ cảnh của Domain.

Bởi lẽ domain có thể sẽ không quan tâm tới “địa chỉ vùng nhớ” mà chúng ta nói. Nó quan tâm một đối tướng đó là ai, là cái gì, có những tính chất gì mà thôi.

Do đó việc, Identity của Entity giúp ta phân biệt được rõ ràng, với cùng attributes, cùng giá trị nhưng khác identity, thì ta có thể dễ dàng phân biệt các entity với nhau. Đặt biệt lưu ý, identity của entity sẽ không được thay đổi xuyên suốt lifecycle của nó.

### Cách nhận biết Entity?

Khi nhìn vào một domain, thấy một yếu tố nào đó, và bạn muốn biết nó là entity hay không? Hãy tự hỏi:

- Bản thân nó có cần được phân biệt với các đối tượng cùng loại?
- Nó có vòng đời riêng và tồn tại lâu dài trong hệ thống không?
- Nó có thể thay đổi thuộc tính nhưng vẫn được coi là cùng một đối tượng không?

Nếu các câu trả lời đều là có, đó chính là một Entity.

Ví dụ, xét ngữ cảnh domain của chúng ta là một shop bán sách, người dùng sẽ có thể

- Shop sẽ có nhiều khách hàng với nhu cầu khác nhàu
- Trong quá trình ứng dụng hoạt động người dùng luôn ở đó
- Và khi họ chuyển đi nơi khác, thì thứ duy nhất thay đổi là địa chỉ của họ

⇒ Khách hàng là một entity.

### Vì sao cần Entity?

Entity là nhân tố quan trọng khi modeling một domain. Khi nhìn vào domain mà mình sắp triển khai hệ thống, bạn phải nhìn được phần lõi của Domain đó. 

- Hệ thống tồn tại và trực tiếp sinh lời cho các doanh nghiệp là dựa vào những gì.
- Ai, cái gì là yếu tố làm cho hệ thống này tồn tại.

## Value object

![image.png](Model-driven%20design%20%5Bpart-2%5D%201c173c4e46b8807e938bef31b5719d4a/image.png)

### Value Object là gì?

Với entity, ta quan tâm “nó là cái gì” hay “người này là ai”, luôn có tính phân biệt giữa các object cùng loại với nhau. Ngoài ra, vẫn có những objects mà ta không quan tâm tới tính định danh mà chỉ quan tâm tới “giá trị thuộc tính” của nó. Tức nó không cần định danh (identity-less), mà chỉ cần attributes. Đó chính là **Value object**.

**Value Object** có một tính chất đặc biệt là **immutable**. Khi ta cần chỉnh sửa giá trị của một attribute thuộc VO đó, ta không thay đổi VO đó, mà ta sẽ tạo mới. Ví dụ, cũng là người mua sách đó, khi họ yêu cầu thay đổi địa chỉ giao hàng, ta không thay đổi trực tiếp mà tạo ra 1 Address mới.

### Cách nhận biết Value Object?

- Object không cần định danh (identity), chỉ cần quan tâm tới thuộc tính của nó
- Ta không cần theo dõi vòng đời của nó

Ví dụ: Địa chỉ của một user, nếu tồn tại 2 địa chỉ có thuộc tính giống nhau thì ta xem nó là một

⇒ Value object is sharable ⇒ Giải thích cho việc tại sao VO immutable

### Vì sao cần Value Object?

Với entity, hiểu đơn giản là một objects có identity. Ta phải tracking, theo dõi nó thương xuyên, và phải lưu trữ entity đó. Vậy thì có phải bất kì domain objects nào cũng là entity hay không?

Câu trả lời là có thể, nhưng không nên. Bởi lẽ việc xem tất cả mọi domain objects là entity sẽ làm tăng chi phí lưu trữ, giảm đi hiệu năng của ứng dụng với việc phải tracking mọi object.

Việc xác định được **Domain Objects**, và nhìn ra đâu là **Entity**, là cái mà chúng ta cần theo dõi vòng đời - và đầu là **Value Object**, thứ mà ta chỉ quan tâm tới thuộc tính của nó là điều cần thiết khi phát triển hệ thống.

## Domain Service

### Domain Service là gì?

Khi trao đổi với các domain expert để phân tích domain, một object thường được xác định khi ta nhận thấy nó có những attributes và kèm theo đó là một số **hành động** hoặc **logic** liên quan. Nhưng đôi lúc có những **hành động** và **logics** lại không thuộc về bất kì **Domain Objects** cụ thể nào. Bản thân nó đại diện cho một Business Rule, thì đó là Doman Service.

> Domain service represents for Business Policy (Rules or Logics)
> 

### Cách nhận biết Domain Service?

Domain Model được hình thành khi giao tiếp thông qua Ubiquitous Language. Với các động từ (verbs) ta có thể hình dung được các method cần thiết. Ví dụ, Khách hàng ‘mua’ sách và ‘thanh toán’ hóa đơn. Với ví dụ đó bạn có thể dễ dàng xác định được:

1. **Domain Objects**: Khách hàng, sách, hóa đơn là các Entity, với khái niệm Value object, từ hóa đơn ta có thể nhìn ra các order item…
2. **Service**: **Mua** và **thanh toán**

Services bản thân nó không có state (trạng thái) bởi lẽ nó không hề có attributes, chỉ đơn thuần là một Interface cung cấp các methods.

Với ví dụ trên, có thể thấy hành động ‘mua’ liên quan tới khách hàng, sách, và khi mua sẽ sinh ra hóa đơn, với hóa đơn đó người dùng sẽ phải thanh toán. Bạn có thể thấy các action mà service chứa đụng thường có phạm vi hoạt động liên objects.

### Vì sao cần Domain service?

- Các methods được đưa vào bên trong nó không thể đặt vào một Objects cụ thể nào, nếu như ta cố tình gán vào một object nào đó, Object đó chắc chắn sẽ bị Spoiled.
- Vì vậy, Domain service giúp chúng ta giải quyết vấn đề trên, với mỗi use-case, ta sẽ có thể nhìn ra được domain service và cô động các actions để dễ kiểm soát cũng như cài đặt hơn

## Aggregate

### Aggregate là gì?

Chúng ta đã đi qua các khái niệm về **Entity**, **Value Objects** khi triển khai phân tích **Domain**. Trong quá trình đó các **Domain Objects** sẽ có những mối quan hệ liên quan tới nhau, ví dụ như Khách hàng A ở tại Địa chỉ B. Tùy vào **Domain** mà các mối quan hệ có thể là **1-1**, **1-n** hay **n-n**. Và cũng tùy vào **Domain**, chắc chắn sẽ tồn tại những mối quan hệ rất phức tạp mà một **Entity** có thể liên quan tới nhiều **Entities** hoặc **Value Objects** khác. 

Các relationship thường sẽ bị hai chiều như 2 (“Ai ở địa chỉ này?” và “Địa chỉ thuộc về ai?”), nhưng một số relationship có thể được đơn giản hóa thành một chiều. Từ khách hàng ta sẽ có địa chỉ của họ, ta không tìm khách hàng từ một địa chỉ nào đó. Việc này giúp đảm bảo tính consistency với các mối quan hệ phức tạp.

Aggregate pattern ra đời với mục địch giải quyết vấn đề complex relationship. Việc ta xác định, khoanh vùng những Objects liên quan với nhau sẽ giúp ích cho việc modeling domain, cùng với đó hỗ trợ việc xây dựng cũng như đảm bảo performance của hệ thống. 

> Aggregate là một cụm các đối tượng domain liên kết logic, và được truy cập thông qua Aggregate Root duy nhất (thường là một Entity)
> 

### Vì sao cần Aggregate?

- Vẫn với ví dụ là shop bán sách, **người dùng mua sách**, bạn phải sử lý **đơn hàng**, các **items** mà khách hàng đã chọn mua, xem xét **membership** của khách hàng và đưa ra quyết định rằng có **discount** hay không, cùng với đó tính toán việc **delivery đơn hàng** đến vị **khách** đấy, thêm nữa việc **thanh đoán** có thể **thực hiện online** và bạn phải xem xét các **bên thứ 3**.
- Nếu bạn không có một cluster, một vùng bọc lại các Objects liên quan tới nhau thì việc nhìn vào domain với mớ relationship kia sẽ rất phiền phức, ở đây chỉ là một ví dụ cực kì nhỏ để các bạn có thể hình dung sơ qua, chỉ là một shop, bạn hãy tưởng tượng một sàn thương mại điển tử như Shopee chẳng hạn, khó thở lắm.
- Tiếp theo, việc chỉnh sửa một thông tin của **Slave Object**. Khi bạn cần phải giao hàng đến **khách hàng A** tại **Địa chỉ B**, thì bạn sẽ phải làm việc với **Khách hàng A** hay **Địa chỉ B**? Chắc chắn là làm việc với khách hàng đúng không? Vì vậy khi một thao tác chỉnh sửa tới child objects, nó nên được thông qua **Owner Object**. Và **Owner Object** trong một **bounded area** được gọi là **Aggregate Root** (là một **Entity**). Mọi **references** từ bên ngoài đều phải thông qua **Aggregate Root** và không bao giờ được đến trực tiếp tới các **Objects** khác thuộc bounded area đó.
- Việc không cho chỉnh sửa trực tiếp mà phải thông qua **Aggregate Root** là cần thiết, việc này giúp đảm bảo tính consistency với các mối quan hệ phức tạp.

# Tiếp theo

Với các bài trước cho tới bài này, ta có được những cái nhìn sơ bộ về DDD cũng như một vài core concept của nó. Tiếp theo ta sẽ tới một phương thức giúp ta dễ dàng hơn trong việc trả lời câu hỏi “Điều gì đang diễn ra trong Domain vậy?”. Mời các bạn đến với Event Storming