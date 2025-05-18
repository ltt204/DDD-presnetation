---
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
style: |
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');
  section {
    font-family: 'Roboto', sans-serif;
  }
marp: true
---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  h1 {
    font-size: 2.5em;
  }
</style>

# **Core Concept of DDD**
## **Ubiquitous Language**

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  h1 {
    font-size: 2.5em;
    text-align: center;
  }
</style>

# **Ubiquitous Language là gì?**

- Là một khái niệm cốt lõi trong DDD
- Không có định nghĩa chính thức từ Eric Evans
- Được minh họa qua các tình huống thực tế
- Giải quyết rào cản ngôn ngữ giữa Developers và Domain Experts

---

# **Rào cản ngôn ngữ**

- Lập trình viên và chuyên gia domain có kiến thức chuyên môn khác nhau
- Khi cùng trao đổi về hệ thống, dễ phát sinh hiểu nhầm
- Domain experts dùng từ ngữ chuyên ngành của lĩnh vực họ
- Developers dùng thuật ngữ kỹ thuật của lĩnh vực CNTT
- → Dễ dẫn đến hiểu sai và phát triển sai hướng

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  h1 {
    font-size: 2.5em;
    margin-bottom: 0.5em;
  }
  p {
    font-size: 1.5em;
    text-align: center;
  }
</style>

# **Vì sao cần Ubiquitous Language?**

Hiểu rõ lĩnh vực để có thể thiết kế hệ thống đúng đắn

---

# **Tầm quan trọng của Ubiquitous Language**

- Cần hiểu rõ domain để thiết kế hệ thống phù hợp
- Không có "bức tranh" toàn cảnh → khó khăn trong thiết kế
- Thiết kế sai → code sai
- Tạo kênh giao tiếp hiệu quả giữa các thành viên
- Lấy model làm trung tâm trong mọi cuộc trao đổi

---

# **Hậu quả của việc thiếu Ubiquitous Language**

Nếu hai bên không có ngôn ngữ chung:
- Hiểu khái niệm theo cách riêng của mỗi bên
- Thiếu sự nhất quán trong diễn giải
- Tiềm ẩn rủi ro cao
- Nguy cơ hiểu lầm lớn cho cả hai bên

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  h1 {
    font-size: 2.5em;
    margin-bottom: 0.5em;
    text-align: center;
  }
  blockquote {
    font-size: 1.2em;
  }
</style>

# **UL được hình thành như thế nào?**

> "The model-based language" - Ngôn ngữ dựa trên model

- Bộ quy tắc về ngôn ngữ xoay quanh model
- Sử dụng xuyên suốt giữa các lập trình viên và domain experts
- Ubiquitous = có mặt ở khắp mọi nơi trong quá trình làm việc

---

# **Đặc điểm của Ubiquitous Language**

- Không bất biến, có thể thay đổi theo thời gian
- Được điều chỉnh khi phát hiện vấn đề trong quá trình sử dụng
- Cần sự tham gia của cả hai phía:
  - Domain experts hiểu sâu về lĩnh vực
  - Developers hiểu rõ về khía cạnh kỹ thuật
- Xoay quanh model - trung tâm của hệ thống

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  blockquote {
    width: 80%;
    text-align: center;
    font-size: 1.3em;
    padding: 1em;
    background-color: rgba(200, 200, 200, 0.2);
    border-radius: 10px;
  }
</style>

> Ubiquitous Language không phải là một loại ngôn ngữ, nó đại diện cho việc giao tiếp giữa các thành viên trong team với nhau. Mọi người trao đổi, xây dựng nên bộ quy tắc để giao tiếp về khái niệm **xung quanh một model**, và họ sẽ phải cam kết sử dụng các quy ước trên trong suốt quá trình làm việc.

---

# **Công cụ giao tiếp cho Ubiquitous Language**

- **UML**: Giúp thể hiện mối quan hệ giữa các objects
  - Hiệu quả với số lượng object nhỏ (3-5)
  - Nhưng không đủ cho hệ thống phức tạp

- **Kết hợp nhiều phương thức**:
  - UML + Documents
  - Code
  - Trao đổi trực tiếp

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  h1 {
    font-size: 2.5em;
  }
  ul {
    font-size: 1.3em;
    list-style-type: none;
    padding: 0;
  }
</style>

# **Hạn chế của một công cụ duy nhất**

- UML với nhiều objects → quá phức tạp
- Các mối quan hệ chằng chịt → khó hiểu
- UML quá đầy đủ → dễ gây hiểu lầm
- Cần kết hợp nhiều phương thức giao tiếp

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  h1 {
    font-size: 2.5em;
    margin-bottom: 1em;
  }
  p {
    font-size: 1.3em;
  }
</style>

# **Tóm tắt**

Ubiquitous Language là:
- Đại diện cho sự giao tiếp giữa các thành viên
- Không phụ thuộc vào một loại ngôn ngữ cụ thể
- Sử dụng kết hợp diagrams, documents, code và trao đổi trực tiếp
- Xoay quanh Model - cốt lõi của dự án
- "Back-bone language" theo cách gọi của Eric Evans

---

<style scoped>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  h1 {
    font-size: 3em;
  }
</style>

# **Tiếp theo**

Model-driven design và cách model hiện diện trong quá trình phát triển hệ thống