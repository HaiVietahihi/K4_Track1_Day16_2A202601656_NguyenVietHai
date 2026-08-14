
# Memo Teardown — Figma

**Nhóm:** … · **Thành viên:** …

**Vì sao chọn sản phẩm này:** (1–2 câu)
Vì trước thời điểm AI bùng nổ, Figma là một công cụ mạnh mẽ dành cho những người làm về thiết kế UI/UX. Nhưng sau khi AI bùng nổ với sự xuất hiện của Claude design, Figma trở thành công cụ mọi người không sử dụng phổ biến nữa

**§1. Timeline các cập nhật lớn**

| Thời điểm    | Cập nhật                                          | Context lúc đó                                                                                                                                                                                                                                   | Nguyên lý                                                                                                                                                                              |
| --------------- | --------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 05/2025         | Figma Make ra mắt                                  | Config 2025: prompt-to-app sinh code thật (React/Tailwind), neo vào design system của khách hàng. Đối thủ AI-native (v0, Lovable, Replit) đã chiếm không gian "prompt-to-app"; Figma vừa trải qua khủng hoảng Make Design 2024.     | Học qua vòng lặp — sửa lỗ hổng thất bại 1 năm trước (thiếu domain context) bằng cách sinh code neo vào design system thật thay vì model chung.                         |
| 05/2025         | Figma Buzz ra mắt                                  | Config 2025: công cụ cho team marketing/brand tạo hàng loạt asset từ template khoá-brand, bulk multi-edit, tích hợp sinh ảnh AI (gpt-image-1, Gemini). Ra mắt cùng Make, Sites, Draw — tham vọng thay thế Illustrator/Canva/Webflow. | Mở rộng thị trường ngang: nhắm tới marketing/brand team, không chỉ mở rộng use case nội bộ; chiến lược cạnh tranh đa mặt.                                             |
| 06/2025         | Dev Mode MCP Server (beta)                          | Hệ sinh thái AI coding agent bùng nổ nhưng agent thiếu context thiết kế chính xác; agent hay đoán sai khi không có thiết kế làm nguồn chân thực.                                                                                | Phòng vệ chống "wrapper mỏng" — biến data thiết kế thành hạ tầng context không thể thay thế, cung cấp context trực tiếp cho agent thay vì cạnh tranh trực diện.     |
| 10/2025         | Mua Weavy (Figma Weave)                             | Figma mua Weavy (Tel Aviv, 2024) >$200M; Weave vận hành độc lập, tích hợp nhiều model AI (Seedance, Sora, Veo, Flux, Ideogram) cho ảnh/video/animation/VFX.                                                                                | Vertical AI = AI Expert + Domain Expert — mua đội domain expert để tránh làm hời hợt, và giữ độc lập trước khi tích hợp vào core để tránh lặp lại sai lầm 2024. |
| 12/2025 → 2026 | Hệ thống quản trị AI credit                     | Sau khi Make/Weave/agent chạy rộng, chi phí inference tăng nhanh và khó dự đoán; nhiều khiếu nại về credit, usage bất thường.                                                                                                       | "You can't just ship and forget" — PM AI phải xây vòng lặp monitor · cost · iterate liên tục; chi phí AI biến thiên khác biệt so với phần mềm deterministic.            |
| 06/2026         | Config 2026: code layers trên canvas + Figma agent | Ranh giới design vs code bị xóa nhòa; Figma agent có skill/connector/shared chat; đối thủ AI-gốc đe dọa lãnh thổ cốt lõi.                                                                                                            | Biến canvas thành nơi tích luỹ domain expertise của designer (đóng gói qua "skill"); thứ model chung không có — củng cố lợi thế cạnh tranh theo hướng Vertical AI.   |

*(6–8 hàng, mỗi hàng kèm link nguồn gốc)*

**Vì sao chọn những mốc này:** (2–3 câu — đâu là mốc nhóm đã loại ra và vì sao)
Những mốc được chọn là những mốc đánh dấu sự thay đổi lớn trong sự phát triển của Figma trong cuộc đua AI trong thời gian vừa qua. Những mốc không được chọn là những mốc đánh dấu sự phát triển của Figma nhưng không liên quan đến AI hoặc những thay đổi nhỏ liên quan đến bao nhiêu lượt người dùng được sử dụng AI.

**§2. Tệp user & JTBD — Figma (bản chuẩn chỉnh, có số liệu & nguồn)**

## 2.1 Quy mô & cơ cấu người dùng hiện tại (số liệu thật, từ hồ sơ IPO)

Figma nộp S-1 lên SEC ngày 1/7/2025 (IPO tháng 7/2025) — đây là nguồn số liệu đáng tin nhất vì là hồ sơ pháp lý bắt buộc công bố trung thực với nhà đầu tư, không phải blog marketing.

| Chỉ số                                                                  | Giá trị                                  | Thời điểm          | Nguồn                                                                                                                  |
| ------------------------------------------------------------------------- | ------------------------------------------ | --------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Monthly Active Users (MAU)                                                | 13 triệu                                  | T3/2025               | [Figma S-1, SEC EDGAR](https://www.sec.gov/Archives/edgar/data/1579878/000162828025033742/figma-sx1.htm)                 |
| % người dùng KHÔNG phải designer                                     | **~66% (2/3 MAU)**                   | T3/2025               | [SaaStr — Top 10 Insights From Figma&#39;s IPO Docs](https://cloud.substack.com/p/top-10-insights-from-figmas-ipo-docs) |
| % người dùng là developer                                             | **~30% MAU**                         | Q1/2025               | [SaaStr S-1 Breakdown](https://www.saastr.com/top-10-interesting-learnings-from-figmas-s-1-that-you-may-have-missed/)    |
| Khách hàng dùng ≥2 sản phẩm Figma                                   | **76%** (tăng từ 64% năm trước) | Q1/2025               | [MostlyMetrics — Figma IPO S-1 Breakdown](https://www.mostlymetrics.com/p/figma-ipo-s1-breakdown)                       |
| Net Dollar Retention                                                      | 132% (S-1) →**136%**                | T3/2025 → 31/12/2025 | S-1;[SQ Magazine Figma Statistics 2026](https://sqmagazine.co.uk/figma-statistics/)                                      |
| Gross Retention (khách >$10K ARR)                                        | **96%**                              | T3/2025               | [SaaStr Insights](https://cloud.substack.com/p/top-10-insights-from-figmas-ipo-docs)                                     |
| Khách hàng >$100K ARR                                                   | 1,031 → 1,405                             | Q1/2025 → Q4/2025    | S-1; SQ Magazine                                                                                                        |
| Khách hàng >$1M ARR                                                     | 40+ → 67 (+68% YoY)                       | T3/2025 → Q4/2025    | [MostlyMetrics](https://www.mostlymetrics.com/p/figma-ipo-s1-breakdown); SQ Magazine                                     |
| Deal Organization/Enterprise mới bắt nguồn từ 1 user Professional cũ | **70%**                              | 2024 & Q1/2025        | SaaStr, MostlyMetrics                                                                                                   |
| Fortune 500 dùng Figma                                                   | 95%                                        | T3/2025               | SQ Magazine                                                                                                             |

**Đọc số liệu này ra sao (đây là bằng chứng định lượng cho phần "dịch chuyển tệp"):**
Con số quan trọng nhất là **2/3 MAU không phải designer** và **30% là developer** — nó chứng minh bằng số, không phải suy đoán, rằng Figma đã dịch chuyển từ "công cụ cho designer" sang "nền tảng cho cả product team". Con số **70% deal enterprise bắt nguồn từ 1 user Professional** giải thích *cơ chế* dịch chuyển: không phải Figma bán từ trên xuống (top-down sales), mà một cá nhân dùng free/professional trước, rồi kéo cả tổ chức vào — đúng mô hình bottom-up SaaS.

## 2.2 Tệp user — so sánh Early Adopters vs Tệp hiện tại

|                                              | Early adopters (2015–2017)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Tệp hiện tại (2023–2026)                                                                                                                |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Đặc điểm cụ thể**              | Product designer cá nhân/freelancer, illustrator, typographer, iconographer — được Figma chủ động mời làm "design evangelist" (người có ảnh hưởng trên Twitter thiết kế) để tạo hiệu ứng lan truyền<cite index="3-1">Figma xác định và tận dụng các "design evangelist" — người dẫn đầu ngành có lượng theo dõi riêng — mời họ làm người dùng đầu tiên để chia sẻ phản hồi</cite>, cùng target ban đầu là <cite index="5-1">typographer, illustrator và iconographer bên cạnh product designer</cite> | Cả product team: designer + developer (30% MAU) + PM + marketer + IT admin doanh nghiệp. Tệp không-designer chiếm 2/3 MAU              |
| **Quy mô đo được**                | Invite-only beta 2015, chưa có số liệu công khai                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | 13 triệu MAU, 450.000 tài khoản trả phí, 95% Fortune 500                                                                               |
| **JTBD chính**                        | "Thiết kế cộng tác thời gian thực, không cần gửi file qua lại"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | "Một nguồn sự thật duy nhất từ ý tưởng → thiết kế → code → trình bày, mọi vai trò làm chung trên 1 file"                |
| **Trước đó dùng gì / cách cũ** | Sketch (chỉ chạy trên Mac, không multiplayer) + gửi file qua Dropbox/email, dễ lệch version                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Developer dùng Zeplin/redline PDF để lấy spec; PM dùng Miro riêng cho brainstorm, PowerPoint riêng cho slide — mỗi việc một tool |

## 2.3 Phân tích đối thủ (competitor landscape) — vì sao user không dùng tool khác

| Đối thủ         | Market share / vị thế 2026                                  | Vấn đề khiến user rời bỏ / không chọn                                                                                                                                                             |
| ------------------ | ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sketch**   | Vẫn dùng ở nhóm nhỏ macOS-only, thị phần đang co lại | Chỉ chạy trên Mac, không có real-time multiplayer,<cite index="30-1">cần thêm công cụ hoặc plugin bên ngoài mới có quy trình handoff tương đương Figma</cite>                         |
| **Adobe XD** | ~1.4% designer chọn làm tool chính (khảo sát UX Tools)   | <cite index="32-1">Adobe tạm dừng phát triển XD từ cuối 2023 và ngừng bán license mới cho khách hàng mới</cite>, sau vụ thương vụ mua lại Figma bị chặn bởi cơ quan quản lý UK/EU |
| **Penpot**   | Mã nguồn mở, đang tăng ở châu Âu                      | <cite index="32-1">Được quan tâm một phần vì không phụ thuộc vào một nhà cung cấp Mỹ duy nhất</cite> — nhưng hệ sinh thái plugin còn mỏng, thiếu chiều sâu so với Figma         |
| **InVision** | ~7.6% (theo đo lường technographic)                        | Chủ yếu là tool prototype thời kỳ trước, đã bị Figma vượt qua khi Figma tích hợp cả design + prototype + dev handoff vào 1 sản phẩm                                                     |

**Khảo sát độc lập xác nhận vị thế:** <cite index="33-1">Khảo sát UX Tools 2024 Design Tools Survey (n=2.220 designer, 11/2024–1/2025) ghi nhận Figma chiếm 82,3% designer chọn làm công cụ chính, bỏ xa Sketch với tỉ lệ khoảng 46:1</cite>. Đây là bằng chứng độc lập, không do Figma tự công bố — có giá trị đối chiếu cao hơn số liệu tự báo cáo của công ty.

## 2.4 Painpoint cụ thể theo từng vai trò (dựa trên review G2 thật + khảo sát ngành)

### Painpoint của developer (nhóm 30% MAU) — vì sao Dev Mode ra đời

- <cite index="40-1">Theo báo cáo "State of the Designer 2025" của chính Figma, 92% designer và 91% developer cho rằng quy trình handoff thiết kế → code vẫn còn nhiều điểm cần cải thiện</cite>.
- Trước Dev Mode: developer phải tự đoán khoảng cách, màu sắc, token bằng mắt hoặc hỏi lại designer qua Slack — <cite index="38-1">trước khi có công cụ này, khoảng trống đó được lấp bằng mockup tĩnh, PDF redline, và rất nhiều tin nhắn qua lại kiểu "khoảng cách ở đây là bao nhiêu?"</cite>.
- Sau Dev Mode, painpoint chưa biến mất hoàn toàn — nó chuyển dạng: <cite index="34-1">Dev Mode hữu ích cho việc đo khoảng cách và lấy asset, nhưng phần xuất CSS vẫn còn nhiều hạn chế, khoảng cách giữa thiết kế và lập trình vẫn cần nối tay ở phần lớn trường hợp</cite>.
- Painpoint sâu hơn về nhận thức: <cite index="37-1">nhiều developer trong một khảo sát cho biết họ không biết đâu là bản thiết kế "cuối cùng" — link lỗi thời, nhánh không được gắn nhãn, thời điểm handoff không rõ ràng dẫn đến việc phải làm lại, đôi khi bị phát hiện muộn giữa sprint</cite>.

### Painpoint chung về hiệu năng (ảnh hưởng đến cả designer lẫn developer)

- <cite index="35-1">Nhiều người đánh giá trên G2 phản ánh gặp vấn đề khi làm việc với file lớn hoặc phức tạp</cite> — đây là painpoint kỹ thuật lặp lại nhất trong review thật, không phải suy đoán.
- Review G2 thật (Manojkumar D., xác thực trên G2.com): <cite index="38-1">hiệu năng có thể chậm rõ rệt trên các file rất lớn, nhiều component và layer — vấn đề này càng lộ rõ khi design system phát triển lớn dần trên nhiều sản phẩm</cite>.

**Vì sao painpoint này quan trọng cho §3 (dự đoán):** nó cho thấy dư địa cải tiến rõ ràng nhất của Figma trong 6-12 tháng tới không nằm ở "thêm tính năng mới" mà ở việc vá 2 lỗ hổng cũ: hiệu năng file lớn, và độ tin cậy của Dev Mode export — 2 painpoint này lặp lại nhất quán trên nhiều nguồn độc lập (G2, khảo sát nội bộ Figma, blog kỹ thuật bên thứ ba).

## 2.5 Dịch chuyển tệp — mốc nào gây ra, chứng minh bằng luồng nghiệp vụ cụ thể

| Mốc (Step 1)                 | Vai trò mới được kéo vào                   | Luồng nghiệp vụ cụ thể chứng minh                                                                                                                                                                                                                                                                  |
| ----------------------------- | ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FigJam ra mắt (2021)         | PM, stakeholder không chuyên thiết kế         | PM dùng FigJam để brainstorm cùng designer ngay từ giai đoạn ý tưởng, không cần biết dùng công cụ vẽ chuyên sâu                                                                                                                                                                       |
| Dev Mode (2023)               | Developer (đưa tỉ lệ developer lên ~30% MAU) | Developer vào thẳng file Figma để lấy token, đo khoảng cách, copy code snippet — thay vì chờ designer xuất file hoặc dùng Zeplin riêng                                                                                                                                                    |
| Figma Slides (2023)           | Marketer, người không code/không thiết kế   | Trình bày ngay trong Figma bằng chính component design system đã có sẵn, không cần dựng lại trong PowerPoint                                                                                                                                                                                 |
| Figma Make (2025, AI-to-code) | Developer & non-technical builder                 | <cite index="21-1">Weekly active user của Figma Make tăng hơn 70% theo quý trong Q4/2025, với hơn một nửa khách hàng trả từ $100K ARR trở lên sử dụng Make hàng tuần</cite> — cho thấy đây không phải tính năng phụ mà đang thực sự thay đổi hành vi khách hàng lớn |

**Nối trực tiếp với con số switching cost:** việc <cite index="22-1">76% khách hàng dùng từ 2 sản phẩm Figma trở lên</cite> chính là hệ quả trực tiếp của chuỗi mốc trên — mỗi sản phẩm mới không thay thế cái cũ mà cộng dồn, khiến một tổ chức càng dùng lâu thì càng khó tách rời từng phần ra dùng tool khác.

## 2.6 Switching cost — phân tích theo 4 forces (có số liệu hỗ trợ từng lực)

| Lực                                                     | Nội dung                                                                                                                                                                               | Bằng chứng                                                                                                                                         |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Push** (đẩy khỏi giải pháp cũ)             | Sketch không multiplayer, chỉ chạy Mac; Adobe XD ngừng phát triển từ 2023                                                                                                        | <cite index="32-1">Adobe tạm dừng phát triển XD cuối 2023, không bán license mới</cite>                                                      |
| **Pull** (hút vào Figma)                         | Miễn phí ở tier cơ bản, chạy trên trình duyệt bất kỳ hệ điều hành nào, hệ sinh thái hợp nhất 5 sản phẩm (Design, FigJam, Dev Mode, Slides, Make)                  | 82,3% designer chọn Figma làm tool chính (UX Tools Survey)                                                                                        |
| **Habit** (thói quen với giải pháp hiện tại) | Design system, thư viện component của tổ chức đã "sống" trong Figma nhiều năm; workflow dev đã gắn với Dev Mode                                                           | 76% khách dùng ≥2 sản phẩm Figma; 96% gross retention khách >$10K ARR                                                                          |
| **Anxiety** (nỗi lo khi chuyển đổi)            | Chuyển sang tool khác đồng nghĩa build lại toàn bộ design system, đào tạo lại cả team liên chức năng (design + dev + PM), rủi ro gián đoạn handoff đang vận hành | Gross retention 96% + 70% deal enterprise bắt nguồn từ user Professional cũ — cho thấy một khi đã "cắm rễ" thì gần như không rời đi |

**Kết luận phần này:** lực **Habit + Anxiety** hiện là lực mạnh nhất giữ chân Figma — không phải vì Figma "tốt nhất tuyệt đối" (painpoint hiệu năng và Dev Mode vẫn tồn tại thật, xem mục 2.4), mà vì chi phí rời đi (build lại design system, đào tạo lại cả product team) đã vượt xa lợi ích tiềm năng của việc chuyển sang một tool khác dù có thể tốt hơn ở vài điểm.

---

## Danh sách nguồn đã dùng (để dán vào §1 nếu trùng mốc, và để tự kiểm chứng)

1. Figma, Inc. — Form S-1, SEC EDGAR: https://www.sec.gov/Archives/edgar/data/1579878/000162828025033742/figma-sx1.htm
2. SaaStr — "Top 10 Interesting Learnings From Figma's IPO": https://www.saastr.com/top-10-interesting-learnings-from-figmas-s-1-that-you-may-have-missed/
3. SaaStr/Substack — "Top 10 Insights From Figma's IPO Docs": https://cloud.substack.com/p/top-10-insights-from-figmas-ipo-docs
4. MostlyMetrics — "Figma IPO: S-1 Breakdown": https://www.mostlymetrics.com/p/figma-ipo-s1-breakdown
5. SQ Magazine — "Figma Statistics 2026": https://sqmagazine.co.uk/figma-statistics/
6. UX Academy — "Figma vs Sketch vs Adobe XD 2026": https://myuxacademy.com/blog/figma-vs-sketch/
7. Art of Styleframe — UX Tools 2024 Design Tools Survey citation: https://artofstyleframe.com/blog/best-ui-design-tools-2026-compared/
8. G2.com — Figma Pros and Cons (review thật của user): https://www.g2.com/products/figma/reviews?qs=pros-and-cons
9. CrazyEgg — "Figma Review: The Good and Bad": https://www.crazyegg.com/blog/figma-review/
10. The Marketing Agency — "Figma Review: My Honest Take for 2026": https://themarketingagency.ca/blog/figma-review/
11. Design Thinker (Substack) — khảo sát developer dùng Dev Mode: https://johnrubino.substack.com/p/i-ran-a-study-on-how-engineers-actually
12. DEV Community — "91% of Teams Say Design Handoff Is Broken" (trích Figma State of the Designer 2025): https://dev.to/hunterstein/91-of-teams-say-design-handoff-is-broken-heres-how-to-fix-it-with-figma-to-azure-5h7
13. Figma Blog — "Reflecting on Figma's First Year": https://www.figma.com/blog/reflecting-on-figmas-first-year/
14. Contrary Research — "Figma Business Breakdown & Founding Story": https://research.contrary.com/company/figma

**§3. Ba dự đoán hướng đi (6–12 tháng tới)**

**Dự đoán 1** *(loại: mở rộng tính năng / segment / mô hình kiếm tiền / đe dọa Big Tech)*

- **Dự đoán:** …
- **Lập luận:** … *(dẫn ngược về §1–§2)*

**Dự đoán 2** *(loại: …)*

- **Dự đoán:** …
- **Lập luận:** …

**Dự đoán 3** *(loại: …)*

- **Dự đoán:** …
- **Lập luận:** …

**§4. AI Log**

| Việc                             | AI làm hay nhóm làm? | Nhóm kiểm chứng/phán đoán lại thế nào?                                     |
| --------------------------------- | ----------------------- | ----------------------------------------------------------------------------------- |
| tổng hợp các nguồn của Figma | AI làm                 | tổng hợp lại, tìm thêm thông tin và xác minh các nguồn do AI tìm được |
|                                   |                         |                                                                                     |
