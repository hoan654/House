# Phân tích yếu tố tác động đến giá nhà tại Mỹ và dự báo giá nhà

## 1. Mục tiêu dự án  
- Phân tích từng yếu tố và xác định những yếu tố ảnh hưởng mạnh đến giá bán nhà.
- Cung cấp insights về mối quan hệ giữa biến với giá trong quá trình EDA và Mô hình.
- Đưa ra các đề xuất, khuyến nghị cho người mua, người bán, nhà đầu tư.
- Xây dựng mô hình hồi quy tuyến tính đa biến, Xgboost,... để dự báo giá nhà  (R², RMSE).  


## 2. Nguồn dữ liệu sử dụng  
- Nguồn: Kaggle (House Sales in King County, USA)
- Link: https://www.kaggle.com/datasets/harlfoxem/housesalesprediction


## 3. Tổng quan dữ liệu  
- **Mô tả chung**: Dữ liệu giao dịch bán nhà tại King County (Washington State), bao gồm thông tin kỹ thuật và vị trí.  
- **Cấu trúc bảng**:  
  - `id`: mã giao dịch  
  - `date`: ngày bán  
  - `price`: giá bán (USD)  
  - `bedrooms`, `bathrooms`: số phòng ngủ, số phòng tắm  
  - `sqft_living`, `sqft_lot`: diện tích sử dụng trong nhà và diện tích đất (sqft)  
  - `floors`: số tầng  
  - `waterfront`: view mặt nước (0/1)  
  - `view`, `condition`, `grade`: đánh giá góc nhìn, tình trạng, chất lượng xây dựng  
  - `sqft_above`, `sqft_basement`: diện tích trên mặt đất và diện tích tầng hầm  
  - `yr_built`, `yr_renovated`: năm xây, năm cải tạo  
  - `lat`, `long`: toạ độ kinh độ và vĩ độ
  - `zipcode`: mã vùng
  - `sqft_living15`, `sqft_lot15`: diện tích trung bình của 15 ngôi nhà xung quanh

## 4. Công cụ và công nghệ áp dụng  
- **Ngôn ngữ**: Python  
- **Xử lý & phân tích**: `pandas`, `numpy`  
- **Trực quan hóa**: `matplotlib`, `seaborn`  
- **Mô hình hóa**: `statsmodels`, `scikit-learn`  
- **Môi trường**: `Google Colab/Jupyter Notebook`
- **Công cụ hỗ trợ**: `Excel`

## 5. Các insight chính  và giả thuyết được đưa ra
1. **Diện tích sử dụng** (`sqft_living`) và **grade** có tương quan mạnh nhất với giá bán.  
2. **Tỷ lệ diện tích/phòng ngủ cao** đem lại giá trị gia tăng vì không gian sống thoải mái hơn.
3. **Tăng điểm view và grade** kỳ vọng kéo giá bán tăng X% khi giữ nguyên các yếu tố khác.  
4. **Waterfront**: Nhà gần mặt nước luôn bán với giá cao hơn do đặc tính địa lý và nhu cầu thị trường.  
5. **Cải tạo** (yr_renovated) làm tăng giá bán so với nhà chưa cải tạo.  

## 6. Mô hình
- Xây dựng và so sánh các mô hình với nhau.
- Lựa chọn Mô hình Xgboost vì có R-squared và RMSE tối ưu nhất.

## 7. Kết luận tổng thể
- Diện tích sử dụng, vị trí địa lý và chất lượng căn nhà là những yếu tố ảnh hưởng lớn nhất đến giá nhà. Ngoài ra các biến này cũng có tương quan lớn với nhau, ví dụ diện tích, phòng ngủ, số lầu có mối quan hệ chặt chẽ - có thể làm tăng giảm giá phụ vào vào bố cục và thiết kế căn nhà. Người mua/bán, nhà đầu tư cần phân tích kỹ các yếu tố trong mối quan hệ tổng để đưa ra quyết định chính xác và tối ưu nhất.
  
## 8. Khuyến nghị dựa trên kết quả phân tích  
- **Nhà đầu tư**: Ưu tiên mua/sửa chữa tại khu vực waterfront và nâng cấp grade để tối đa hóa lợi nhuận.  
- **Người bán**: Đầu tư cải tạo, sơn sửa, nâng cấp grade và khai thác tính view để tăng curb appeal.  
- **Người mua**: Lưu ý cân bằng giữa số phòng ngủ và diện tích mỗi phòng, ưu tiên nhà có waterfront nếu ngân sách cho phép.
