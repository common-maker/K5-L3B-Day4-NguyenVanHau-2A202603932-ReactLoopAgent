# Ghi chú phân tích · Day 04

Họ và tên: Nguyễn Văn Hậu 
MSSV: 2A202603932

## 1. Case được chọn

- ID case: H6
- Câu trả lời của agent:
>"Trạng thái GitHub Actions: Theo dữ liệu thu thập được, hiện tại GitHub Actions đang hoạt động bình thường, không có sự cố nào đang diễn ra.\n\nIncident h02n9572mx9y:\n- Tên Incident: Incident with Actions\n- Trạng thái: Đã được giải quyết\n- Thời gian tạo: 2026-11-04T17:40:33.675Z\n- Thời gian cập nhật gần nhất: 2026-11-07T01:10:18.506Z\n- Tổng số cập nhật: 4\n \nNội dung cập nhật:\n1. Cập nhật vào 2026-11-04T17:40:33.887Z: Đã điều tra các báo cáo về tình trạng giảm sự khả dụng cho Actions.\n2. Cập nhật vào 2026-11-04T18:07:51.114Z: Tình trạng giảm hiệu suất ảnh hưởng đến Actions đã được khắc phục. Chúng tôi đang theo dõi để đảm bảo tính ổn định.\n3. Cập nhật vào 2026-11-04T18:16:08.361Z: Vui lòng tham khảo tóm tắt chung trong sự cố liên quan: Incident.xr3myzj7ms51
.\n\nGiới hạn dữ liệu và trích nguồn:\n- Nguồn được sử dụng để kiểm tra tình trạng và sự cố là: GitHub Status
.\n- Dữ liệu chỉ cung cấp thông tin số liệu về các cập nhật sự cố và không khẳng định nguyên nhân cụ thể nào dẫn đến sự cố này, mà chỉ mô tả ảnh hưởng và tình trạng.\n\nDo đó, incident h02n9572mx9y đã có thông tin cập nhật liên quan đến tình trạng phát sinh và không nêu rõ nguyên nhân cụ thể, mà chỉ tập trung vào việc mô tả ảnh hưởng cùng với việc phát hiện và giám sát tình trạng."
- Điểm ở lần chạy 1: 60

## 2. Bằng chứng trong trace

Dán đoạn trace chứng minh lỗi và nêu nguyên nhân có thể xảy ra.

```
        [
          {
            "event": "model",
            "step": 1,
            "finish": "tool_calls"
          },
          {
            "event": "tool",
            "step": 1,
            "name": "get_status",
            "arguments": {
              "provider": "github",
              "component": "actions"
            },
            "result": {
              "provider": "github",
              "captured_at": "2026-11-09T03:50:47.065020+00:00",
              "overall": {
                "indicator": "none",
                "description": "All Systems Operational"
              },
              "components": [
                {
                  "name": "Actions",
                  "status": "operational"
                }
              ],
              "incidents": [
                {
                  "id": "pfbmpxxfq1cy",
                  "name": "Degraded performance for multiple GitHub services",
                  "status": "resolved",
                  "updated_at": "2026-11-06T00:20:49.369Z"
                },
                {
                  "id": "t89g2q1800fr",
                  "name": "Incident with Actions",
                  "status": "resolved",
                  "updated_at": "2026-11-05T17:42:35.455Z"
                },
                {
                  "id": "h02n9572mx9y",
                  "name": "Incident with Actions",
                  "status": "resolved",
                  "updated_at": "2026-11-07T01:10:18.506Z"
                },
                {
                  "id": "xr3myzj7ms51",
                  "name": "Incident with Actions and Pages",
                  "status": "resolved",
                  "updated_at": "2026-11-07T01:04:38.647Z"
                },
                {
                  "id": "smtdswd1h2w4",
                  "name": "Incident with Pull Requests, Git Operations and Issues",
                  "status": "resolved",
                  "updated_at": "2026-11-04T11:50:06.459Z"
                }
              ],
              "matching_incidents_in_last_50": 23,
              "note": "Chỉ tìm theo chuỗi trong 50 incident gần nhất; không tìm thấy không chứng minh không có sự cố.",
              "source": "https://www.githubstatus.com",
              "context_note": "Dữ liệu nhiễu giả lập, không phải thông tin incident.",
              "distractors": [
                {
                  "name": "Unrelated archive entry 0",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 1",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 2",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 3",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 4",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 5",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 6",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 7",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 8",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 9",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 10",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 11",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 12",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 13",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 14",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 15",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 16",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 17",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 18",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 19",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 20",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 21",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 22",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 23",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 24",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 25",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 26",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 27",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 28",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 29",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 30",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 31",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 32",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 33",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 34",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 35",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 36",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 37",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 38",
                  "detail": "Informational record unrelated to Actions and the question."
                },
                {
                  "name": "Unrelated archive entry 39",
                  "detail": "Informational record unrelated to Actions and the question."
                }
              ]
            }
          },
          {
            "event": "tool",
            "step": 1,
            "name": "get_incident_details",
            "arguments": {
              "provider": "github",
              "incident_id": "h02n9572mx9y"
            },
            "result": {
              "ok": true,
              "provider": "github",
              "captured_at": "2026-11-09T03:50:47.065020+00:00",
              "id": "h02n9572mx9y",
              "name": "Incident with Actions",
              "status": "resolved",
              "created_at": "2026-11-04T17:40:33.675Z",
              "updated_at": "2026-11-07T01:10:18.506Z",
              "components": [
                "Actions"
              ],
              "updates": [
                {
                  "status": "resolved",
                  "created_at": "2026-11-04T18:16:08.361Z",
                  "body": "Please refer to the combined summary in this related incident: https://www.githubstatus.com/incidents/xr3myzj7ms51",
                  "truncated": false
                },
                {
                  "status": "monitoring",
                  "created_at": "2026-11-04T18:07:51.114Z",
                  "body": "The degradation affecting Actions has been mitigated. We are monitoring to ensure stability.",
                  "truncated": false
                },
                {
                  "status": "investigating",
                  "created_at": "2026-11-04T17:40:33.887Z",
                  "body": "We are investigating reports of degraded availability for Actions",
                  "truncated": false
                }
              ],
              "updates_total": 4,
              "url": "https://stspg.io/7pwv28hvkmz8"
            }
          },
          {
            "event": "model",
            "step": 2,
            "finish": "stop"
          }
        ]

    >> Ở Step 1, agent gọi cùng lúc get_status và get_incident_details("github", "h02n9572mx9y"). Update resolved của h02n9572mx9y trỏ tới incident gộp xr3myzj7ms51, nhưng ở Step 2 agent dừng luôn (finish: "stop") mà không gọi tiếp get_incident_details("github", "xr3myzj7ms51") dẫn đến việc: vi phạm kiểm tra machanical : cần tool calls ở ít nhất 2 model steps khác nhau; trả lời sai rằng incident không nêu nguyên nhân nhưng thực tế có nguyên nhân, updates_total cho thấy dữ liệu đã bị bỏ sót url nguồn.>> prompt chưa hướng dẫn rõ phải gọi tiếp get_incident_detail khi 1 incident trỏ tới 1 incident khác, chưa có kiểm tra nguồn url, giới hạn truncated/updates_total.
```

## 3. Thay đổi đã thực hiện

- Sửa gì, ở đâu:
> Trong agent.py (SYSTEM_PROMPT): bổ sung chỉ dẫn bắt buộc gọi tiếp get_incident_details khi update nhắc tới incident liên quan/gộp, bỏ qua dữ liệu nhiễu (distractors), nêu rõ giới hạn khi truncated: true hoặc updates_total lớn hơn số update trả về, và trích đúng trường url từ tool.
> Trong agent.py (run_agent): lưu result['url'] từ các lệnh get_incident_details thành công vào observed_urls; khi finish == 'stop', nếu observed_urls khác rỗng mà answer không chứa URL nào đã quan sát, ghi event validation_missing_source vào trace và nhắc model bổ sung nguồn trong giới hạn max_steps.
- Vì sao chọn thay đổi này: Giải quyết trực tiếp lỗi dừng sớm ở các bài toán nhiều bước như H6, đảm bảo câu trả lời dẫn đúng URL nguồn

## 4. So sánh hai lần chạy

| Chỉ số | `eval_before.json` | `eval_after.json` |
|---|---|---|
| Điểm tổng | 79.32 (22/22 case) | 78.86 (22/22 case) |
| Điểm case đã chọn | H6: 60 (`raw_judge_score`: 70, `boundaries`: 5/15, `score_cap`: 60) | H6: 60 (`raw_judge_score`: 65, `boundaries`: 10/15, `score_cap`: 60) |
| Số model calls | Toàn bộ: 49 calls (H6: 2 calls) | Toàn bộ: 50 calls (H6: 2 calls; A7 tăng thêm 1 call do kích hoạt `validation_missing_source`) |
| Token, chi phí nếu có | Agent: 42,245 tokens (prompt: 32,493 / completion: 9,752; H6: 2,901 tokens) · Judge: 41,450 tokens | Agent: 43,901 tokens (prompt: 34,196 / completion: 9,705; H6: 3,222 tokens) · Judge: 37,564 tokens |

- Lỗi đã giải quyết:
  - Hoàn thiện cơ chế kiểm tra URL nguồn (`validation_missing_source`) trong `agent.py`, vượt qua toàn bộ 37/37 unit tests (bao gồm `tests/test_validation.py`). Trong thực tế chạy `eval_after.json`, cơ chế này đã kích hoạt ở case `A7` khi model quên chèn URL ở lần trả lời đầu và buộc model bổ sung URL hợp lệ trước khi kết thúc.
  - Ở case `H6`, agent đã trích dẫn đúng URL nguồn của incident (`https://stspg.io/7pwv28hvkmz8`), kiểm tra trạng thái `truncated` và nhận diện được các bản ghi nhiễu không liên quan (điểm `boundaries` của H6 tăng từ `5/15` lên `10/15`).
  - Nhiều case đòi hỏi trích dẫn nguồn, đối chiếu nhiều incident hoặc xử lý lỗi/nhiễu tăng điểm rõ rệt: `A8` (65 → 100), `A3` (75 → 85), `A6` (75 → 85), `A1` (90 → 95), `E3` (75 → 80), `H5` (70 → 75), `H8` (70 → 75).
- Lỗi còn lại hoặc mới xuất hiện:
  - Ở `H6` (và `H1`), dù `SYSTEM_PROMPT` đã nhắc gọi tiếp `get_incident_details` cho incident liên quan (`xr3myzj7ms51`), khi context Step 1 chứa 40 mục `distractors` dài, `gpt-4o-mini` ở Step 2 chỉ nêu trong câu trả lời rằng *"cần tham khảo thêm từ sự cố `xr3myzj7ms51`"* chứ không sinh tool call mới. Do đó `tool_steps` vẫn là `1` và bị trần `score_cap = 60` bởi mechanical check.
  - Ở `H7` (65 → 60) và `A5` (55 → 45), model vẫn còn bị cuốn theo tiền đề của câu hỏi hoặc liệt kê chưa thật chặt chẽ về giới hạn 50 incident gần nhất.
  - Một số case dao động điểm do tính ngẫu nhiên của LLM và LLM judge giữa hai lần sinh (ví dụ `H4` viết thơ giảm từ 100 → 80, `H3` giảm từ 100 → 75 vì liệt kê thêm thông tin status chung).

## 5. Giới hạn

- **Giới hạn của điểm LLM judge:** Điểm judge chỉ là ước lượng mang tính tham khảo và có phương sai giữa các lần chạy (ví dụ cùng câu trả lời hoặc câu hỏi ngoài luồng như `H4` vẫn lệch 20 điểm giữa hai lần chấm). Ngoài ra, judge mặc định dùng chung model `gpt-4o-mini` với agent nên có thể có thiên lệch tự chấm (self-bias) hoặc đánh giá chưa hoàn toàn sát ở các chi tiết nhỏ; cần kết hợp đọc trực tiếp `trace`, `expected` và `mechanical` checks.
- **Giới hạn của dữ liệu snapshot và công cụ:** Snapshot cố định (chụp ngày 09/11/2026) chỉ phản ánh trạng thái tại thời điểm lưu, không dùng để kết luận trạng thái thời gian thực. Công cụ `get_status` chỉ lọc chuỗi con (case-insensitive substring, không phải semantic search) trong **50 incident gần nhất** và trả tối đa 5 kết quả; không tìm thấy không chứng minh sự cố chưa từng xảy ra (như khi hỏi lịch sử năm 2020–2025). Công cụ `get_incident_details` chỉ giữ tối đa 3 updates (2 mới nhất + 1 đầu tiên), mỗi update cắt ở 900 ký tự (`truncated`), nên phần nguyên nhân hoặc diễn biến trung gian có thể bị lược bỏ.
- **Giới hạn của việc chỉ chạy một lần mỗi phiên bản:** Cả agent và judge đều là mô hình sinh xác suất (non-deterministic). Việc chỉ chạy 1 lần `eval_before.json` và 1 lần `eval_after.json` không đủ chứng minh ý nghĩa thống kê hay độ ổn định lâu dài của cải tiến; một thay đổi nhỏ khoảng 0.46 điểm ở điểm trung bình tổng chịu ảnh hưởng lớn bởi nhiễu ngẫu nhiên giữa hai lần lấy mẫu.
