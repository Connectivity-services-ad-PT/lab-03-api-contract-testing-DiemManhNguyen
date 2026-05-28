# Consumer–Provider Handshake

## Thông tin chung

- Lab: FIT4110 Lab 03
- Ngày: 2026-05-28
- Provider team: team-vision
- Consumer team: team-iot
- Provider service: AI Vision
- Consumer service: IoT Ingestion

## Contract

- Contract file: contracts/ai-vision.openapi.yaml
- Mock base URL: http://localhost:4011
- Auth method: Bearer Token
- Endpoint được test: POST /detect

## Smoke test

### Request

```http
POST /detect
Authorization: Bearer mock-token
Content-Type: application/json
```

```json
{
  "camera_id": "CAM01",
  "image_url": "https://example.com/frame.jpg"
}
```

### Expected response

```json
{
  "detection_id": "DET-12345",
  "label": "person",
  "confidence": 0.98
}
```

## Kết quả

- [x] Consumer gọi mock thành công.
- [x] Consumer parse được field cần dùng.
- [x] Consumer hiểu lỗi 4xx/5xx provider trả về.
- [x] Có Newman report hoặc screenshot.

## Ghi chú thay đổi hợp đồng

| Nội dung | Trước | Sau | Người đồng ý |
|---|---|---|---|
| Không có thay đổi | | | |

## Xác nhận

- Provider representative: Nguyen Van A (team-vision)
- Consumer representative: Diem Manh Nguyen (team-iot)
