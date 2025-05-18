# Core concept of DDD: Ubiquitous Language

Subject: Software Design
Date: March 13, 2025
Tags: Idea, Note
Trong Tin Ly: Tiến Phan Thanh, Trong Tin

# Overview

Hoq bjc noj j`

# Ubiquitous Language

Đây là khái niệm được nhắc đến đầu tiên. Evans không thực sự trả lời câu hỏi “Nó là gì?”, ông dẫn dắt mình qua tình huống ngoài khi các Domain Experts làm việc chung với Developers đính kèm là sự khác nhau về “ngôn ngữ” mặc dù cả 2 đều dùng tiếng Việt (chẳng hạn).

Có thể nói đó là rào cản ngôn ngữ. Những người lập trình viên, ngồi xuống cùng với những con người khác nhau về chuyên môn để cùng trao đổi về một khía cạnh của hệ thống mà hai bên sẽ cùng nhau phát triển. Khi đó ta cần phải hiểu về hệ thống và các khái niệm xung quanh nó. Domain experts sẽ miêu tả những behaviors, những tính chất của hệ thống bằng các từ ngữ “chuyên ngành” trong lĩnh vực của họ. Với sự khác nhau về domain, hai bên chắc chắn sẽ xảy ra sự misleading và đây là một điều cần tránh khi làm việc nhóm

## Vì sao lại cần UL?

Bắt đầu nào, bạn còn nhớ lúc nhỏ, à mà cũng không cần xa tới vậy, giờ ném bạn qua bên trường Y Dược nghe mấy bạn bên đó nói chuyện về các cơ quan trong cơ thể thì lúc đó bạn sẽ cảm thấy như thế nào? 

Nó không phải lĩnh vực của chúng ta. Khi làm việc mình sẽ cần phải ngồi lại với những “domain expert” để nghe họ diễn giải về *các khái niệm*, về *cách hoạt động,*… của một phần trong hệ thống chúng ta sắp sửa bắt tay vào phát triển cũng sẽ tương tự như vậy. 

Nhưng những điều đó là thứ mà chúng ta phải nghe, phải hiểu thì chúng ta mới biết được chúng ta cần thiết kế hệ thống như thế nào. Nếu không có được một *bức tranh* toàn cảnh về hệ thống, thì chưa nói tới việc code, chúng ta sẽ stuck tại phần thiết kế hoặc có thể xong nhưng sẽ không hoàn thiện nó. Mà khi phần design đã gặp vấn đề, thì phần code sẽ khó mà suôn sẻ.

Lúc này sự trao đổi, lăng nghe giữa các members trong team sự cần thiết. Ubiquitous Language không thực sự là một Language, nó nói về việc các members khi giao tiếp với nhau, cần lấy model làm trung tâm. 

Nếu như 2 bên (Developers and Domain Experts) không tìm được một bộ ngôn ngữ chung để giao tiếp với nhau, khi nghe những từ ngữ chuyên ngành của một bên, thì bên còn lại phải hiểu theo một cách riêng của họ, thiếu đi sự nhất quán. Việc này tiềm ẩn rủi ro cao, nó mang nguy cơ gây hiểu lầm rất lớn cho cả hai bên.

## UL được hình thành như thế nào?

“*The model-based language*" hay ngôn ngữ dựa trên model, bộ quy tắc về ngôn ngữ được sinh ra xoay quanh model được sử dụng giữa các lập trình viên, giữa lập trình viên và domain experts và giữa các domain experts với nhau hay nó Ubiquitous trong suốt quá trình làm việc và trao đổi.

Bộ quy tắc này không bất biến, khi nó được sử dụng thường xuyên, chắc chắn sẽ lòi ra các vấn đề không ít thì nhiều ảnh hưởng tới việc thấu hiểu các vấn đề gặp phải trong qua trình phát triển hệ thống. Khi đó, sẽ có những cuộc nói chuyện để thay đổi và chỉnh sửa ngôn ngữ ấy sao cho trở nên phù hợp hơn. Vì họ là domain expert, họ hiểu domain hơn chúng ta, và chúng ta cũng cần họ hiểu được khía cạnh kỹ thuật, là thứ mà chúng ta am hiểu hơn.

Dù ông không nói UL thực chất là gì, ông nhấn mạnh rằng UL là một ngôn ngữ xoay quanh model và được sử dụng giữa các bên. Với mình, đây là điều mình rút ra theo góc nhìn cá nhân:

<aside>
🤓

Ubiquitous Language không phải là một loại ngôn ngữ, nó đại diện cho việc giao tiếp (communication) giữa các thành viên trong team với nhau. Mọi người trao đổi, xây dựng nên bộ quy tắc để giao tiếp về khái niệm **xung quanh một model**, và họ sẽ phải cam kết sẽ sử dụng các quy ước trên trong suốt quá trình làm việc. 

</aside>

## Công cụ giao tiếp: UML, docs, code, giao tiếp

Việc gạch đi phần UML này cũng có lý do, sau khi đọc thêm và nghiền ngẫm nhiều hơn, một mình UML không thể là ngôn ngữ trung gian để giao tiếp.

UML rất ổn, không cần bàn cãi, những nó không đủ. Nó là một công cụ có thể giúp chúng ta thể hiện các mối quan hệ giữa các objects với nhau. Nó sẽ rất tuyệt với khi trên whiteboard chỉ có 3-5 objects, mọi người có tập trung để hiểu và nêu lên các ý kiến, quan điểm của mình về các relationships đó.

Nhưng nếu như có qua nhiều objects, các đường quan hệ nối chằn chịt, có thể tràn ra khỏi bảng bất cứ lúc nào. Khi đấy thì mọi người sẽ bị quá tải (overwhelm, không biết diễn tả như nào) bởi sự rối rắm của nó. UML khi thể hiện một object thì thường sẽ đầy đủ mọi thứ, từ relationships và cả các attributes của nó. Khi quá nhiều objects thì tổng quan diagram sẽ too complete và dễ dẫn đến sự misleading.

Vì vậy, sử dụng mỗi UML là không đủ, ta cần kết hợp nhiều phương thức để các thành viên trong đội giao tiếp với nhau. Từ UML, kết hợp cùng documents, cả code cũng sẽ tham gia. Cuối cùng là việc nói chuyện trực tiếp để bù đắp cho phần “sắc thái” của các phương thức trên.  

# Tóm tắt

Ubiquitous Language không có một hình thù cố định, nó là đại diện cho sự giao tiếp giữa các thành viên. Nó không sử dụng bất kì một loại ngôn ngữ nào, mọi thứ từ diagrams, documents hay cả trao đổi ngoài đời sống. Và khi giao tiếp với nhau, bất kể phương thức nào, thì đều cần xoay quanh Model, cái cốt lõi của dự án, hay Eric Evans nói là “back-bone language”.

Phần tiếp theo sẽ nói về Model-driven design, đi sâu hơn về việc model sẽ hiện diện như thế nào trong quá trình phát triển hệ thống.