# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: Nguyễn Trọng Phúc
- Mã học viên: 2A202602552
- Vai trò / bối cảnh (VD: sinh viên năm X, intern PM, ...): Hiện tại mình đang làm AI Engineer tại Vin Smart Future (thuộc Vingroup). Đợt này mình được giao phối hợp với bên Khối Vận Hành của VinFast và Xanh SM (GSM) để tìm ra các điểm nghẽn trong quy trình.
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem):
  - Phân tích xem có quy trình nào đang làm bằng tay mà gây chậm tiến độ bên VinFast và Xanh SM không.
  - Đi thực tế và khảo sát xem người dùng xe điện VinFast đang kêu ca gì nhất (nhất là vụ app, trạm sạc với khi gọi hỗ trợ).
  - Đề xuất xem chỗ nào nhét AI vào để tối ưu được.
  - Chạy đi họp với team vận hành để xem "pain point" nào là đau thật.
  - Lọc đống data vận hành (như vụ hủy chuyến bên Xanh, xe hết pin giữa đường, hay ngồi dò hóa đơn sạc điện).

---

## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | Lặp lại | Đối chiếu hóa đơn sạc điện đối tác: Cứ mỗi tuần kế toán lại phải lôi dữ liệu từ gần 2.000 trụ sạc liên kết ra dò tay với hóa đơn thực tế trong hệ thống. | 3 bạn kế toán bên VinFast | Mất toi 40 tiếng/tuần chỉ để dò số. Tỉ lệ sót lỗi tầm 12%, tính ra thất thoát cỡ 500 triệu một quý. |
| 2 | Tốn thời gian | Phân tích lý do hủy chuyến: Ngày nào cũng phải ngồi nghe lại ghi âm khách gọi hủy chuyến, cộng thêm đọc note của tài xế để phân loại xem vì sao khách hủy (top 10 lý do). | Team QA với bên Vận hành Xanh SM, các sếp cũng bị ảnh hưởng vì báo cáo chậm | Ở HN thôi mà ngày đã tầm 200 cuốc hủy. Mỗi case nghe và note mất 8-12 phút. Team QA tốn gần 30 tiếng mỗi ngày, insight thì 3-5 ngày sau mới tới tay sếp. Tính ra mất khoảng 8-10% GMV do không tối ưu kịp. |
| 3 | AI có thể tốt hơn | Chẩn đoán lỗi xe từ mô tả tiếng Việt: Khách toàn tả kiểu "xe kêu cụp cụp", "nghe xẹt xẹt", mấy bạn tổng đài phải nghe rồi tự đi tra cứu cái list 450 mã lỗi xem nó là bệnh gì. | Mấy bạn CSKH với khách hàng VinFast | Phân loại đúng ngay lần đầu mới được tầm 55%. Chừng 30% khách vác xe lên xưởng xong phải quay lại lần 2 vì bắt bệnh sai. Mỗi lượt khách gọi mất tầm 10 phút. |
| 4 | Pain từ người khác | Xử lý sự cố pin thực địa: Bác tài đang chạy thì báo hết pin, điều phối viên lại lạch cạch lên hệ thống tra xem trạm nào gần nhất hoặc điều xe cứu hộ tới. | Bác tài Xanh SM với mấy bạn điều vận | Mỗi ca giải quyết mất tầm 15 phút. Ngày cỡ 80 ca ở Hà Nội, ngốn 20 tiếng/ngày của bộ phận điều vận, làm rò rỉ đâu đó 15% doanh thu vì xe nằm đường. |
| 5 | AI-upgrade + Pain từ người khác | App VinFast tìm trạm sạc quá khó. Data thì không real-time (nhiều khi tới nơi mới biết trụ đang có người sạc). Khách thì chả biết pin hiện tại có lết nổi tới đích hay tới trạm tiếp theo không. | Khách đi xe VinFast, bác tài Xanh SM, mấy bạn trực tổng đài | Tầm 25% chủ xe kêu từng bị hết pin dọc đường do không tính được. 30% tới trạm nhưng trụ sạc full lại lóc cóc đi tìm trạm khác. NPS giảm mất 18 điểm, tổng đài ngày hứng 300 cuộc gọi chỉ để hỏi "em ơi trạm sạc gần nhất ở đâu?". |

> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi: Mình có nhờ AI gợi ý thêm xem trong hệ sinh thái VinFast với Xanh SM thì còn những pain point nào theo 4 lăng kính kia.
- Ý dùng được: Khá hay là AI gợi ý thêm vụ "range anxiety" (nỗi sợ hết pin dọc đường) từ góc độ người dùng cuối — cái này khớp luôn với mấy cái khảo sát thực tế mình đang làm.
- Ý bỏ vì không phải pain thật: AI có gợi ý mấy cái kiểu "xây AI toàn diện cho chuỗi cung ứng" — nghe thì kêu nhưng chả có workflow cụ thể nào, với lại nó out trình so với phạm vi vận hành mình đang làm, nên bỏ.

**Self-check Phase 1:**
- [x] Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể
- [x] Dùng ít nhất 3/4 lăng kính
- [x] Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
| 1 | ⭐ AI Agent Trợ lý Sạc Thông minh (App VinFast — trạm sạc + dự đoán pin) | Đây là nỗi đau số 1 của người dùng luôn. 100% chủ xe VinFast với tài xế Xanh SM đều dính. Làm được cái này ROI cực cao (đỡ được bao nhiêu cuộc gọi tổng đài, kéo NPS lên). | Dự đoán pin thì dễ sai số vì còn tùy thời tiết, đạp ga mạnh nhẹ, xe chở nặng hay nhẹ. Chưa rõ API trạm sạc bên VinFast có support real-time thật không. |
| 2 | Phân tích lý do hủy chuyến Xanh SM | Workflow 5 bước rất rõ ràng, điểm nghẽn cũng nằm lồ lộ ở bước 2-3 (nghe ghi âm). Đo đếm được ngay (đang từ 8-12 phút xuống tính bằng giây). | Cần có một model Speech-to-Text tiếng Việt ngon. Scope có thể hơi phình to ra. |
| 3 | Chẩn đoán lỗi xe từ mô tả tiếng Việt | Thấy rõ ai đang chịu khổ (CSKH), quy trình 4 bước rành rành. Accuracy cải thiện từ 55% lên 85% là đo được ngay. | Cái này chủ yếu giúp nội bộ CSKH chứ chưa trực tiếp gãi ngứa được cho khách hàng ngoài kia. |

### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

---

#### Problem Card #1 — ⭐ AI Agent Trợ lý Sạc Thông minh

```text
Problem 1 câu:
Cần một con AI Agent tự biết tính xem pin còn lại có bò tới đích được không, 
chủ động báo người lái lúc nào nên sạc và chỉ luôn trạm sạc ĐANG TRỐNG trên 
đường đi — giải luôn cái "nỗi sợ hết pin" mà app hiện tại chưa làm được.

Actor:
• Khách đi xe VinFast (lúc nào cũng nơm nớp lo hết pin, hoặc chạy tới trạm sạc thì full trụ)
• Bác tài Xanh SM (đang chở khách mà cạn pin thì ăn cám)
• Mấy bạn trực tổng đài (ngày nghe 300 cuộc gọi hỏi đường ra trạm sạc)

Thời điểm / bối cảnh:
Cứ lúc nào chạy đường dài hoặc đi trong phố mà pin báo thấp là bị. 
Ngày nào cũng có người dính, cả chủ xe cá nhân lẫn tài xế Xanh SM.

Current workflow 3-7 bước:
1. Nhìn đồng hồ báo % pin
2. Lôi app VinFast ra dò trạm sạc (app thì lag, search tìm mỏi mắt)
3. App báo trạm "còn trống" nhưng thật ra chả real-time gì
4. Hì hục lái tới nơi → hết trụ trống → lại lóc cóc quay ra tìm trạm khác
5. Bí quá bốc máy gọi tổng đài nhờ tra hộ (mất toi 7 phút/cuộc)

Bottleneck:
• Bước 2-3: Dùng app ức chế + data cũ rích (mất 5-10 phút mò mẫm)
• Bước 4: Đến nơi full trụ (lãng phí 15-30 phút vòng tới vòng lui)

Impact:
Khoảng 25% chủ xe từng bị hết pin giữa đường, 30% tới trạm mà ngậm ngùi quay đầu. 
Làm NPS rớt mất 18 điểm, tổng đài thì ngày nào cũng gánh 300 cuộc gọi mệt mỏi.

Success metric:
Giảm tỉ lệ cạn pin giữa đường từ 25% xuống < 5%.
Đến trạm mà full trụ giảm từ 30% xuống < 5%.
Tổng đài đỡ được việc, giảm từ 300 xuống < 50 cuộc gọi hỏi trạm/ngày. Kéo NPS lên 18 điểm.

Non-AI alternative:
Sửa lại UI/UX của app cho dễ tìm hơn, update data trạm sạc liên tục (tầm 5 phút/lần).
Nhưng cách này khách vẫn phải tự tính toán pin và tự lên kế hoạch, không chủ động nhắc được.

AI hypothesis:
Làm một con AI Agent kết hợp Model học máy dự đoán pin (dựa vào tốc độ đang chạy, 
thời tiết, tải trọng) + API check trạm sạc real-time + GPS. Con Agent này sẽ tự nhảy 
ra cảnh báo nếu thấy pin không đủ lết tới đích, và tự động vẽ đường ra trạm sạc đang 
trống tiện nhất.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết
```

**Draft workflow Card #1** (ASCII / Mermaid / ảnh đính kèm):

```text
CURRENT STATE — Mất 22-47 phút (mỗi lần cần sạc)

[1 Ngó % pin: 1'] → [2 Mò app tìm trạm: 5-10'] → [3 Lái tới trạm: 10-20'] → [4 Trạm full → quay lại: 15-30']  <-- chỗ kẹt ở đây
→ [5 Gọi hotline: 7']

FUTURE STATE — Mất 2-5 phút (chủ động báo, khỏi cần mò)

[1 AI tự tính pin + chủ động alert: 0' (tự động)]
→ [2 AI tự check trạm trống real-time trên đường đi rồi gợi ý: 0' (tự động)]
→ [3 Tài xế OK + lái theo map: 2-5']  <-- human boundary
→ [4 Đến nơi sạc luôn vì biết chắc trạm trống]

Fallback: Nếu AI tính sai hoặc API trạm sạc sập → tài xế vẫn lôi app ra dò tay 
hoặc gọi hotline như cũ.
```

File đính kèm (nếu vẽ riêng): `01-individual-problem-scan-workflow-card-1.png`

---

#### Problem Card #2 — Xanh SM: Phân tích lý do hủy chuyến

```text
Problem 1 câu:
Tự động nghe file ghi âm khách hủy chuyến + đọc note của bác tài để xếp vào 
10 lý do hủy phổ biến, giúp team QA bắt bệnh được ngay trong ngày thay vì 
phải chờ 3-5 ngày sau mới có report.

Actor:
• Team QA/Vận hành Xanh SM (ngày nào cũng căng tai nghe 200 cuộc ghi âm)
• Ban Giám Đốc (đợi report dài cổ, lúc nhận được thì việc đã rồi)

Thời điểm / bối cảnh:
Ngày nào team QA ở Hà Nội cũng phải nghe cỡ 200 cuộc khách gọi hủy. Cần số liệu ngay 
để điều chỉnh mà toàn bị trễ 3-5 ngày.

Current workflow 3-7 bước:
1. Lên hệ thống kéo file ghi âm với ghi chú của tài xế xuống
2. Cắm tai nghe từng file, gõ note lại nội dung (8-12 phút/case)
3. So lại với cái list 10 lý do hủy chuyến xem nó thuộc loại nào
4. Gõ kết quả vào Google Sheet
5. Cuối tuần gom lại làm báo cáo nộp sếp

Bottleneck:
Bước 2-3: Vừa nghe ghi âm vừa phân tích phân loại. 8-12 phút/case × 200 case/ngày 
= ngốn hết 30 tiếng mỗi ngày của team QA.

Impact:
Để thất thoát doanh thu tầm 8-10% GMV vì bắt mạch trễ, không sửa chính sách kịp. 
Mấy bạn QA thì cày chết bỏ, 30 tiếng/ngày cho đúng 1 cái task lặp đi lặp lại.

Success metric:
Từ 8-12 phút rút xuống dưới 1 phút/case. Sếp có insight ngay trong ngày. Độ chính xác phải đạt ≥ 90%.

Non-AI alternative:
Tuyển thêm chục bạn QA về ngồi nghe → tốn tiền, không scale được. 
Gom bớt lý do hủy lại → báo cáo sẽ chung chung, chả biết đường nào mà sửa.

AI hypothesis:
Dùng API Speech-to-Text để dịch ghi âm ra chữ → Ném vào LLM để nó tự soi 10 lý do 
và dán nhãn → Tự động đổ data vào Sheet. Mấy bạn QA chỉ cần check lại mấy case 
con AI báo confidence thấp là xong.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #2:**

```text
CURRENT STATE — Ngốn 30 giờ/ngày (của cả team QA)

[1 Kéo file ghi âm: 30'] → [2 Nghe + take note: 8-12'/case × 200]  <-- nút thắt
→ [3 Dán nhãn lý do: 2'/case] → [4 Điền Sheet: 1'/case] → [5 Làm báo cáo tuần]

FUTURE STATE — Rút còn ~3 giờ/ngày

[1 Tool tự kéo ghi âm: 5' (dùng rule/script)]
→ [2 Speech-to-Text dịch ra chữ: ~30s/case (AI lo)]
→ [3 LLM dán nhãn + tự điền Sheet: ~10s/case (AI lo)]
→ [4 QA chỉ ngồi check lại mấy case khó: 2'/case ~20 cases]  <-- human boundary
→ [5 Dashboard có số nhảy real-time luôn]

Fallback: Case nào AI dịch sai hoặc không tự tin (< 80%) → QA lại cắm tai nghe làm tay.
```

File đính kèm: `01-individual-problem-scan-workflow-card-2.png`

---

#### Problem Card #3 — VinFast: Chẩn đoán lỗi xe từ mô tả tiếng Việt

```text
Problem 1 câu:
Dùng AI nghe/đọc mô tả bệnh của xe từ khách (bằng tiếng Việt tự nhiên) rồi tự 
map ra mã lỗi kỹ thuật, giúp mấy bạn CSKH bắt bệnh chuẩn hơn, kéo tỉ lệ trúng phóc 
lần đầu từ 55% lên 85%.

Actor:
• Bạn CSKH VinFast (suốt ngày phải ngồi dò cái bảng 450 mã lỗi hoa cả mắt)
• Khách hàng (bực mình vì bắt sai bệnh, vác xe đi sửa lần 2)

Thời điểm / bối cảnh:
Khách gọi hotline tả bệnh xe bằng từ ngữ đời thường (kiểu "xe em bị xệ đuôi", 
"đang chạy nghe lục cục"). Ngày nào cũng có hàng trăm cuộc gọi kiểu này.

Current workflow 3-7 bước:
1. Khách gọi hotline than phiền về xe
2. Bạn CSKH vừa nghe, vừa chép lại, rồi tra cái bảng 450 mã lỗi
3. Chốt xem là lỗi gì, tư vấn sửa chữa
4. Lên lịch hẹn vác xe ra xưởng

Bottleneck:
Bước 2-3: Khách tả kiểu dân dã, CSKH phải tự phiên dịch ra thuật ngữ kỹ thuật 
rồi lục trong 450 mã lỗi. Mất xừ nó 10 phút/lượt, mà bắt đúng bệnh được có 55%.

Impact:
Tầm 30% khách hàng phải xách xe lên xưởng lần 2 vì sửa lần 1 không hết bệnh. 
Vừa bực mình khách, vừa tốn tiền xưởng. NPS tuột dốc.

Success metric:
Bắt đúng bệnh lần đầu: 55% → 85%. 
Khách phải đi sửa lần 2: 30% → 10%. Thời gian tư vấn: 10 phút → 3 phút.

Non-AI alternative:
Làm lại cái bảng mã lỗi cho dễ search hơn + training các bạn CSKH kỹ hơn. 
Nhưng tiếng Việt thì phong phú, tra bằng text bình thường vẫn khó trúng.

AI hypothesis:
Dùng NLU tiếng Việt để hiểu khách đang tả cái gì → Map cái đó vào kho mã lỗi 
kỹ thuật → Gợi ý luôn phương án sửa chữa. CSKH chỉ việc dòm lại xem hợp lý 
không rồi confirm với khách.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
```

**Draft workflow Card #3:**

```text
CURRENT STATE — Tốn 10 phút/lượt

[1 Khách tả bệnh: 2'] → [2 CSKH tra 450 mã lỗi: 5']  <-- nút thắt ở đây
→ [3 Bắt bệnh + tư vấn: 2'] → [4 Chốt lịch hẹn xưởng: 1']

FUTURE STATE — Còn 3 phút/lượt

[1 Khách tả (voice/text): 1']
→ [2 AI NLU hiểu ý + tự động map mã lỗi: ~10s (AI)]
→ [3 CSKH nhìn gợi ý + chốt lại với khách: 1.5']  <-- human boundary
→ [4 Tool tự đặt lịch xưởng: 30s]

Fallback: AI mà độ tin cậy < 70% thì CSKH lại quay ra tra bảng bằng tay.
```

File đính kèm: `01-individual-problem-scan-workflow-card-3.png`

---

### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```text
Card #1 — ⭐ AI Agent Trợ lý Sạc Thông minh (VinFast)
```

**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```text
Thực sự đây là pain point lớn nhất của người dùng xe điện: luôn nơm nớp sợ hết pin, 
app tìm trạm thì chán, data thì sai bét. Làm được cái này là cứu vãn được cả chủ xe 
VinFast lẫn tài xế Xanh SM. Tưởng tượng xem, đỡ được cả đống cuộc gọi ăn vạ lên tổng đài, 
NPS tăng vọt. Rất đáng để ốp mô hình Agent vào vì phải kết dính đống data real-time lại với nhau.
```

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

```text
1. Data train model để đoán pin có chuẩn không? Vì chạy xe ngoài đường còn tùy 
   trời mưa nắng, bật điều hòa to nhỏ, đạp ga thốc hay nhẹ.
2. Bên VinFast có sẵn cái API trả trạng thái trụ sạc real-time không, hay mình lại 
   phải đẻ ra thêm một bước build cái API đó?
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra: AI nó vặn vẹo là scope này to quá, một con Agent ôm cả vụ dự đoán pin, check trạm, với vẽ lại đường đi là quá sức, kéo theo nguyên mảng data pipeline khổng lồ. Nó khuyên làm Workflow check trạm sạc trước cho dễ.
- Tôi sửa gì: Công nhận nó nói đúng. Mình chốt lại là chia phase ra làm. Pilot đầu tiên chỉ làm vụ lấy trạng thái trạm sạc real-time + hú lên khi pin yếu thôi. Ngon lành rồi mới ráp cái model dự đoán pin xịn xò vào sau.

### Self-check nộp phần 01
- [x] Có 5+ problems + top 3 Cards đủ field
- [x] Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- [x] Đã chọn 1 card pitch + câu hỏi challenge
