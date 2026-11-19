# Yêu cầu đầu ra
## Promt:
```markdown
# CONTEXT
Bạn là chuyên gia phân tích dữ liệu giáo dục. Giảng viên môn lập trình có kết quả kiểm tra của 5 sinh viên trong 3 tuần (thang điểm 10) và nhận thấy điểm của một số sinh viên đang giảm dần. Giảng viên cần phân tích dữ liệu để đưa ra biện pháp hỗ trợ học tập.

| Sinh viên | Tuần 1 | Tuần 2 | Tuần 3 |
|---|---|---|---|
| An | 8 | 7 | 5 |
| Bình | 7 | 6 | 4 |
| Chi | 9 | 8 | 8 |
| Dũng | 6 | 5 | 3 |
| Hà | 8 | 8 | 7 |

# REQUEST
1/ Tính mức tăng, giảm điểm của từng sinh viên.
2/ Xác định sinh viên có dấu hiệu sa sút.
3/ So sánh kết quả học tập giữa các sinh viên.
4/ Nêu những vấn đề giảng viên cần xác minh thêm.
5/ Đề xuất giải pháp cải thiện kết quả học tập.

# EXPLANATION
1/ Chỉ dùng dữ liệu trong bảng trên.
2/ Không suy đoán nguyên nhân khiến điểm giảm.
3/ Mọi nhận định phải kèm số liệu chứng minh.
4/ Định nghĩa "sa sút": điểm giảm liên tiếp qua cả 3 tuần (T2 < T1 và T3 < T2). Không thêm tiêu chí hoặc ngưỡng khác.
5/ Khi thực hiện các bước tính toán hãy trình bày một cách cụ thể các phép tính ra.

# ACTION
Phân tích lần lượt theo 4 bước và trình bày rõ từng bước:
**Bước 1/ Tính toán:** Với mỗi sinh viên, tính Δ T1→T2, Δ T2→T3, tổng Δ T1→T3 và điểm trung bình.
**Bước 2/ So sánh:** Xếp hạng theo điểm trung bình và theo tổng Δ. Chỉ ra sinh viên giảm nhiều nhất, giảm ít nhất và nhóm có mức giảm giống nhau.
**Bước 3/ Nhận định:** Đối chiếu từng sinh viên với định nghĩa sa sút, nêu số liệu làm căn cứ.
**Bước 4/ Đề xuất:** Chỉ đề xuất giải pháp dựa trực tiếp trên nhận định ở Bước 3.

# TONE
Khách quan, ngắn gọn, chuyên nghiệp. Mỗi ý một câu, không lặp ý, không khen chê, không dùng ngôn ngữ cảm xúc.

# EXTRAS
1/ Bảng phân tích: Sinh viên | Δ T1→T2 | Δ T2→T3 | Tổng Δ | TB | Sa sút (Có/Không)
2/ Nhóm sinh viên có dấu hiệu sa sút: tên và căn cứ số liệu.
3/ Ba nhận định quan trọng: mỗi nhận định 1 câu, kèm số liệu.
4/ Ba giải pháp hỗ trợ học tập cụ thể: mỗi giải pháp gồm đối tượng, hành động và căn cứ dữ liệu.
5/ Toàn bộ bộ kết quả đầu ra này hãy trả về file .md.
```
## Kết quả
```markdown
# Phân tích kết quả kiểm tra môn lập trình (3 tuần, 5 sinh viên)
 
**Dữ liệu đầu vào (thang điểm 10):**
 
| Sinh viên | Tuần 1 | Tuần 2 | Tuần 3 |
|---|---|---|---|
| An | 8 | 7 | 5 |
| Bình | 7 | 6 | 4 |
| Chi | 9 | 8 | 8 |
| Dũng | 6 | 5 | 3 |
| Hà | 8 | 8 | 7 |
 
**Định nghĩa sa sút:** T2 < T1 và T3 < T2 (điểm giảm liên tiếp qua cả 3 tuần).
 
---
 
## Bước 1: Tính toán
 
Công thức: Δ T1→T2 = T2 − T1; Δ T2→T3 = T3 − T2; Tổng Δ = T3 − T1; TB = (T1 + T2 + T3) / 3.
 
| Sinh viên | Δ T1→T2 | Δ T2→T3 | Tổng Δ | Điểm TB |
|---|---|---|---|---|
| An | 7 − 8 = **−1** | 5 − 7 = **−2** | 5 − 8 = **−3** | (8 + 7 + 5) / 3 = 20 / 3 = **6,67** |
| Bình | 6 − 7 = **−1** | 4 − 6 = **−2** | 4 − 7 = **−3** | (7 + 6 + 4) / 3 = 17 / 3 = **5,67** |
| Chi | 8 − 9 = **−1** | 8 − 8 = **0** | 8 − 9 = **−1** | (9 + 8 + 8) / 3 = 25 / 3 = **8,33** |
| Dũng | 5 − 6 = **−1** | 3 − 5 = **−2** | 3 − 6 = **−3** | (6 + 5 + 3) / 3 = 14 / 3 = **4,67** |
| Hà | 8 − 8 = **0** | 7 − 8 = **−1** | 7 − 8 = **−1** | (8 + 8 + 7) / 3 = 23 / 3 = **7,67** |
 
---
 
## Bước 2: So sánh
 
**Xếp hạng theo điểm trung bình (cao → thấp):**
 
| Hạng | Sinh viên | TB |
|---|---|---|
| 1 | Chi | 8,33 |
| 2 | Hà | 7,67 |
| 3 | An | 6,67 |
| 4 | Bình | 5,67 |
| 5 | Dũng | 4,67 |
 
**Xếp hạng theo tổng Δ (giảm ít → giảm nhiều):**
 
| Hạng | Sinh viên | Tổng Δ |
|---|---|---|
| 1 (đồng hạng) | Chi | −1 |
| 1 (đồng hạng) | Hà | −1 |
| 3 (đồng hạng) | An | −3 |
| 3 (đồng hạng) | Bình | −3 |
| 3 (đồng hạng) | Dũng | −3 |
 
- Giảm nhiều nhất: An, Bình, Dũng (cùng −3 điểm).
- Giảm ít nhất: Chi, Hà (cùng −1 điểm).
- Nhóm có mức giảm giống nhau thứ nhất: An, Bình, Dũng (Δ T1→T2 = −1, Δ T2→T3 = −2, tổng Δ = −3).
- Nhóm có mức giảm giống nhau thứ hai: Chi, Hà (tổng Δ = −1).
- Điểm TB thấp nhất là Dũng (4,67); cao nhất là Chi (8,33); chênh lệch 8,33 − 4,67 = 3,66 điểm.
---
 
## Bước 3: Nhận định (đối chiếu định nghĩa sa sút)
 
| Sinh viên | T2 < T1? | T3 < T2? | Kết luận |
|---|---|---|---|
| An | 7 < 8: Có | 5 < 7: Có | **Sa sút** |
| Bình | 6 < 7: Có | 4 < 6: Có | **Sa sút** |
| Chi | 8 < 9: Có | 8 < 8: Không | Không sa sút |
| Dũng | 5 < 6: Có | 3 < 5: Có | **Sa sút** |
| Hà | 8 < 8: Không | 7 < 8: Có | Không sa sút |
 
---
 
## Bảng phân tích tổng hợp
 
| Sinh viên | Δ T1→T2 | Δ T2→T3 | Tổng Δ | TB | Sa sút (Có/Không) |
|---|---|---|---|---|---|
| An | −1 | −2 | −3 | 6,67 | Có |
| Bình | −1 | −2 | −3 | 5,67 | Có |
| Chi | −1 | 0 | −1 | 8,33 | Không |
| Dũng | −1 | −2 | −3 | 4,67 | Có |
| Hà | 0 | −1 | −1 | 7,67 | Không |
 
## Nhóm sinh viên có dấu hiệu sa sút
 
- **An:** 8 → 7 → 5, giảm liên tiếp (−1, −2), tổng −3.
- **Bình:** 7 → 6 → 4, giảm liên tiếp (−1, −2), tổng −3.
- **Dũng:** 6 → 5 → 3, giảm liên tiếp (−1, −2), tổng −3.
## Ba nhận định quan trọng
 
1. 3/5 sinh viên (An, Bình, Dũng) thuộc nhóm sa sút, chiếm 60% lớp khảo sát.
2. Cả 3 sinh viên sa sút giảm 2 điểm ở T2→T3, gấp đôi mức giảm 1 điểm ở T1→T2.
3. Dũng có TB thấp nhất (4,67) và điểm T3 thấp nhất (3), trong khi Chi (TB 8,33) và Hà (TB 7,67) giảm tổng cộng 1 điểm và không sa sút.
---
 
## Những vấn đề giảng viên cần xác minh thêm
 
1. Ba bài kiểm tra có cùng thang điểm, cùng mức độ khó và cùng dạng đề hay không.
2. Nội dung kiểm tra mỗi tuần là kiến thức mới hay tích lũy, và có trùng với phần An, Bình, Dũng mất điểm hay không.
3. Điểm T3 của An, Bình, Dũng mất ở những câu hoặc phần kiến thức cụ thể nào (so với T2).
4. Dữ liệu 3 mốc có đủ để kết luận xu hướng hay cần thêm kết quả tuần 4 trở đi.
5. Có thiếu dữ liệu nào ngoài bảng điểm (số lần nộp bài, số buổi tham dự) để đối chiếu hay không.
---
 
## Bước 4: Đề xuất giải pháp hỗ trợ học tập
 
| # | Đối tượng | Hành động | Căn cứ dữ liệu |
|---|---|---|---|
| 1 | An, Bình, Dũng | Chữa chi tiết bài kiểm tra tuần 3 và ôn lại các phần kiến thức bị mất điểm. | Cả 3 giảm 2 điểm ở T2→T3 (An 7→5, Bình 6→4, Dũng 5→3). |
| 2 | Dũng | Ưu tiên phụ đạo cá nhân, hẹn gặp trao đổi trực tiếp trong tuần tới. | TB thấp nhất lớp (4,67) và T3 = 3, thấp nhất lớp. |
| 3 | An, Bình, Dũng | Cho bài kiểm tra ngắn ở tuần 4 để xác nhận xu hướng, tiếp tục theo dõi hằng tuần. | Cả 3 giảm liên tiếp qua 3 tuần; chưa có dữ liệu tuần 4 để xác nhận xu hướng. |
 ```