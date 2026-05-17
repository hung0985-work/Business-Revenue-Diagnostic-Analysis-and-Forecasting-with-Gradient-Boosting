# Business Revenue Diagnostic Analysis and Forecasting with Gradient Boosting

## 1. Tổng quan dự án

Dự án này phân tích tình hình kinh doanh của một doanh nghiệp thương mại điện tử thời trang theo mô hình Direct-to-Customer. Mục tiêu chính là chẩn đoán nguyên nhân khiến doanh thu sụt giảm sau giai đoạn tăng trưởng, đồng thời xây dựng mô hình dự báo doanh thu để hỗ trợ doanh nghiệp ra quyết định về sản phẩm, tồn kho, khuyến mãi và phân bổ nguồn lực.

Dự án kết hợp giữa phân tích dữ liệu kinh doanh, phân tích khách hàng, phân tích danh mục sản phẩm, phân tích tồn kho và mô hình dự báo chuỗi thời gian bằng các thuật toán Gradient Boosting.

## 2. Bối cảnh kinh doanh

Trong giai đoạn 2012–2022, doanh nghiệp từng đạt quy mô tăng trưởng tốt với hơn 646.000 đơn hàng và hơn 3,2 triệu sản phẩm bán ra. Tuy nhiên, sau năm 2016, doanh thu, số lượng đơn hàng và số sản phẩm bán ra bắt đầu suy giảm mạnh.

Trong khi thị trường thương mại điện tử Việt Nam vẫn tiếp tục tăng trưởng, doanh nghiệp lại đi ngược xu hướng khi mất dần khách hàng mới, suy giảm tỷ lệ chuyển đổi và đối mặt với vấn đề giữ chân khách hàng. Vì vậy, dự án tập trung làm rõ nguyên nhân cốt lõi của sự suy giảm này và đề xuất hướng phục hồi tăng trưởng.

## 3. Mục tiêu phân tích

Dự án tập trung trả lời các câu hỏi chính:

- Doanh nghiệp đang gặp vấn đề ở chi phí, trải nghiệm khách hàng hay nhu cầu thị trường?
- Nguyên nhân nào dẫn đến sự sụt giảm đơn hàng và doanh thu?
- Nhóm khách hàng nào đang có nguy cơ rời bỏ cao?
- Danh mục sản phẩm hiện tại có còn phù hợp với nhu cầu thị trường không?
- Tồn kho đang phản ánh vấn đề vận hành hay vấn đề product-market fit?
- Có thể dự báo Revenue và COGS bằng mô hình Gradient Boosting không?
- Doanh nghiệp nên ưu tiên cải thiện sản phẩm, khách hàng hay khuyến mãi?

## 4. Phương pháp thực hiện

Dự án sử dụng các nhóm phương pháp chính sau:

### 4.1. Business Diagnostic Analysis

Phân tích hiệu quả kinh doanh tổng thể thông qua doanh thu, số lượng đơn hàng, số lượng khách hàng, sản lượng bán ra, AOV, Gross Profit Margin và xu hướng tăng trưởng qua từng năm.

### 4.2. Customer Analysis

Sử dụng phân tích RFM để phân nhóm khách hàng thành các nhóm như Champions, Loyal, New/Recent, At Risk và Lost. Phần này giúp đánh giá chất lượng tệp khách hàng, mức độ trung thành và rủi ro mất khách hàng.

### 4.3. Product Portfolio Analysis

Phân tích danh mục sản phẩm nhằm xác định Hero Product, Zombie Product, nhóm sản phẩm tăng trưởng yếu, nhóm sản phẩm tồn kho cao và mức độ phụ thuộc doanh thu vào một số dòng sản phẩm chính.

### 4.4. Inventory and Demand Analysis

Phân tích stockout, overstock, sell-through rate, days of supply và reorder flag để đánh giá mức độ lệch pha giữa hàng nhập và nhu cầu thị trường.

### 4.5. Revenue Forecasting

Xây dựng mô hình dự báo Revenue và COGS bằng các thuật toán Gradient Boosting, bao gồm:

- XGBoost
- LightGBM
- CatBoost

Dữ liệu chuỗi thời gian được chuyển thành dạng bảng thông qua các biến calendar, lag, rolling, momentum và Fourier để mô hình học được xu hướng, mùa vụ và quán tính của doanh thu.

### 4.6. Model Evaluation and Interpretation

Mô hình được đánh giá bằng RMSE và MAE. Ngoài ra, SHAP được sử dụng để giải thích các yếu tố ảnh hưởng đến dự báo Revenue và COGS.

## 5. Cấu trúc file dự án

```text
Business-Revenue-Forecasting/
│
├── Model_Result.csv
│   └── File lưu kết quả mô hình dự báo, bao gồm các chỉ số đánh giá và/hoặc kết quả dự báo Revenue, COGS.
│
├── Notebook_Code.ipynb
│   └── Notebook chính để xử lý dữ liệu, tạo biến dự báo, huấn luyện mô hình Gradient Boosting, đánh giá mô hình và xuất kết quả.
│
├── Notebook_EDA.ipynb
│   └── Notebook phân tích khám phá dữ liệu, bao gồm phân tích doanh thu, khách hàng, sản phẩm, tồn kho, retention, RFM và các vấn đề kinh doanh cốt lõi.
│
└── Report.pdf
    └── Báo cáo tổng hợp toàn bộ kết quả phân tích, chẩn đoán nguyên nhân sụt giảm doanh thu, mô hình dự báo và khuyến nghị kinh doanh.
```

## 6. Hướng dẫn đọc dự án

Dự án gồm các file chính sau:

- `Report.pdf`: Dùng để đọc nhanh toàn bộ logic phân tích, từ bối cảnh kinh doanh, vấn đề doanh thu, nguyên nhân gốc rễ đến khuyến nghị và kết quả mô hình dự báo.
- `Notebook_EDA.ipynb`: Dùng để xem quá trình phân tích khám phá dữ liệu, bao gồm phân tích đơn hàng, khách hàng, danh mục sản phẩm, tồn kho và các dấu hiệu demand collapse.
- `Notebook_Code.ipynb`: Dùng để xem phần xử lý dữ liệu cho mô hình, feature engineering, huấn luyện XGBoost, LightGBM, CatBoost và đánh giá kết quả dự báo.
- `Model_Result.csv`: Dùng để kiểm tra kết quả đầu ra của mô hình, bao gồm kết quả dự báo hoặc bảng so sánh hiệu suất mô hình.

## 7. Kết quả chính

Một số kết quả nổi bật của dự án:

- Doanh nghiệp tăng trưởng tốt trong giai đoạn đầu nhưng bắt đầu suy giảm mạnh sau năm 2016.
- Vấn đề chính không đến từ chi phí xấu đi, vì Gross Profit Margin duy trì ở mức thấp nhưng tương đối ổn định trong nhiều năm.
- Trải nghiệm khách hàng có vấn đề nhất định, thể hiện qua điểm đánh giá trung bình chưa cao, nhưng không đủ để giải thích toàn bộ sự sụt giảm doanh thu.
- Nguyên nhân chính là demand collapse, thể hiện qua sự sụt giảm nghiêm trọng của khách hàng mới, số lượng đơn hàng và sản lượng bán ra.
- Doanh nghiệp có dấu hiệu PMF erosion khi khách hàng không còn tìm thấy sản phẩm đủ hấp dẫn để mua dù mức discount tăng.
- Danh mục sản phẩm có nhiều zombie product, trong khi các Hero Product cũ suy yếu và không có sản phẩm mới đủ mạnh để thay thế.
- Tồn kho phản ánh sự lệch pha nghiêm trọng giữa hàng nhập và nhu cầu thị trường, với tình trạng vừa stockout ở sản phẩm bán tốt vừa overstock ở sản phẩm bán chậm.
- Mô hình Gradient Boosting được xây dựng để dự báo Revenue và COGS, trong đó XGBoost được lựa chọn cho bài toán dự báo Revenue và CatBoost được lựa chọn cho bài toán dự báo COGS.
- Khi kiểm thử trên tập test thực tế, mô hình đạt **MSE khoảng 740K**, cho thấy mô hình có khả năng dự báo tương đối ổn định và có thể được sử dụng như một công cụ hỗ trợ lập kế hoạch doanh thu.

## 8. Công cụ sử dụng

Dự án sử dụng các công cụ và thư viện chính sau:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- LightGBM
- CatBoost
- SHAP
- Time-series feature engineering
- Jupyter Notebook

## 9. Hạn chế của dự án

Dự án vẫn có một số hạn chế:

- Dữ liệu có thể tồn tại khác biệt giữa doanh thu gross và doanh thu net do cách ghi nhận discount và trạng thái đơn hàng.
- Một số chỉ tiêu kinh doanh cần được diễn giải dựa trên giả định về mô hình D2C và bối cảnh TMĐT thời trang.
- Mô hình dự báo sử dụng dữ liệu lịch sử nên có thể chưa phản ánh đầy đủ các thay đổi bất thường trong tương lai.
- Kết quả dự báo hỗ trợ ra quyết định nhưng không thay thế hoàn toàn đánh giá chiến lược từ phía doanh nghiệp.
- Một số nguyên nhân như xu hướng thị trường, đối thủ cạnh tranh, chất lượng thiết kế sản phẩm và chiến lược thương hiệu chưa được lượng hóa đầy đủ trong dữ liệu.

## 10. Định hướng phát triển tiếp theo

Trong các phiên bản tiếp theo, dự án có thể được mở rộng theo các hướng:

- Xây dựng dashboard theo dõi Revenue, COGS, GPM, tồn kho và sell-through rate theo thời gian thực.
- Tạo hệ thống cảnh báo sớm cho zombie product, overstock và sản phẩm có nguy cơ suy giảm.
- Phát triển mô hình dự báo nhu cầu theo từng category hoặc từng SKU.
- Kết hợp dữ liệu marketing, traffic, conversion rate và campaign để dự báo doanh thu chính xác hơn.
- Xây dựng mô hình gợi ý nhập hàng dựa trên stockout, sell-through rate và biên lợi nhuận.
- Tích hợp mô hình dự báo vào quy trình ra quyết định về sản phẩm, khuyến mãi và quản trị tồn kho.
