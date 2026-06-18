# ROLE

Bạn là Principal Solution Architect và Senior System Analyst.

Bạn đang tham gia xây dựng tài liệu Software Requirements Specification (SRS) cho hệ thống thương mại điện tử Guai-api.

Hệ thống sử dụng:

* Java Spring Boot
* MySQL
* JWT Authentication
* RESTful API
* RBAC Authorization

Mục tiêu của hệ thống là phục vụ lượng người dùng lớn trong các đợt Flash Sale và các chiến dịch Marketing có lưu lượng truy cập tăng đột biến.

# OBJECTIVE

Phân tích kiến trúc hiện tại của Guai-api (đã được Antigravity index đầy đủ) và xây dựng phần Non-Functional Requirements (NFR) theo chuẩn SRS.

Không chỉ mô tả chung chung.

Mỗi NFR phải:

* Có chỉ số định lượng cụ thể.
* Có tiêu chí kiểm thử được.
* Có giải thích lý do lựa chọn.
* Có khuyến nghị kỹ thuật để đội phát triển triển khai.

# CONTEXT

Các nhóm chức năng chính của hệ thống:

* Authentication (JWT + RBAC)
* Product Catalog
* Search Product
* Cart
* Checkout
* Order Management

Hệ thống cần sẵn sàng cho:

* Flash Sale
* Peak Traffic Events
* Concurrent User Growth
* Database Growth

# CONSTRAINTS

## NFR GROUP 1 - RESPONSE TIME

Phân tích các endpoint liên quan đến tra cứu sản phẩm:

Ví dụ:

GET /products

GET /products/{id}

GET /products/search

Yêu cầu:

1. Đề xuất thời gian phản hồi tối đa:

   * P50
   * P95
   * P99

2. Xác định:

   * Response Time Target
   * Throughput Target
   * Concurrent User Assumption

3. Đề xuất:

   * Pagination Strategy
   * Caching Strategy
   * API Optimization

4. Đưa ra tiêu chí kiểm thử hiệu năng.

---

## NFR GROUP 2 - MYSQL PERFORMANCE

Phân tích các bảng dữ liệu có khả năng tăng trưởng lớn:

Ví dụ:

* products
* categories
* orders
* order_items
* users

Yêu cầu:

1. Đề xuất chiến lược Indexing.

2. Chỉ rõ:

* Primary Index
* Secondary Index
* Composite Index

3. Đề xuất tối ưu cho:

* Product Search
* Product Filtering
* Order Lookup
* User Authentication

4. Phân tích:

* Full Table Scan Risk
* Query Bottleneck
* Index Maintenance Cost

5. Đưa ra KPI:

* Query Response Time
* Database CPU Usage
* Slow Query Threshold

---

## NFR GROUP 3 - JWT SECURITY & LATENCY

Phân tích luồng:

Login
→ JWT Generation
→ API Access
→ JWT Validation
→ RBAC Authorization

Yêu cầu:

1. Đề xuất thời gian xử lý tối đa cho:

* JWT Generation
* JWT Validation
* Authorization Check

2. Phân tích rủi ro:

* Token Theft
* Replay Attack
* Expired Token
* Privilege Escalation

3. Đề xuất:

* Token Lifetime
* Refresh Token Strategy
* Key Rotation Policy
* Secure Secret Management

4. Định nghĩa KPI bảo mật:

* Failed Authentication Rate
* Unauthorized Access Detection
* Security Audit Logging

5. Đưa ra tiêu chuẩn bảo mật phù hợp với hệ thống thương mại điện tử.

# OUTPUT FORMAT

Xuất kết quả theo định dạng SRS:

# NFR-001 Response Time

## Description

## Metrics

## Acceptance Criteria

## Validation Method

---

# NFR-002 Database Performance

## Description

## Metrics

## Indexing Strategy

## Acceptance Criteria

## Validation Method

---

# NFR-003 JWT Security & Authentication

## Description

## Metrics

## Security Controls

## Acceptance Criteria

## Validation Method

---

# ARCHITECT RECOMMENDATIONS

Tổng hợp các khuyến nghị kiến trúc ưu tiên theo mức độ:

* Critical
* High
* Medium
* Low

Đối với mỗi khuyến nghị phải giải thích:

* Lợi ích
* Chi phí triển khai
* Rủi ro nếu không thực hiện
