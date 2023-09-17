[data.csv](https://github.com/thangdtph27626/pandas/files/12642835/data.csv)# Sử dụng pandas vẽ biểu đồ

## Khái niệm

Pandas là một thư viện Python cung cấp các cấu trúc dữ liệu nhanh, mạnh mẽ, linh hoạt và mang hàm ý. Tên thư viện được bắt nguồn từ panel data (bảng dữ liệu). Pandas được thiết kế để làm việc dễ dàng và trực quan với dữ liệu có cấu trúc (dạng bảng, đa chiều, có tiềm năng không đồng nhất) và dữ liệu chuỗi thời gian.

## Vì sao bạn nên chọn pandas?

Pandas rất phù hợp với nhiều loại dữ liệu khác nhau:

- Dữ liệu dạng bảng với các cột được nhập không đồng nhất, như trong bảng SQL hoặc bảng tính Excel.
- Dữ liệu chuỗi thời gian theo thứ tự và không có thứ tự (không nhất thiết phải có tần số cố định).
- Dữ liệu ma trận tùy ý (được nhập đồng nhất hoặc không đồng nhất) với nhãn hàng và cột.
- Bất kỳ hình thức khác của các bộ dữ liệu quan sát / thống kê. Dữ liệu thực sự không cần phải được dán nhãn vào cấu trúc dữ liệu pandas.
- Pandas được xây dựng dựa trên NumPy. Hai cấu trúc dữ liệu chính của pandas là Series (1 chiều) và DataFrame (2 chiều) xử lý được phần lớn các trường hợp điển hình trong tài chính, thống kê, - -- khoa học xã hội và nhiều lĩnh vực kỹ thuật.

Ưu điểm của pandas:

- Dễ dàng xử lý dữ liệu mất mát, được biểu thị dưới dạng NaN, trong dữ liệu dấu phẩy động cũng như dấu phẩy tĩnh theo ý người dùng mong muốn: bỏ qua hoặc chuyển sang 0
- Khả năng thay đổi kích thước: các cột có thể được chèn và xóa khỏi DataFrame và các đối tượng chiều cao hơn
- Căn chỉnh dữ liệu tự động và rõ ràng: các đối tượng có thể được căn chỉnh rõ ràng với một bộ nhãn hoặc người dùng chỉ cần bỏ qua các nhãn và để Series, DataFrame, v.v. tự động căn chỉnh dữ - liệu cho bạn trong các tính toán
- Chức năng group by mạnh mẽ, linh hoạt để thực hiện các hoạt động kết hợp phân tách áp dụng trên các tập dữ liệu, cho cả dữ liệu tổng hợp và chuyển đổi
- Dễ dàng chuyển đổi dữ liệu rời rạc (ragged), chỉ mục khác nhau (differently-indexed) trong các cấu trúc dữ liệu khác của Python và NumPy thành các đối tượng DataFrame
- Cắt lát (slicing) thông minh dựa trên nhãn, lập chỉ mục ưa thích (fancy indexing) và tập hợp lại (subsetting) các tập dữ liệu lớn 
- Gộp (merging) và nối (joining) các tập dữ liệu trực quan
- Linh hoạt trong định hình lại (reshaping) và xoay (pivoting) các tập dữ liệu
- Dán nhãn phân cấp (hierarchical) của các trục (có thể có nhiều nhãn trên mỗi đánh dấu)
- Các công cụ IO mạnh mẽ để tải dữ liệu từ các tệp phẳng (flat file) như CSV và delimited, tệp Excel, cơ sở dữ liệu và lưu / tải dữ liệu từ định dạng HDF5 cực nhanh
- Chức năng theo chuỗi thời gian (time series) cụ thể: tạo phạm vi ngày và chuyển đổi tần số, thống kê cửa sổ di chuyển, dịch chuyển ngày và độ trễ.
- Tích hợp tốt với các thư viện khác của python như SciPy, Matplotlib, Plotly, v.v.
- Hiệu suất tốt

 ## Cài đặt thư viện Pandas

- Sử dụng pip và gõ lệnh: pip install pandas
-  Hoặc bằng Anaconda, dùng lệnh: conda install pandas

## Vẽ biểu đồ

Pandas sử dụng plot()phương pháp này để tạo sơ đồ.

Chúng ta có thể sử dụng Pyplot, một mô-đun con của thư viện Matplotlib để hiển thị sơ đồ trên màn hình.

```
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('data.csv')

df.plot()

plt.show()
```

[Tải file data.csv ](https://www.w3schools.com/python/pandas/data.csv)

![image](https://github.com/thangdtph27626/pandas/assets/109157942/6fc4647b-963c-42f3-8931-d7ec2c072a17)

## Vẽ biểu đồ phân tán

Bạn có thể vẽ biểu đồ phân tán với kind đối số:

> kind = 'scatter'

Biểu đồ phân tán cần có trục x và trục y.

Trong ví dụ bên dưới, chúng tôi sẽ sử dụng "Thời lượng" cho trục x và "Calo" cho trục y.

Bao gồm các đối số x và y như thế này:

```
x = 'Duration', y = 'Calories'

import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv('data.csv')

df.plot(kind = 'scatter', x = 'Duration', y = 'Calories')

plt.show()

```

![image](https://github.com/thangdtph27626/pandas/assets/109157942/a1909dff-6ce7-4623-9489-812ff787eb07)

- vẽ biểu đồ cột

Sử dụng kindđối số để xác định rằng bạn muốn có biểu đồ:

> kind = 'hist'

Một biểu đồ chỉ cần một cột.

Biểu đồ cho chúng ta thấy tần suất của từng khoảng thời gian, ví dụ: có bao nhiêu bài tập kéo dài từ 50 đến 60 phút?

Trong ví dụ bên dưới, chúng tôi sẽ sử dụng cột "Thời lượng" để tạo biểu đồ:

```
df["Duration"].plot(kind = 'hist')
```

![image](https://github.com/thangdtph27626/pandas/assets/109157942/5c651002-6168-4fb2-adc3-242e95c8e24e)

Bạn có thể tìm hiểu những cách vẽ biểu đồ khác tại đây [https://pandas.pydata.org/docs/user_guide/visualization.html](https://pandas.pydata.org/docs/user_guide/visualization.html)
