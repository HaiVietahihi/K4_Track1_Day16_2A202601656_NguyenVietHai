# Memo Teardown — Figma

**Thành viên nhóm:**

| # | Họ và tên | MSSV |
|---|---|---|
| 1 | Nguyễn Hoàng Minh | 2A202601764 |
| 2 | Nguyễn Việt Hải | 2A202601656 |
| 3 | Trịnh Hải Đăng | 2A20601602 |

**Vì sao chọn sản phẩm này:** (1–2 câu)

Vì trước thời điểm AI bùng nổ, Figma là một công cụ mạnh mẽ dành cho những người làm về thiết kế UI/UX. Nhưng sau khi AI bùng nổ với sự xuất hiện của Claude design, Figma trở thành công cụ mọi người không sử dụng phổ biến nữa 

**§1. Timeline các cập nhật lớn**

| Thời điểm | Cập nhật | Context lúc đó | Nguyên lý | Nguồn |
| -----------| ----------| ----------------| -----------| -------|
| 05/2025 | Figma Make ra mắt | Config 2025: prompt-to-app sinh code thật (React/Tailwind), neo vào design system của khách hàng. Đối thủ AI-native (v0, Lovable, Replit) đã chiếm không gian "prompt-to-app"; Figma vừa trải qua khủng hoảng Make Design 2024. | Học qua vòng lặp — sửa lỗ hổng thất bại 1 năm trước (thiếu domain context) bằng cách sinh code neo vào design system thật thay vì model chung. | [Config 2025 press release](https://www.figma.com/blog/config-2025-press-release/) |
| 05/2025 | Figma Buzz ra mắt | Config 2025: công cụ cho team marketing/brand tạo hàng loạt asset từ template khoá-brand, bulk multi-edit, tích hợp sinh ảnh AI (gpt-image-1, Gemini). Ra mắt cùng Make, Sites, Draw — tham vọng thay thế Illustrator/Canva/Webflow. | Mở rộng thị trường ngang: nhắm tới marketing/brand team, không chỉ mở rộng use case nội bộ; chiến lược cạnh tranh đa mặt. | [Config 2025 press release](https://www.figma.com/blog/config-2025-press-release/) |
| 06/2025 | Dev Mode MCP Server (beta) | Hệ sinh thái AI coding agent bùng nổ nhưng agent thiếu context thiết kế chính xác; agent hay đoán sai khi không có thiết kế làm nguồn chân thực. | Phòng vệ chống "wrapper mỏng" — biến data thiết kế thành hạ tầng context không thể thay thế, cung cấp context trực tiếp cho agent thay vì cạnh tranh trực diện. | [Introducing Figma MCP Server](https://www.figma.com/blog/introducing-figma-mcp-server/) |
| 10/2025 | Mua Weavy (Figma Weave) | Figma mua Weavy (Tel Aviv, 2024) >$200M; Weave vận hành độc lập, tích hợp nhiều model AI (Seedance, Sora, Veo, Flux, Ideogram) cho ảnh/video/animation/VFX. | Vertical AI = AI Expert + Domain Expert — mua đội domain expert để tránh làm hời hợt, và giữ độc lập trước khi tích hợp vào core để tránh lặp lại sai lầm 2024. | [Welcome Weavy to Figma](https://www.figma.com/blog/welcome-weavy-to-figma/) |
| 12/2025 → 2026 | Hệ thống quản trị AI credit | Sau khi Make/Weave/agent chạy rộng, chi phí inference tăng nhanh và khó dự đoán; nhiều khiếu nại về credit, usage bất thường. | "You can't just ship and forget" — PM AI phải xây vòng lặp monitor · cost · iterate liên tục; chi phí AI biến thiên khác biệt so với phần mềm deterministic. | [Release notes: AI credit usage history](https://www.figma.com/release-notes/archive/?title=ai-credit-usage-history) |
| 06/2026 | Config 2026: code layers trên canvas + Figma agent | Ranh giới design vs code bị xóa nhòa; Figma agent có skill/connector/shared chat; đối thủ AI-gốc đe dọa lãnh thổ cốt lõi. | Biến canvas thành nơi tích luỹ domain expertise của designer (đóng gói qua "skill"); thứ model chung không có — củng cố lợi thế cạnh tranh theo hướng Vertical AI. | [Config 2026 recap](https://www.figma.com/blog/config-2026-recap/) |

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
| Net Dollar Retention (khách >$10K ARR)                                    | 132% → **139%** → **136%**          | S-1 (T3/2025) → Q1 FY2026 → Q2 FY2026 | S-1; [Figma Q2 2026 results](https://investor.figma.com/news-events/news/news-details/2026/Figma-Announces-Second-Quarter-2026-Financial-Results/default.aspx) |
| Doanh thu quý gần nhất                                                    | **$370M, +48% YoY** (quý thứ 3 liên tiếp tăng tốc) | Q2 FY2026 (công bố 5/8/2026) | [Businesswire — Figma Q2 2026](https://www.businesswire.com/news/home/20260805158853/en/Figma-Announces-Second-Quarter-2026-Financial-Results) |
| Khách >$10K ARR dùng AI credit hàng tuần                                  | **>80%**                                 | Q2 FY2026             | [Figma Q2 earnings call](https://www.fool.com/earnings/call-transcripts/2026/08/12/figma-fig-q2-2026-earnings-call-transcript/) |
| Khách >$10K ARR dùng Figma agent hàng tuần                                | **>50%**                                 | Q2 FY2026             | [Figma Q2 earnings call](https://www.fool.com/earnings/call-transcripts/2026/08/12/figma-fig-q2-2026-earnings-call-transcript/) |
| Giá cổ phiếu FIG                                                          | **−52% trong H1/2026** (dù doanh thu +46–48%) | 30/6/2026             | [Motley Fool — Why Figma Stock Lost 52%](https://www.fool.com/investing/2026/07/10/why-figma-stock-lost-52-in-the-first-half-of-2026/) |
| Gross Retention (khách >$10K ARR)                                        | **96%**                              | T3/2025               | [SaaStr Insights](https://cloud.substack.com/p/top-10-insights-from-figmas-ipo-docs)                                     |
| Khách hàng >$100K ARR                                                   | 1,031 → 1,405                             | Q1/2025 → Q4/2025    | S-1; SQ Magazine                                                                                                        |
| Khách hàng >$1M ARR                                                     | 40+ → 67 (+68% YoY)                       | T3/2025 → Q4/2025    | [MostlyMetrics](https://www.mostlymetrics.com/p/figma-ipo-s1-breakdown); SQ Magazine                                     |
| Deal Organization/Enterprise mới bắt nguồn từ 1 user Professional cũ | **70%**                              | 2024 & Q1/2025        | SaaStr, MostlyMetrics                                                                                                   |
| Fortune 500 dùng Figma                                                   | 95%                                        | T3/2025               | SQ Magazine                                                                                                             |

**Đọc số liệu này ra sao (đây là bằng chứng định lượng cho phần "dịch chuyển tệp"):**
Con số quan trọng nhất là **2/3 MAU không phải designer** và **30% là developer** — nó chứng minh bằng số, không phải suy đoán, rằng Figma đã dịch chuyển từ "công cụ cho designer" sang "nền tảng cho cả product team". Con số **70% deal enterprise bắt nguồn từ 1 user Professional** giải thích *cơ chế* dịch chuyển: không phải Figma bán từ trên xuống (top-down sales), mà một cá nhân dùng free/professional trước, rồi kéo cả tổ chức vào — đúng mô hình bottom-up SaaS.

> **⚠️ Đính chính giả định mở đầu memo.** Câu "Figma trở thành công cụ mọi người không sử dụng phổ biến nữa" **không đúng với dữ liệu**: doanh thu Q2 FY2026 tăng **48% YoY**, NDR **136%**, thị phần designer **82,3%**. Thứ đang sụt là **niềm tin của thị trường vốn**, không phải mức độ sử dụng — cổ phiếu FIG mất **52% trong H1/2026** vì nhà đầu tư sợ Claude Design / Lovable / Google Stitch sẽ làm công cụ thiết kế truyền thống trở nên không cần thiết ([Motley Fool](https://www.fool.com/investing/2026/07/10/why-figma-stock-lost-52-in-the-first-half-of-2026/), [IndexBox](https://www.indexbox.io/blog/figma-stock-drops-16-in-april-2026-as-ai-competition-fears-intensify/)). **Khoảng cách giữa "usage vẫn tăng" và "định giá vẫn giảm" chính là câu hỏi trung tâm của §3** — thị trường đang đặt cược rằng số liệu hiện tại là chỉ báo trễ (lagging indicator).

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
| **InVision** | **Đã đóng cửa hoàn toàn 31/12/2024** — không còn là đối thủ | Bị Figma vượt qua khi Figma gộp design + prototype + dev handoff vào 1 sản phẩm; công ty từng được định giá $2B đã ngừng dịch vụ và xoá dữ liệu người dùng cuối 2024 ([Fast Company](https://www.fastcompany.com/91006037/invision-former-ux-trailblazer-ending-services-figma-adobe)) |

> **⚠️ Lỗi khung phân tích đã sửa.** Bảng trên chỉ trả lời câu hỏi *"vì sao Figma thắng cuộc chiến 2016–2024"* — tất cả 4 đối thủ đều đã chết (InVision), đóng băng (XD), hoặc co lại (Sketch). **Nó không trả lời câu hỏi của 2026.** §1 xác định mối đe doạ là AI-native (v0, Lovable, Replit), nhưng §2.3 bản gốc không có tên nào trong số đó → phân tích switching cost ở §2.6 vì thế trông vững hơn thực tế. Bảng bổ sung dưới đây vá lỗ hổng này.

### 2.3b Đối thủ thế hệ AI-native (đây mới là mặt trận 2026)

| Đối thủ | Vị thế 2026 | Vì sao nguy hiểm với Figma | Vì sao chưa thay thế được Figma |
|---|---|---|---|
| **Lovable** | **$400M ARR (T2/2026)**; từ 0 → $20M ARR trong 2 tháng — nhanh nhất lịch sử startup châu Âu | Bỏ qua hoàn toàn bước thiết kế: prompt → full-stack app có Supabase, auth, deploy 1 click | Không có design system, không có handoff nhiều vai trò, không phải "nguồn sự thật" cho tổ chức |
| **Claude Design (Anthropic)** | Ra mắt 2026; là nguyên nhân trực tiếp khiến FIG **giảm 16% riêng T4/2026** ([IndexBox](https://www.indexbox.io/blog/figma-stock-drops-16-in-april-2026-as-ai-competition-fears-intensify/)) | Tấn công đúng lõi: sinh giao diện chất lượng cao mà không cần canvas | **Figma đã chọn bắt tay thay vì đối đầu** — xem "Code to Canvas" 17/2/2026 ở §2.5 |
| **Google Stitch** | Bản cập nhật T3/2026 (voice canvas + infinite canvas) khiến **cổ phiếu Figma rớt 12%** | Google có phân phối miễn phí + model in-house, không chịu áp lực inference cost như Figma | Chưa có hệ sinh thái plugin, chưa có enterprise governance |
| **v0 (Vercel)** | Sinh React/Tailwind chất lượng cao, hỗ trợ Figma-to-code | Chiếm luôn khâu "design → code" mà Dev Mode đang bảo vệ | Không có backend/database/auth; vẫn phải lấy Figma làm nguồn thiết kế |

**Hệ quả cho §3:** thị trường công cụ thiết kế lần đầu sau một thập kỷ **không còn là độc quyền Figma**. Điều này giải thích vì sao mọi động thái ở §1 từ 2025 trở đi (MCP, Weave, Make, Code Layers) đều mang hình dạng **phòng thủ có tính mở rộng**, chứ không phải mở rộng thuần tuý.

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
| Figma Slides (beta 26/6/2024 tại Config 2024, GA đầu 2025) | Marketer, người không code/không thiết kế   | Trình bày ngay trong Figma bằng chính component design system đã có sẵn, không cần dựng lại trong PowerPoint *(bản gốc memo ghi nhầm 2023 — đã sửa theo [Figma Blog](https://www.figma.com/blog/introducing-figma-slides/))* |
| Figma Make (2025, AI-to-code) | Developer & non-technical builder                 | <cite index="21-1">Weekly active user của Figma Make tăng hơn 70% theo quý trong Q4/2025, với hơn một nửa khách hàng trả từ $100K ARR trở lên sử dụng Make hàng tuần</cite> — cho thấy đây không phải tính năng phụ mà đang thực sự thay đổi hành vi khách hàng lớn |
| **AI credit enforcement (11/3 & 18/3/2026)** | Không kéo vai trò mới — mà **đổi quan hệ kinh tế với mọi vai trò cũ** | Từ "trả tiền theo ghế, dùng bao nhiêu cũng được" → "ghế + hạn mức tiêu thụ". Mỗi seat có định mức (3.000 credit/Professional, 3.500/Organization, 4.250/Enterprise, 500 cho Dev/Collab/View); hết thì mua thêm ở mức $0,03/credit. **Đây là dịch chuyển lớn nhất chưa được bản gốc ghi nhận**, vì nó biến user thành người phải cân nhắc chi phí mỗi lần prompt ([Figma Help](https://help.figma.com/hc/en-us/articles/33459875669015-How-AI-credits-work)) |
| **Code to Canvas — hợp tác Anthropic (17/2/2026)** | Người dùng Claude Code / AI coding agent — tệp **chưa từng mở Figma** | Sinh giao diện bằng Claude Code → gõ "Send this to Figma" → UI thành layer Figma **sửa được**. Figma tự đặt mình ở *cuối* luồng AI thay vì đầu luồng ([CNBC](https://www.cnbc.com/2026/02/17/figma-anthropic-ai-code-designs.html)) |
| **Config 2026 (24/6/2026): Code Layers, Motion, Agent + connectors** | Developer sâu hơn (Git), motion designer, và **người dùng của Notion/Slack/GitHub/Atlassian** | Code Layers giữ **liên kết hai chiều sống với code Git-tracked** → file thiết kế và codebase thành *cùng một artifact*. Agent nối ra Notion/Slack/GitHub/Atlassian → Figma trở thành nơi công việc *bắt đầu*, không chỉ nơi thiết kế ([Config 2026 recap](https://www.figma.com/blog/config-2026-recap/)) |

**Nối trực tiếp với con số switching cost:** việc <cite index="22-1">76% khách hàng dùng từ 2 sản phẩm Figma trở lên</cite> chính là hệ quả trực tiếp của chuỗi mốc trên — mỗi sản phẩm mới không thay thế cái cũ mà cộng dồn, khiến một tổ chức càng dùng lâu thì càng khó tách rời từng phần ra dùng tool khác.

## 2.6 Switching cost — phân tích theo 4 forces (có số liệu hỗ trợ từng lực)

| Lực                                                     | Nội dung                                                                                                                                                                               | Bằng chứng                                                                                                                                         |
| -------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Push** (đẩy khỏi giải pháp cũ)             | Sketch không multiplayer, chỉ chạy Mac; Adobe XD ngừng phát triển từ 2023                                                                                                        | <cite index="32-1">Adobe tạm dừng phát triển XD cuối 2023, không bán license mới</cite>                                                      |
| **Pull** (hút vào Figma)                         | Miễn phí ở tier cơ bản, chạy trên trình duyệt bất kỳ hệ điều hành nào, hệ sinh thái hợp nhất 5 sản phẩm (Design, FigJam, Dev Mode, Slides, Make)                  | 82,3% designer chọn Figma làm tool chính (UX Tools Survey)                                                                                        |
| **Habit** (thói quen với giải pháp hiện tại) | Design system, thư viện component của tổ chức đã "sống" trong Figma nhiều năm; workflow dev đã gắn với Dev Mode                                                           | 76% khách dùng ≥2 sản phẩm Figma; 96% gross retention khách >$10K ARR                                                                          |
| **Anxiety** (nỗi lo khi chuyển đổi)            | Chuyển sang tool khác đồng nghĩa build lại toàn bộ design system, đào tạo lại cả team liên chức năng (design + dev + PM), rủi ro gián đoạn handoff đang vận hành | Gross retention 96% + 70% deal enterprise bắt nguồn từ user Professional cũ — cho thấy một khi đã "cắm rễ" thì gần như không rời đi |

> **⚠️ Lỗi thời điểm phân tích đã sửa.** Bảng 4 forces ở trên đang phân tích **cuộc chuyển đổi Sketch → Figma (2016–2020)**, không phải cuộc chuyển đổi đang diễn ra. Trong 4 forces, "Push" phải là lực đẩy user **rời khỏi giải pháp hiện tại của họ** — mà giải pháp hiện tại của user năm 2026 chính là **Figma**. Bảng dưới đây làm lại 4 forces cho đúng thời điểm 2026, và đây mới là cơ sở hợp lệ để dự đoán ở §3.

### 2.6b Bốn lực cho cuộc chuyển đổi ĐANG diễn ra (Figma → AI-native), tính đến 8/2026

| Lực | Nội dung | Bằng chứng | Cường độ |
|---|---|---|---|
| **Push** — đẩy user rời Figma | (1) Chi phí AI credit trở thành khoản phải cân nhắc: hết định mức là $0,03/credit, 10.000 credit/tháng = $3.600/năm. (2) Hiệu năng file lớn vẫn kém (§2.4). (3) Với người chỉ cần "một app chạy được", quy trình canvas là bước thừa | [Figma Help — AI credits](https://help.figma.com/hc/en-us/articles/33459875669015-How-AI-credits-work); review G2 §2.4 | **Trung bình — và đang tăng** |
| **Pull** — hút sang AI-native | Lovable đi từ prompt thẳng ra app có backend/auth/deploy, **$400M ARR T2/2026**; Google Stitch miễn phí, có phân phối Google | [Lovable ARR](https://muz.li/blog/lovable-for-designers-the-complete-guide-to-building-apps-with-ai-2026/); [Stitch tác động cổ phiếu](https://www.nxcode.io/resources/news/vibe-design-tools-compared-stitch-v0-lovable-2026) | **Mạnh với cá nhân / startup nhỏ; yếu với enterprise** |
| **Habit** — giữ ở Figma | Design system + thư viện component của tổ chức đã sống trong Figma nhiều năm; 76% khách dùng ≥2 sản phẩm; **>80% khách >$10K ARR dùng AI credit hàng tuần**, tức thói quen AI cũng đã hình thành *bên trong* Figma | S-1; [Figma Q2 FY2026](https://www.fool.com/earnings/call-transcripts/2026/08/12/figma-fig-q2-2026-earnings-call-transcript/) | **Rất mạnh** |
| **Anxiety** — sợ rời đi | Rời đi = build lại design system, đào tạo lại cả team liên chức năng, mất governance/audit trail mà AI-native chưa có; **96% gross retention** khách >$10K ARR | S-1; SaaStr | **Rất mạnh ở enterprise, yếu ở cá nhân** |

**Đọc bảng này ra sao:** Push và Pull đang mạnh lên ở **đầu phễu** (cá nhân, freelancer, startup — nhóm mà Lovable/Stitch phục vụ tốt và rẻ hơn), trong khi Habit và Anxiety vẫn giữ chặt **đuôi phễu** (enterprise). Đó chính xác là hình dạng của **NDR 136% + doanh thu +48% nhưng cổ phiếu −52%**: doanh thu hôm nay đến từ đuôi phễu đã khoá chặt, còn thị trường lo về đầu phễu đang rò rỉ. **Mô hình bottom-up "70% deal enterprise bắt nguồn từ 1 user Professional" (§2.1) là chỗ dễ tổn thương nhất** — nếu người dùng cá nhân mới bắt đầu bằng Lovable thay vì Figma, đường ống enterprise của 3–5 năm sau sẽ cạn, dù số liệu năm nay vẫn rất đẹp.

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

**Nguồn bổ sung (thêm khi kiểm chứng lại §2 và dựng §3 — tất cả từ 2026):**

15. Figma IR — "Figma Announces Second Quarter 2026 Financial Results" (5/8/2026): https://investor.figma.com/news-events/news/news-details/2026/Figma-Announces-Second-Quarter-2026-Financial-Results/default.aspx
16. Motley Fool — Figma (FIG) Q2 2026 Earnings Call Transcript: https://www.fool.com/earnings/call-transcripts/2026/08/12/figma-fig-q2-2026-earnings-call-transcript/
17. Motley Fool — "Why Figma Stock Lost 52% in the First Half of 2026": https://www.fool.com/investing/2026/07/10/why-figma-stock-lost-52-in-the-first-half-of-2026/
18. IndexBox — "Figma Stock Falls 16% in April 2026 Amid Anthropic AI Disruption Concerns": https://www.indexbox.io/blog/figma-stock-drops-16-in-april-2026-as-ai-competition-fears-intensify/
19. CNBC — "Figma partners with Anthropic to turn AI-generated code into editable designs" (17/2/2026): https://www.cnbc.com/2026/02/17/figma-anthropic-ai-code-designs.html
20. Figma Developer Docs — Code to canvas: https://developers.figma.com/docs/figma-mcp-server/code-to-canvas/
21. Figma Help Center — "How AI credits work" (định mức credit theo seat, giá $0,03/credit): https://help.figma.com/hc/en-us/articles/33459875669015-How-AI-credits-work
22. Figma Blog — "Updates to AI Credits in Figma": https://www.figma.com/blog/updates-to-ai-credits-in-figma/
23. Figma Blog — "Stack the deck with Figma Slides" (26/6/2024 — dùng để đính chính năm ra mắt Slides): https://www.figma.com/blog/introducing-figma-slides/
24. Fast Company — "InVision, former UX trailblazer, is shutting down in the era of Figma": https://www.fastcompany.com/91006037/invision-former-ux-trailblazer-ending-services-figma-adobe
25. Muzli — "Lovable for Designers" (số liệu $400M ARR T2/2026): https://muz.li/blog/lovable-for-designers-the-complete-guide-to-building-apps-with-ai-2026/
26. NxCode — "Vibe Design Tools 2026: Stitch vs v0 vs Lovable vs Bolt": https://www.nxcode.io/resources/news/vibe-design-tools-compared-stitch-v0-lovable-2026
27. CMSWire — "Figma Launches Code Layers & Motion at Config 2026": https://www.cmswire.com/digital-experience/figma-launches-code-layers-motion-at-config-2026/

**§3. Ba dự đoán hướng đi (6–12 tháng tới)**

**Cửa sổ dự đoán: 8/2026 → 8/2027** (mốc kiểm chứng chính: Config 2027, khoảng 6/2027, và 4 kỳ báo cáo tài chính Q3 FY2026 → Q2 FY2027).

**Nguyên tắc lập dự đoán (để tránh đoán mò).** Không dự đoán nào dưới đây được rút ra từ cảm tính. Cả ba đều xây trên ba loại bằng chứng có thể kiểm chứng độc lập: (1) **cam kết công khai đã có** — thứ Figma đã lên waitlist, đã beta, đã ký đối tác; (2) **ràng buộc tài chính** — thứ một công ty niêm yết *buộc* phải làm khi guidance đã hứa với nhà đầu tư; (3) **phát ngôn của ban lãnh đạo trên earnings call** — có giá trị pháp lý, không phải marketing. Mỗi dự đoán đều kèm **điều kiện phản chứng** (điều gì xảy ra thì dự đoán này SAI) — vì một dự đoán không thể sai được thì cũng không có giá trị.

---

### Dự đoán 1 — *(loại: mô hình kiếm tiền)*

> **Dự đoán:** Trong 6–12 tháng tới, Figma sẽ **bật tính phí AI credit cho nhóm tính năng hiện đang miễn phí trong beta** — Figma agent, Code Layers, Motion, generative plugins, Make on local code — và hoàn tất chuyển từ mô hình thuần seat sang **hybrid seat + consumption**. Kèm theo đó, Figma sẽ **nâng định mức credit kèm seat** (thay vì tăng giá seat trực diện) để giữ vẻ ngoài "không tăng giá", và tiếp tục đẩy gói **AI credit subscription** (mở bán 11/3/2026) thành kênh doanh thu được nhắc riêng trong báo cáo.

**Lập luận — chuỗi bằng chứng dẫn ngược về §1–§2:**

1. **§1 đã ghi đúng nguyên lý, chỉ chưa ghi hệ quả.** Mốc 12/2025→2026 "hệ thống quản trị AI credit" với nguyên lý *"You can't just ship and forget"* đã đặt nền hạ tầng đo đếm. Hạ tầng đo đếm chỉ tồn tại để phục vụ một việc: **tính tiền**. Ngày 11/3/2026 Figma mở bán gói credit; ngày 18/3/2026 **enforce cứng hạn mức mọi seat** — hạ tầng đã chuyển từ quan sát sang thu phí.

2. **Ban lãnh đạo đã tự nói ra phần còn thiếu.** Trên earnings call Q2 FY2026, CFO Praveer Melwani nêu rõ: *agent, Make on local code, Motion, generative plugins và Code Layers **chưa tiêu credit trả phí** khi còn ở beta/early access, và điều đó **gây áp lực lên gross margin cho tới khi bắt đầu monetize***. Đây không phải suy đoán của nhóm — đây là ban lãnh đạo **thông báo trước ý định** cho nhà đầu tư. Từ "cho tới khi" (*before monetization begins*) là cam kết về thì tương lai.

3. **Ràng buộc tài chính khiến việc này gần như bắt buộc.** Figma nâng guidance cả năm thêm $40M lên $1,463–1,467 tỷ **nhưng giữ nguyên dự báo lợi nhuận hoạt động** → không có dư địa hy sinh margin để mua thị phần. Cùng lúc, **chi phí inference AI là yếu tố lớn nhất kéo dòng tiền tự do giảm YoY**. Một công ty niêm yết bị nén margin bởi chi phí biến đổi, đã hứa lợi nhuận với nhà đầu tư, và đang cho hàng loạt tính năng đắt tiền chạy miễn phí — chỉ có hai lối ra: tính phí, hoặc cắt tính năng. Cắt tính năng là tự sát trước Lovable/Claude Design.

4. **Willingness-to-pay đã được kiểm chứng bằng thực nghiệm, không phải khảo sát.** Sau khi enforce hạn mức giữa T3/2026: **>75% khách enterprise chạm trần credit đã chọn trả thêm** thay vì dừng lại, và **>80% khách >$10K ARR tiêu credit hàng tuần**. Đây là dữ liệu hành vi có trả tiền thật — loại bằng chứng mạnh nhất trong product thinking.

5. **Vì sao là "nâng định mức" chứ không phải "tăng giá seat":** §2.6b cho thấy lực **Push** (đẩy user rời Figma) hiện đến chủ yếu từ *cảm giác chi phí AI khó lường*. Tăng giá seat sẽ kích hoạt lực Push đó ở đúng nhóm đầu phễu đang rò rỉ. Nâng định mức kèm seat thì ngược lại — nó *giảm* lo lắng, đồng thời vẫn tăng ARPU vì nhóm dùng nhiều vẫn phải mua thêm. Đây là nước đi có lợi ở cả hai phía.

**Điều gì làm dự đoán này SAI:** nếu đến Config 2027 (≈6/2027) Code Layers và Figma agent ra bản GA mà **vẫn không tiêu credit trả phí**, hoặc Figma công bố **bỏ hẳn credit quay lại unlimited theo seat**. Kịch bản này chỉ hợp lý nếu Figma quyết định hy sinh lợi nhuận để chặn Lovable — nhưng guidance giữ nguyên operating income đã loại phần lớn khả năng đó.

---

### Dự đoán 2 — *(loại: đe dọa Big Tech / định vị cạnh tranh)*

> **Dự đoán:** Figma sẽ **không đối đầu trực diện** với các AI-native. Thay vào đó, trong 6–12 tháng tới Figma sẽ **mở rộng mô hình "Code to Canvas" ra ít nhất một đối tác agent lớn nữa ngoài Anthropic** (ứng viên khả dĩ nhất: OpenAI, Google, Cursor, hoặc GitHub Copilot), và biến Figma thành **lớp trung lập (neutral layer) mà mọi AI coding agent đều đi qua** — thay vì cố thắng cuộc đua sinh code.

**Lập luận — chuỗi bằng chứng dẫn ngược về §1–§2:**

1. **Đây là nguyên lý §1 đã nhận diện, chỉ cần đọc tiếp một bước.** Mốc 6/2025 (MCP Server) được §1 ghi nguyên lý *"phòng vệ chống wrapper mỏng — biến data thiết kế thành hạ tầng context không thể thay thế, cung cấp context trực tiếp cho agent thay vì cạnh tranh trực diện"*. **"Thay vì cạnh tranh trực diện"** chính là chiến lược, và Figma đã thi hành nó nhất quán suốt 12 tháng sau đó.

2. **Bằng chứng quyết định: Figma đã bắt tay chính đối thủ đáng sợ nhất của mình.** Ngày **17/2/2026**, Figma và Anthropic công bố **Code to Canvas** — người dùng sinh giao diện bằng Claude Code rồi gõ *"Send this to Figma"* để biến nó thành layer sửa được. Hãy đọc kỹ mức độ nghịch lý ở đây: **Claude Design là nguyên nhân trực tiếp khiến cổ phiếu FIG rớt 16% chỉ trong tháng 4/2026**, vậy mà Figma chọn tích hợp với chính Anthropic. Đó không phải mâu thuẫn — đó là chiến lược có ý thức: *nếu không thắng được ở khâu sinh, hãy sở hữu khâu tinh chỉnh và thống nhất*.

3. **Config 2026 xác nhận hướng "hub", không phải "silo".** Figma agent giờ nối ra **Notion, Slack, GitHub, Atlassian**. Code Layers giữ **liên kết hai chiều sống với code Git-tracked**, biến file thiết kế và codebase thành cùng một artifact. Không có động thái nào trong số này là "làm model tốt hơn Anthropic" — tất cả đều là "làm chỗ hội tụ tốt hơn bất kỳ ai".

4. **§2.1 cho thấy vì sao Figma buộc phải đi đường này.** **30% MAU là developer** — nhóm này chỉ ở lại nếu Figma nằm trên đường đi công việc của họ. Mà đường đi công việc của developer năm 2026 chạy qua AI coding agent. Cạnh tranh với agent = tự đẩy 30% MAU ra ngoài; tích hợp với agent = giữ họ lại mà không cần thắng.

5. **§2.6b giải thích vì sao đây là nước đi tối ưu chứ không phải nước đi yếu.** Interoperability đánh thẳng vào lực **Anxiety**: user không còn phải "chọn phe" giữa Figma và AI agent. Đồng thời nó vô hiệu hoá lực **Pull** của đối thủ — nếu dùng Lovable/Claude xong vẫn đưa về Figma được, thì lý do *rời bỏ* Figma biến mất, chỉ còn lý do *dùng thêm*.

6. **Nền tảng kỹ thuật đã sẵn sàng để nhân rộng.** Code to Canvas chạy trên **Figma MCP** — một giao thức mở, không phải tích hợp riêng cho Anthropic. Chi phí biên để thêm đối tác thứ hai là thấp; đây là dấu hiệu kiến trúc cho thấy Figma *thiết kế sẵn* cho nhiều đối tác ngay từ đầu.

**Điều gì làm dự đoán này SAI:** nếu Figma ký **thoả thuận độc quyền** với Anthropic, hoặc đóng MCP thành giao thức riêng, hoặc tung model sinh thiết kế first-party và định vị nó **đối đầu trực tiếp** với Claude Design/Stitch. Tín hiệu cảnh báo sớm cần theo dõi: phát biểu của Melwani về **"first-party models"** như đòn bẩy giảm chi phí inference — nếu first-party model chuyển từ *giảm chi phí* sang *vũ khí cạnh tranh*, dự đoán này cần xem lại.

---

### Dự đoán 3 — *(loại: mở rộng segment)*

> **Dự đoán:** Động cơ tăng trưởng của Figma trong 6–12 tháng tới sẽ **dịch từ "bán thêm ghế designer" sang "bán thêm loại công việc cho tài khoản enterprise đã có"** — cụ thể là gộp **Weave + Motion + Buzz** thành một hướng đi cho **marketing/content/motion team**. Biểu hiện kiểm chứng được: Weave sẽ **hết vận hành độc lập và tích hợp vào canvas chính**, và Figma sẽ công bố chỉ số dạng "**số sản phẩm trung bình mỗi khách hàng**" hoặc tỉ lệ non-designer **vượt mốc 2/3 hiện tại**.

**Lập luận — chuỗi bằng chứng dẫn ngược về §1–§2:**

1. **§2.1 cho thấy động cơ tăng trưởng thật của Figma chưa bao giờ là designer.** **76% khách hàng dùng ≥2 sản phẩm, tăng từ 64% chỉ trong một năm** — đây là chỉ số tăng nhanh nhất trong toàn bộ hồ sơ S-1. Cộng với **NDR 136%**: phần lớn tăng trưởng đến từ khách *cũ chi nhiều hơn*, không phải khách mới. Trong SaaS, khi NDR là động cơ chính thì cross-sell luôn thắng acquisition về ROI.

2. **§1 cho thấy Figma đã mua sẵn nguyên liệu và đang lắp ráp.** Figma chi **>$200M mua Weavy (10/2025)** — đội chuyên ảnh/video/animation/VFX với Seedance, Sora, Veo, Flux, Ideogram. Nguyên lý §1 ghi đúng: *"giữ độc lập trước khi tích hợp vào core để tránh lặp lại sai lầm 2024"*. **Chữ "trước khi" hàm ý một mốc tích hợp đang tới.** Tại Config 2026, Weave Tools đã được nối vào canvas Figma với template publishing khả dụng ngay và **tool publishing "sắp có"** — quá trình tích hợp đã bắt đầu, chưa kết thúc. Dự đoán này chỉ là đọc tiếp quỹ đạo đó.

3. **Figma Motion đã GA, không còn beta.** Config 2026 ra Motion với timeline, keyframe, preset, sinh bằng AI, xuất CSS/JSON/React/MP4/WebM/SVG/GIF. Một tính năng vừa xuất **video MP4** vừa xuất **React** không nhắm vào một tệp user duy nhất — nó nhắm vào **cả marketing lẫn engineering**. Đây là dấu hiệu rõ của ý đồ mở rộng segment.

4. **§2.5 đã có tiền lệ chứng minh cơ chế này hoạt động.** FigJam kéo PM vào, Dev Mode kéo developer lên **30% MAU**, Slides kéo marketer vào. **Mỗi lần Figma thêm một loại công việc, nó thêm một loại người dùng — và không lần nào bỏ loại cũ.** Weave/Motion/Buzz là lần lặp thứ tư của đúng công thức đó, chỉ khác là lần này nhắm vào công việc nội dung/thương hiệu.

5. **Cấu trúc bán hàng khiến đây là con đường ít rủi ro nhất.** **70% deal enterprise bắt nguồn từ một user Professional** và **95% Fortune 500 đã dùng Figma** — nghĩa là Figma đã ở sẵn bên trong gần như mọi tổ chức lớn. Bán thêm cho marketing team *trong tài khoản đã có* không cần giành user từ Canva, không cần chiến dịch acquisition mới, và tận dụng đúng lực **Habit** đang mạnh nhất ở §2.6b.

6. **Vì sao là *bây giờ*:** §2.6b chỉ ra đầu phễu (cá nhân, startup) đang bị Lovable/Stitch bào mòn. Khi acquisition đầu phễu khó hơn, một công ty niêm yết cần giữ tốc độ tăng trưởng sẽ **dồn lực vào chỗ mình còn ưu thế tuyệt đối** — đuôi phễu enterprise. Cross-sell vào enterprise là câu trả lời tăng trưởng duy nhất không phụ thuộc vào việc thắng cuộc chiến AI-native.

**Điều gì làm dự đoán này SAI:** nếu Figma **thu hẹp** danh mục để tập trung phòng thủ lõi design+code (dấu hiệu: khai tử hoặc đóng băng Buzz/Slides), hoặc giữ Weave vận hành độc lập vô thời hạn, hoặc Canva khoá chặt segment marketing đến mức Figma rút lui. Chỉ số cần theo dõi: nếu **tỉ lệ khách dùng ≥2 sản phẩm chững lại quanh 76–78%** trong 2–3 quý liên tiếp thì luận điểm cross-sell đã hết dư địa.

---

### Ba dự đoán này ăn khớp với nhau thế nào

Đọc riêng lẻ thì là ba dự đoán; đọc cùng nhau thì là **một chiến lược thống nhất trả lời cho nghịch lý ở §2.1: doanh thu +48% nhưng cổ phiếu −52%**.

| Dự đoán | Giải quyết vấn đề gì | Thuộc lực nào ở §2.6b |
|---|---|---|
| **1. Hybrid seat + consumption** | Chi phí inference đang bào mòn margin | Kiểm soát lực **Push** (đừng để giá đẩy user đi) trong khi vẫn thu được tiền |
| **2. Trung lập với mọi AI agent** | Đối thủ AI-native đang chiếm đầu phễu | Vô hiệu hoá lực **Pull** của đối thủ, giảm lực **Anxiety** |
| **3. Cross-sell marketing/motion** | Tăng trưởng đầu phễu đang chậm lại | Khai thác tối đa lực **Habit** ở đuôi phễu |

**Rủi ro chung của cả ba (điều nhóm không dự đoán được):** cả ba đều là nước đi **phòng thủ thông minh** ở đuôi phễu, và **không nước nào giải quyết vấn đề gốc** mà thị trường đang định giá — rằng thế hệ người dùng mới có thể bắt đầu sự nghiệp bằng Lovable hoặc Claude Design và **không bao giờ mở Figma lần đầu**. Mô hình bottom-up của Figma cần một người dùng cá nhân đi trước 3–5 năm rồi mới thành deal enterprise. Nếu đầu vào đó cạn, mọi chỉ số hiện tại vẫn đẹp trong 2–3 năm rồi mới sụp — và đó chính xác là điều **NDR 136% không thể đo được**, còn **cổ phiếu −52% thì đã đo rồi**.

**§4. AI Log**

Nhóm ghi lại đầy đủ vì đây là phần phản ánh trung thực nhất cách nhóm làm việc. Nguyên tắc xuyên suốt: **§1 và §2 do nhóm tự nghiên cứu và viết; AI chỉ vào ở vai trò kiểm chứng, phát hiện lỗi và sửa.** Chỉ riêng §3 nhóm mới để AI dựng khung bằng chứng, rồi nhóm phản biện và chốt.

**Phân công:** §1 — Hoàng Minh & Việt Hải · §2 — Hải Đăng (toàn bộ) · §3 — cả nhóm phản biện trên khung AI dựng · §4 — cả nhóm.

### 4.1 Nhật ký theo từng đầu việc

| # | Phần | Việc | Ai làm? | AI vào ở đâu / nhóm kiểm chứng lại thế nào? |
|---|---|---|---|---|
| 1 | Chọn đề | Chọn sản phẩm teardown (Figma) | **Cả nhóm** | Tự chọn vì cả 3 thành viên đều dùng Figma thật và cảm nhận được thay đổi sau khi AI bùng nổ — phán đoán từ trải nghiệm, không hỏi AI |
| 2 | **§1** | Nghiên cứu lịch sử cập nhật Figma 2024–2026, lọc ra các mốc lớn | **Hoàng Minh & Việt Hải** | Nhóm tự đọc blog Figma, release notes, tin Config để dựng danh sách mốc. AI **không** tham gia bước này |
| 3 | **§1** | Chốt 6 mốc đưa vào bảng, loại các mốc còn lại | **Hoàng Minh & Việt Hải** | Tiêu chí loại do nhóm đặt: bỏ mốc không liên quan AI, bỏ thay đổi nhỏ (ví dụ điều chỉnh số lượt dùng AI). Ghi lại lý do loại ở phần "Vì sao chọn những mốc này" |
| 4 | **§1** | Viết cột "Context lúc đó" | **Hoàng Minh & Việt Hải** | Nhóm tự dựng bối cảnh cạnh tranh từng thời điểm (v0/Lovable/Replit, khủng hoảng Make Design 2024) |
| 5 | **§1** | Viết cột "Nguyên lý" | **Hoàng Minh & Việt Hải** | Nhóm tự đối chiếu từng mốc với bài học trên lớp (học qua vòng lặp, Vertical AI = AI Expert + Domain Expert, monitor–cost–iterate) để nguyên lý *giải thích* được mốc chứ không phải nhãn dán |
| 6 | **§1** | Tìm và gắn link nguồn cho 6 mốc | **Hoàng Minh & Việt Hải** tìm link, AI điền vào bảng | Nhóm tự mở từng link kiểm tra nội dung khớp với mốc, rồi mới đưa AI điền theo đúng thứ tự |
| 7 | **§1** | *AI kiểm chứng lại* | AI check | AI đối chiếu lại timeline với nguồn 2026, xác nhận 6 mốc đều có thật và đúng thời điểm. Không phát hiện lỗi ở §1 |
| 8 | **§2** | Tra cứu và dựng toàn bộ bảng số liệu §2.1 từ hồ sơ S-1 | **Hải Đăng** | Tự chọn nguồn ưu tiên là hồ sơ pháp lý (S-1 nộp SEC) hơn blog marketing, vì hồ sơ pháp lý bị ràng buộc phải trung thực với nhà đầu tư |
| 9 | **§2** | Viết §2.2 — bảng so sánh Early adopters vs tệp hiện tại | **Hải Đăng** | Tự tra lịch sử invite-only beta 2015, chiến lược "design evangelist", và đối chiếu với số MAU hiện tại |
| 10 | **§2** | Viết §2.3 — phân tích đối thủ | **Hải Đăng** | Tự tra khảo sát UX Tools 2024, tình trạng Sketch/Adobe XD/Penpot |
| 11 | **§2** | Viết §2.4 — painpoint theo vai trò | **Hải Đăng** | Tự đọc review G2 thật, khảo sát "State of the Designer 2025", khảo sát developer dùng Dev Mode |
| 12 | **§2** | Viết §2.5 — dịch chuyển tệp theo luồng nghiệp vụ | **Hải Đăng** | Tự nối từng mốc §1 với vai trò mới được kéo vào, kèm luồng nghiệp vụ cụ thể chứng minh |
| 13 | **§2** | Viết §2.6 — switching cost theo 4 forces | **Hải Đăng** | Tự áp khung 4 forces đã học vào từng lực, kèm số liệu hỗ trợ |
| 14 | **§2** | Dựng danh sách 14 nguồn tham khảo | **Hải Đăng** | Tự truy từng số liệu về nguồn gốc để người đọc kiểm chứng lại được |
| 15 | **§2** | *AI kiểm chứng — phát hiện 4 lỗi factual* | AI check & sửa | (a) InVision đã đóng cửa hoàn toàn 31/12/2024 chứ không còn thị phần 7,6%; (b) Figma Slides ra 26/6/2024 chứ không phải 2023; (c) NDR 136% là số Q2 FY2026 chứ không phải 31/12/2025; (d) thiếu 2 mốc lớn — Code to Canvas 17/2/2026 và AI credit enforcement 3/2026. **Hải Đăng mở lại từng link đối chiếu trước khi chốt** |
| 16 | **§2** | *AI kiểm chứng — phát hiện 2 lỗi logic* | AI check & bổ sung | (a) §2.3 chỉ có đối thủ thế hệ cũ đã chết/đóng băng, thiếu AI-native → thêm §2.3b; (b) §2.6 phân tích 4 forces cho cuộc chuyển đổi 2016 chứ không phải 2026 → thêm §2.6b. Nhóm tự phán đoán lại xem khung mới có thuyết phục hơn không hay chỉ dài hơn |
| 17 | **§2** | *AI cập nhật số liệu mới* | AI check & bổ sung | Bổ sung số Q2 FY2026 (doanh thu $370M +48%, >80% khách dùng credit hàng tuần) và diễn biến cổ phiếu −52% H1/2026 — những số công bố sau khi Hải Đăng đã viết xong |
| 18 | Mở đầu | Đính chính câu "vì sao chọn sản phẩm này" | AI phát hiện mâu thuẫn, **nhóm quyết định** | Câu "Figma không còn phổ biến" mâu thuẫn với chính §2 (82,3% thị phần, doanh thu +48%). Nhóm chọn **giữ luận điểm gốc nhưng sửa cho đúng**: cái giảm là niềm tin thị trường vốn, không phải mức độ sử dụng |
| 19 | **§3** | Dựng 3 dự đoán + chuỗi bằng chứng | AI làm khung, **cả nhóm phản biện và chốt** | Mỗi dự đoán bắt buộc kèm **điều kiện phản chứng**. Nhóm tự trả lời: nếu điều kiện phản chứng xảy ra thì luận điểm nào ở §1–§2 sai theo? |
| 20 | **§3** | Loại các hướng dự đoán không dùng | **Cả nhóm** | Loại các hướng không có bằng chứng công khai chống lưng (Figma bị thâu tóm, ra sản phẩm 3D) — chỉ là suy diễn hợp lý, không kiểm chứng được |
| 21 | **§3** | Phần "Ba dự đoán ăn khớp thế nào" + "Rủi ro chung" | AI làm, nhóm giữ lại | Nhóm giữ vì nó buộc 3 dự đoán nối về cùng một nghịch lý (doanh thu +48% nhưng cổ phiếu −52%), và vì phần "Rủi ro chung" thừa nhận giới hạn của chính bài phân tích |
| 22 | Trình bày | Format bảng, đánh số mục, gắn link | AI làm | Nhóm rà lại để bảng không vỡ và mọi link đều bấm được |

### 4.2 Ba lỗi nhóm tự mắc ở §1–§2 mà AI bắt được

Ghi lại trung thực vì đây là chỗ nhóm học được nhiều nhất — cả ba lỗi đều nằm trong phần **nhóm tự viết**, không phải phần AI viết:

1. **Số đúng nhưng mốc thời gian sai.** Hải Đăng lấy NDR 136% từ một bài tổng hợp và gán cho ngày 31/12/2025, trong khi đó là số của **Q2 FY2026** — lệch gần 8 tháng. Bài học: **con số đúng + mốc thời gian sai = số liệu sai.** Nhóm bổ sung quy tắc: mọi số phải kèm kỳ báo cáo cụ thể và truy về đúng bản gốc, không lấy qua bài tổng hợp trung gian.

2. **Bảng đối thủ đầy đủ nhưng trả lời sai câu hỏi.** §2.3 bản gốc liệt kê Sketch, Adobe XD, Penpot, InVision — có số, có nguồn, format chuẩn, nhưng **cả 4 đều đã chết hoặc đóng băng**. Nó trả lời "vì sao Figma thắng 2016–2024" trong khi đề bài hỏi về 2026. Nặng hơn: InVision đã **đóng cửa hoàn toàn từ 31/12/2024** mà vẫn được ghi là còn 7,6% thị phần. Bài học: **một bảng trông đúng format vẫn có thể lệch hoàn toàn câu hỏi** — phải luôn tự hỏi "cái này đang trả lời câu hỏi nào, và có phải câu hỏi của đề không?"

3. **Áp đúng khung nhưng sai thời điểm.** §2.6 dùng khung 4 forces chuẩn, nhưng đặt "Push" = lực đẩy khỏi Sketch/Adobe XD — tức đang phân tích cuộc chuyển đổi **2016**, không phải cuộc chuyển đổi 2026. Mà giải pháp hiện tại của user năm 2026 chính là Figma, nên "Push" phải là lực đẩy user **rời khỏi Figma**. Sai lệch này khiến phân tích switching cost trông vững hơn thực tế. Bài học: **khung phân tích chỉ đúng khi xác định đúng "giải pháp hiện tại" là gì tại thời điểm đang xét.**

### 4.3 Hai giới hạn của AI mà nhóm quan sát được

Để cân bằng, nhóm ghi lại cả chỗ AI **không** giúp được:

1. **AI không tự phát hiện mâu thuẫn giữa các phần cho tới khi được yêu cầu.** Câu mở đầu memo ("Figma không còn phổ biến") mâu thuẫn trực tiếp với §2 (82,3% thị phần, doanh thu +48%) nhưng tồn tại song song qua nhiều bản. AI chỉ chỉ ra khi nhóm yêu cầu **kiểm tra chéo cả bài**, không tự nêu khi được yêu cầu viết tiếp. Bài học: mặc định AI xử lý từng phần độc lập — muốn bắt mâu thuẫn phải yêu cầu rõ.

2. **AI không thể đảm bảo dự đoán §3 là đúng.** Nhóm có yêu cầu "làm sao cho mọi dự đoán đều đúng", và AI nói thẳng là không đảm bảo được với dự đoán tương lai. Thay vào đó nhóm chấp nhận cách làm chặt hơn: chỉ dự đoán phần **kéo dài quỹ đạo Figma đã công bố** (đã lên waitlist, đã beta, lãnh đạo đã phát biểu trên earnings call), và mỗi dự đoán bắt buộc kèm **điều kiện phản chứng**.

### 4.4 Nguyên tắc dùng AI nhóm rút ra sau bài này

| Nguyên tắc | Vì sao |
|---|---|
| **Tự làm nghiên cứu trước, AI kiểm chứng sau** | §1 và §2 nhóm tự viết trọn vẹn rồi mới đưa AI soát. Nhờ vậy nhóm hiểu nội dung đủ sâu để **phán xét được** những gì AI sửa — nếu để AI viết trước, nhóm sẽ không đủ nền để biết nó đúng hay sai |
| Dùng AI để **tìm nguồn**, không dùng AI để **làm nguồn** | Mọi số liệu đều truy được về hồ sơ SEC, thông cáo IR, earnings call, hoặc blog chính chủ Figma — không có số nào chỉ do AI "nhớ" |
| Ưu tiên **hồ sơ pháp lý** hơn bài blog | S-1 và báo cáo quý bị ràng buộc trách nhiệm pháp lý; blog thì không |
| Không lấy số qua **bài tổng hợp trung gian** | Lỗi NDR 136% xảy ra đúng vì lấy số qua bài tổng hợp thay vì bản gốc |
| Mọi dự đoán phải có **điều kiện phản chứng** | Dự đoán không thể sai được là dự đoán vô giá trị. Đây là rào chắn chống việc AI viết ra thứ nghe thuyết phục mà rỗng |
| Phải **chủ động yêu cầu AI kiểm tra chéo** toàn bài | Cả 3 lỗi ở 4.2 và mâu thuẫn ở câu mở đầu chỉ lộ ra khi nhóm yêu cầu soát lại, không lộ ra khi yêu cầu viết tiếp |
| Phán đoán cuối cùng thuộc về nhóm | AI đề xuất sửa gì thì nhóm vẫn phải tự quyết giữ hay bỏ — ví dụ nhóm chọn **giữ** luận điểm gốc ở câu mở đầu và chỉ sửa lại cho chính xác, thay vì bỏ theo gợi ý |
