# 03 — Individual Reflection

> Viết bằng lời của bạn (Phase 7 trong `01-worksheet.md`). Có thể dùng AI gợi ý câu hỏi tự soi, không dùng AI viết thay. 8-12 câu, có chuyện cụ thể.

## Thông tin cá nhân

- Họ và tên: Nguyễn Trọng Phúc
- Mã học viên: 2A202602552
- Nhóm: Nhóm 5 thành viên
- Candidate problem nhóm chọn: Điều phối lựa chọn trạm sạc cho tài xế Xanh SM/chủ xe VinFast dựa trên mức pin, quãng đường, giao thông và trạng thái trụ thay đổi theo thời gian.

---

## 1. Tôi đã tham gia vào phần nào?

Ghi việc cụ thể + kết quả cụ thể. Không ghi chung chung kiểu "tham gia thảo luận".

| Hoạt động | Tôi đã làm gì? (việc cụ thể) | Kết quả / ảnh hưởng tới nhóm |
| --- | --- | --- |
| Scan cá nhân | Tôi ghi lại 5 vấn đề từ bối cảnh VinFast/Xanh SM, gồm đối chiếu hóa đơn sạc, phân tích hủy chuyến, chẩn đoán lỗi xe, xử lý sự cố pin và tìm trạm sạc. | Nhóm có ba candidate thuộc đúng domain tôi đang làm để đưa vào vòng hội tụ. |
| Pitch Problem Card | Tôi chuẩn bị và trình bày ba candidate: trợ lý sạc, phân tích lý do hủy chuyến và chẩn đoán lỗi xe từ mô tả tiếng Việt; candidate trạm sạc là bài tôi ưu tiên. | Candidate trạm sạc được đưa vào shortlist và sau đó trở thành bài toán nhóm chọn. |
| Challenge bài của bạn khác | Repo chưa ghi lại câu hỏi cụ thể nào tôi đã đặt cho candidate của thành viên khác, nên tôi không nhận phần đóng góp này. | Không có bằng chứng đủ rõ để kết luận ảnh hưởng của tôi ở hoạt động này. |
| Gom trùng / cluster | Tôi làm rõ ba candidate VinFast/Xanh SM của mình và sự khác nhau giữa pain của người dùng cuối với pain nội bộ QA/CSKH; tôi không nhận là người tổng hợp toàn bộ bảng cluster. | Ba candidate của tôi được đặt trong cụm vận hành và trải nghiệm VinFast/Xanh SM để nhóm so sánh. |
| Chọn candidate problem | Tôi đề xuất bài toán trạm sạc và nêu các biến động cần xét: pin, quãng đường, giao thông, trạng thái trụ và trường hợp nhiều xe cùng hướng tới một trạm. | Nhóm thu hẹp từ “tìm trạm gần nhất” sang duy trì lựa chọn trạm phù hợp khi điều kiện thay đổi. |
| Validation / research | Với vai trò research, tôi đối chiếu các chức năng tìm trạm, định tuyến, ước lượng pin và đặt chỗ đã có của VinFast qua nguồn chính thức. | Nhóm tránh build lại chức năng cơ bản và nhận ra cần kiểm chứng khoảng trống re-routing/điều phối thực tế. |
| Workflow nhóm | Với vai trò workflow, tôi góp phần mô tả luồng hiện tại từ kiểm tra pin đến đổi/giữ phương án và luồng tương lai gồm Rule lọc an toàn, xếp hạng, người lái xác nhận và fallback. | Workflow chỉ ra bottleneck t0–t1, boundary human-in-the-loop và đường lui khi dữ liệu thiếu hoặc trễ. |
| Problem Statement | Tôi đóng góp ngữ cảnh domain, bottleneck và các metric cần đo như thời gian chọn/đổi trạm, số lần re-route và tỷ lệ override; tôi không nhận vai trò viết toàn bộ bản cuối. | Problem Statement v1 tập trung vào quyết định động, có boundary không tự quyết định thay người lái. |
| Rule / Workflow / Agent | Tôi điều chỉnh quan điểm ban đầu từ “AI Agent trợ lý sạc” sang Workflow làm mức chính, Rule giữ constraint an toàn và chỉ dùng AI ở trade-off khó. | Phương án pilot dễ kiểm soát, test và rollback hơn Agent tự lập kế hoạch. |
| Decision | Tôi ủng hộ quyết định `Not Yet` vì nhóm chưa có baseline và chưa xác minh quyền truy cập cũng như độ trễ của dữ liệu real-time. | Quyết định cuối không chạy theo AI; nhóm xác định rõ các bước validation cần làm trước pilot. |

**Dấu tay rõ nhất của tôi trong artifact cuối (1-2 câu):**

```text
Dấu tay rõ nhất của tôi là candidate điều phối trạm sạc VinFast/Xanh SM và phần research, workflow xoay quanh pin, giao thông, trạng thái trụ thay đổi theo thời gian. Tôi cũng góp phần kéo phương án từ “Agent” về Workflow + Rule có người lái xác nhận và có fallback.
```

---

## 2. Bảng dùng AI (mỗi dòng 1 phase có dùng AI — 2 cột cuối bắt buộc)

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
| --- | --- | --- | --- | --- |
| Scan | Tôi nhờ AI gợi ý thêm pain point trong hệ sinh thái VinFast/Xanh SM theo bốn lăng kính. | AI nhắc tới “range anxiety”, trùng với vấn đề tôi quan sát ở người dùng xe điện. | AI gợi ý “AI toàn diện cho chuỗi cung ứng”, quá rộng và không có actor hay workflow cụ thể. | Tôi bỏ ý quá rộng và chỉ giữ những vấn đề gắn với công việc, người chịu ảnh hưởng và dấu hiệu đo được. |
| Problem Card | Tôi dùng AI phản biện scope của card trợ lý sạc. | AI chỉ ra một Agent ôm dự đoán pin, trạng thái trạm và định tuyến sẽ kéo theo data pipeline quá lớn. | AI vẫn thiên về đề xuất giải pháp trước khi xác minh API và pain thực tế. | Tôi thu hẹp hướng pilot về trạng thái trạm, cảnh báo và workflow có thể kiểm soát trước. |
| Workflow | Tôi dùng AI kiểm tra các bước còn thiếu và gợi ý tách phần Rule, máy, AI và người lái. | AI giúp phát hiện cần có monitor, re-score và fallback khi dữ liệu thiếu hoặc trễ. | AI giả định dữ liệu real-time luôn sẵn và có thể tự re-route an toàn. | Tôi thêm bước người lái xác nhận, quyền override và quay về danh sách trạm gốc. |
| Research | Tôi dùng AI để gợi ý các chức năng hiện có cần kiểm chứng, sau đó chỉ giữ thông tin có nguồn VinFast chính thức. | AI giúp lập danh sách từ khóa về tìm trạm, ước lượng pin, route planning và reservation. | AI không chứng minh được API nội bộ, độ trễ dữ liệu hay giới hạn đặt chỗ. | Tôi ghi các điểm đó là điều chưa rõ và không biến chúng thành dữ kiện đã xác nhận. |
| Problem Statement | Tôi dùng AI phản biện độ mơ hồ của Problem Statement v0. | AI giúp nhận ra “app khó tìm trạm” chưa phải bottleneck đủ chặt. | AI có xu hướng viết metric kiểu “nhanh hơn, tốt hơn” nhưng không có baseline. | Tôi đổi bottleneck sang duy trì lựa chọn khi điều kiện thay đổi và ghi rõ metric vẫn cần baseline từ pilot. |
| Rule / Workflow / Agent | Tôi nhờ AI so sánh mức phù hợp của ba phương án trên cùng bài toán. | AI giúp tách Rule cho constraint an toàn, Workflow cho luồng xác định trước và Agent cho planning linh hoạt. | AI dễ suy luận rằng bài toán nhiều biến thì mặc định cần Agent. | Tôi chọn Workflow + Rule vì luồng chính vẫn mô tả được, dễ debug và có rủi ro thấp hơn. |
| Decision | Tôi dùng AI rà các điều kiện Go/Not Yet/No-Go và các giả định còn thiếu. | AI giúp hệ thống hóa câu hỏi về baseline, data, hậu quả khi sai và owner review. | AI không thể tự xác nhận pain, quyền truy cập API hay chất lượng dữ liệu thật. | Tôi giữ quyết định `Not Yet` và yêu cầu phỏng vấn, log thực tế cùng xác minh API trước khi pilot. |

> Nếu phase nào không dùng AI, ghi `Không dùng` và vì sao tự làm.

---

## 3. Reflection câu hỏi mở

Chọn 3-4 câu trong 6 câu dưới để viết thành đoạn 8-12 câu (không trả lời bullet 1 dòng):

- Tôi học được gì khi nghe top 3 problems của các bạn khác?
- Nhóm có lúc nào bị solution-first, đòi làm Agent cho ngầu không?
- Tôi có thay đổi ý kiến sau khi bị challenge không, vì sao đổi?
- Tôi đóng góp gì thật sự vào artifact cuối, phần nào có dấu tay của tôi?
- Điều khó nhất khi viết Problem Statement là gì, metric hay boundary?
- Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

**Reflection:**

```text
Khi nghe các candidate khác, tôi nhận ra bài toán có workflow và metric rõ chưa chắc được chọn nếu tác động chủ yếu chỉ nằm trong một quy trình nội bộ. Ở phần của mình, ba candidate đều đến từ VinFast/Xanh SM, nhưng bài trạm sạc được nhóm giữ lại vì tác động trực tiếp tới tài xế và chủ xe. Dấu tay rõ nhất của tôi là ngữ cảnh pin, giao thông, trạng thái trụ thay đổi theo thời gian và workflow xử lý từ lúc người lái kiểm tra pin đến khi giữ hoặc đổi trạm. Ban đầu tôi gọi ý tưởng này là “AI Agent Trợ lý Sạc Thông minh” và khá solution-first vì thấy bài toán có nhiều dữ liệu động. Sau khi bị phản biện về scope, API và rủi ro tự re-route, tôi đổi quan điểm sang Workflow + Rule, còn người lái vẫn xác nhận quyết định cuối. Sự thay đổi đó giúp tôi hiểu rằng độ phức tạp cao không đồng nghĩa với việc bắt buộc phải dùng Agent. Điều khó nhất khi viết Problem Statement là metric vì nhóm đã gọi tên được thời gian chọn trạm, số lần re-route và tỷ lệ override nhưng chưa có baseline hay mục tiêu định lượng. Research từ nguồn VinFast cũng cho thấy nhiều chức năng tìm trạm, định tuyến, ước lượng pin và đặt chỗ đã tồn tại, nên nhóm không thể giả định mình đang giải một khoảng trống hoàn toàn mới. Tôi học được rằng boundary “không tự quyết định thay người lái” và fallback về Rule quan trọng không kém ý tưởng tối ưu. Nếu làm lại, tôi sẽ challenge mạnh hơn về số liệu baseline, độ trễ dữ liệu trụ sạc và giới hạn reservation trước khi nhóm chấm candidate trạm sạc cao nhất.
```

---

## 4. Tự kiểm cuối bài (check trước khi nộp repo)

- [x] [12đ] Cá nhân có 5+ problems + top 3 Problem Cards
- [ ] [12đ] Tôi đã pitch rõ + challenge nhóm đúng trọng tâm (repo có nội dung pitch nhưng chưa ghi bằng chứng tôi đã challenge bài của thành viên khác)
- [x] Nhóm có nhật ký hội tụ từ candidates về 1 bài
- [x] [15đ] Nhóm có workflow trước/sau
- [ ] [20đ] Nhóm có PS v0/v1 với metric + boundary rõ (đã có metric và boundary nhưng chưa có baseline/mục tiêu định lượng)
- [x] [15đ] Nhóm có so sánh No AI / Rule / Workflow / Agent
- [x] [10đ] Nhóm có Go / Not Yet / No-Go + lý do rõ
- [x] [10đ] Reflection này có vai trò thật + AI giúp/sai ở đâu + điều học được + nếu làm lại đổi gì
- [ ] [6đ] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp AI (cần tự kiểm tra bằng cách trình bày lại mà không nhìn bài)
