3. <a name="_toc231591534"></a><a name="_toc231766133"></a>**Kết quả đạt được**
   1. <a name="_toc231591535"></a><a name="_toc231766134"></a>**Kết quả phân cụm**

Sau khi thực hiện chạy thuật toán K-Means tự mã hóa với số cụm lựa chọn là K =12 trên tập dữ liệu gồm 1.373 Website, các Website đã được phân tách thành các nhóm nội dung riêng biệt. Các từ khóa có trọng số TF-IDF cao nhất tại tâm cụm đã phản ánh rõ nét chủ đề của từng cụm. 

|**Mã cụm**|**Số lượng Website**|**Các từ khóa có trọng số TF-IDF cao nhất**|
| :-: | :-: | :-: |
|**Cụm 1**|613|home, sex, video, service, time, phone, online, contact, information, live|
|**Cụm 2**|85|hotel, travel, flight, tour, view, book, resort, room, day, hotels|
|**Cụm 3**|84|december, league, cricket, football, news, team, match, sports, win, world|
|**Cụm 4**|50|recipe, recipes, easy, chicken, food, indian, cake, pot, soup, chocolate|
|**Cụm 5**|71|game, card, play, player, chess, board, games, hand, pinball, point|
|**Cụm 6**|50|photography, camera, photo, photographer, image, dec, light, lens, focus, review|
|**Cụm 7**|41|movie, watch, series, drama, comedy, season, show, rate, tvma, action|
|**Cụm 8**|40|add, cart, gift, shop, baby, gifts, view, online, love, quality|
|**Cụm 9**|43|chat, room, online, people, friend, gay, join, video, meet, teen|
|**Cụm 10**|43|shop, online, view, fashion, shoes, product, men, accessories, home, shopping|
|**Cụm 11**|66|health, yoga, care, hospital, surgery, medicine, cancer, medical, patient, news|
|**Cụm 12**|187|news, world, late, december, india, ago, coronavirus, business, year, home|

<a name="_toc231764715"></a>*Bảng 3. *3* . Kết quả phân cụm – 12 cụm website và đặc trưng chủ đề.*

Từ kết quả thu được cho thấy, xét về độ chính xác ngữ nghĩa, thuật toán đã chứng minh khả năng phân tách dữ liệu ở mức độ chi tiết và sắc bén. Cụ thể, không chỉ nhận diện được các nhóm chủ đề lớn mà thuật toán còn bóc tách thành công các phân khúc chuyên sâu. Trong lĩnh vực thương mại điện tử, thuật toán đã phân lập rõ ràng nhóm Website về sản phẩm mẹ và bé (cụm 8:  shop, baby, gifts,... ) với nhóm Website thời trang (cụm 10: fashion, shoes, product, men,...). Tương tự, mảng giải trí trực tuyến cũng được phân rã thành các cụm đặc thù bao gồm: trò chơi điện tử (Cụm 5: game, card, play,...), phim ảnh (Cụm 7:movie, watch, series,...) và mạng xã hội (Cụm 9: chat, room, online,...).

Về phân phối dữ liệu, kết quả phân cụm cho thấy sự phân hóa mạnh mẽ về quy mô giữa các nhóm. Cụm 1 và cụm 12 chiếm tỷ trọng áp đảo với số lượng tương ứng là 613 và 187 Website. Sự phân bổ này phản ánh chính xác đặc thù của môi trường Internet thực tế, nơi các trang dịch vụ tổng hợp và tin tức thời sự luôn chiếm số lượng lớn. Trong khi đó, các cụm chủ đề chuyên biệt còn lại có độ phủ tương đối đồng đều, dao động từ 40 đến 85 Website mỗi cụm, cho thấy tính ổn định của thuật toán khi xử lý các miền dữ liệu ngách.

1. ` `**<a name="_toc231591536"></a><a name="_toc231766135"></a>Trực quan hóa dữ liệu**

Kết quả của quá trình phân cụm được trực quan thông qua biểu đồ cột biểu diễn số lượng Website trong mỗi cụm, với tổng số cụm k=12 cung cấp một cái nhìn trực quan về quy mô của tập dữ liệu sau khi thuật toán hội tụ. 

<img width="936" height="554" alt="image" src="https://github.com/user-attachments/assets/0d919586-bd13-4b02-949d-fedf05a1e765" />

<a name="_toc231764598"></a><a name="_toc231764791"></a>*Hình 3. *2*. Phân bố số lượng website trong 12 cụm sau huấn luyện.*

Biểu đồ cho thấy số lượng website trong các cụm đang tồn tại sự phân bổ bất đối xứng. Tập dữ liệu thể hiện sự phân hóa mạnh mẽ về mặt quy mô, cụ thể cụm 1 chiếm ưu thế tuyệt đối với 613 Website (chiếm gần một nửa tổng số mẫu khảo sát), tiếp theo là Cụm 12 với 187 Website. Sự chênh lệch lớn này là hoàn toàn hợp lý, phản ánh đúng bản chất của việc thu thập dữ liệu thô ngẫu nhiên trên Internet, nơi các nhóm chủ đề mang tính đại chúng (như dịch vụ giải trí tổng hợp, tin tức thời sự), ít chứa những từ vựng chuyên ngành để phân bố vào một cụm cụ thể, luôn có tần suất xuất hiện áp đảo.

Mặc dù tồn tại các cụm có kích thước quá lớn, thuật toán không gặp phải hiện tượng gom sai các phần tử nhỏ vào cụm lớn. Cụ thể, 10 cụm chuyên đề còn lại (từ Cụm 2 đến Cụm 11) duy trì được số lượng phần tử khá đồng đều, dao động trong biên độ hẹp từ 40 đến 85 Website. Điều này chứng tỏ thuật toán đã xác định thành công các điểm trọng tâm tách biệt cho từng ngách nội dung cụ thể, đảm bảo tính công bằng và toàn vẹn của kết quả phân nhóm.

Để đánh giá trực quan hình thái phân bổ của các Website sau khi chạy thuật toán K-Means, hệ thống sử dụng biểu đồ phân tán. Vì mỗi Website đang được biểu diễn dưới dạng vector TF-IDF có số chiều rất lớn, kỹ thuật giảm chiều dữ liệu PCA- Principal Component Analysis đã được áp dụng để nén dữ liệu xuống không gian 2 chiều với hai thành phần chính là PC1 và PC2 để tiến hành trực quan hóa. 

<img width="945" height="563" alt="image" src="https://github.com/user-attachments/assets/5d7f14a3-d504-465f-ba2d-1507a5f5b4f4" />

<a name="_toc231764599"></a><a name="_toc231764792"></a>*Hình 3. *3*. Trực quan hoá 12 cụm website trong không gian 2D (PCA).*

Phần lớn các điểm dữ liệu - đại diện cho các Website, tập trung thành một khối dày đặc ở khu vực góc trên bên trái của trục tọa độ khoảng PC1 từ -0.1 đến 0.1 và PC2 từ 0.0 đến 0.2. Sự chồng lấn này trên mặt phẳng 2D là hiện tượng hoàn toàn bình thường khi ép dữ liệu văn bản từ hàng nghìn chiều xuống 2 chiều, bởi nhiều trang web sẽ chia sẻ một lượng lớn từ vựng nền giống nhau. Cụm 1 - màu xanh dương nhạt, 613 Website, đóng vai trò là quần thể trung tâm do chứa lượng dữ liệu lớn nhất và mang tính đại chúng cao.

Mặc dù có sự tập trung ở trung tâm, đồ thị vẫn ghi nhận những cụm có tính tách biệt vươn hẳn ra ngoài:

- Theo trục hoành (PC1): Các điểm thuộc Cụm 9 (màu xám) kéo dài và tách biệt hoàn toàn về phía bên phải đồ thị (PC1 đạt tới 0.8).
- Theo trục tung (PC2): Các điểm thuộc Cụm 6 (màu tím nhạt) lại trải dài thành một dải phân bố độc lập hướng thẳng xuống dưới (PC2 tiệm cận -0.8).

Sự vươn dài và tách biệt này chứng minh rằng tập từ vựng của hai nhóm nội dung thuộc cụm 6 và cụm 9 có tính đặc thù và chuyên biệt rất cao, tạo ra phương sai lớn và khác biệt hoàn toàn so với phần còn lại của tập dữ liệu.

Các điểm cùng màu nhìn chung hội tụ bám sát lấy nhau thành từng vệt hoặc khối, rất ít hiện tượng điểm nhiễu bị văng quá xa khỏi cụm của mình. Điều này một lần nữa khẳng định thuật toán K-Means phân cụm đã tối ưu hóa tốt khoảng cách nội cụm, gom nhóm thành công các Website có chung đặc trưng ngữ nghĩa.

1. ` `**<a name="_toc231591537"></a><a name="_toc231766136"></a>Đánh giá chất lượng phân cụm**

Khác với các bài toán học có giám sát có thể sử dụng nhãn dữ liệu thực tế để tính toán tỷ lệ phân loại đúng sai, phân cụm Website bằng K-Means là bài toán học không giám sát. Do đó, việc đánh giá độ chính xác và chất lượng mô hình được thực hiện thông qua phương pháp đánh giá nội tại. Các chỉ số này tập trung phân tích cấu trúc hình học của các cụm dựa trên hai tiêu chí: mức độ gắn kết nội cụm và độ tách biệt giữa các cụm.

Tại cấu hình số cụm lựa chọn K = 12, hệ thống ghi nhận các kết quả đo lường nội tại thực nghiệm như sau:

|**Chỉ số**|**Giá trị**|**Giải thích**|**Đánh giá**|
| - | - | - | - |
|Silhouette Score [-1,1]|0\.0259|Độ tách biệt giữa cụm so với trong cụm|Điển hình với TF-IDF chiều cao|
|Calinski-Harabasz [0,∞) ↑|8\.7505|BGSS/WGSS – phân tán giữa/trong cụm|Tốt: phân tán giữa cụm > trong cụm|

<a name="_toc231764716"></a>*Bảng 3. *4*. Bảng đánh giá chất lượng phân cụm.*

- **Chỉ số WCSS:** 1255.4057

Giá trị WCSS đo lường tổng bình phương khoảng cách từ các điểm dữ liệu đến tâm cụm tương ứng của chúng. Quan sát tốc độ suy giảm hiệu số WCSS trong chuỗi thực nghiệm từ K = 2 đến K = 30:

- Giai đoạn tiệm cận ranh giới ( từ K = 11 đến K = 12): Khi tăng số lượng tâm cụm từ 11 lên 12, mô hình ghi nhận một bước cải thiện lớn về mặt không gian khi WCSS giảm mạnh 9.3208 đơn vị (từ  1264.7265  xuống  1255.4057 ). Điều này chứng tỏ việc bóc tách thêm cụm thứ 12 giúp thu hẹp đáng kể khoảng cách hình học nội cụm, mang lại hiệu quả phân loại ngữ nghĩa rõ rệt.
- Giai đoạn bão hòa cục bộ ( từ K = 12 đến K = 13 ): Ngay sau bước ngoặt trên, nếu tiếp tục tăng số cụm từ 12 lên 13, giá trị WCSS chỉ giảm thêm một lượng cực kỳ nhỏ là  1.7689  đơn vị (từ  1255.4057 xuống 1253.6368 ). Xu hướng gãy dốc này kéo dài liên tục cho đến tận  K = 30 , khi biên độ giảm giữa mỗi bước chỉ dao động mờ nhạt từ 1 đến 3 đơn vị.

Sự thay đổi đột ngột về độ dốc toán học (đang giảm mạnh  khoảng 9.32 đơn vị bỗng dừng khựng lại và chỉ còn giảm khoảng 1.77 ) chính là minh chứng thực nghiệm xác lập vị trí  K = 12  là điểm khuỷu tay trên đồ thị tối ưu. Tại điểm này, mô hình đạt được sự cân bằng lý tưởng: giảm thiểu tối đa sai số nội cụm mà không làm cấu trúc dữ liệu bị phân mảnh quá mức hoặc gia tăng chi phí tính toán vô ích.

- **Chỉ số Silhouette Score:** 0.0259

Chỉ số Silhouette đánh giá chất lượng cấu trúc cụm trên thang đo từ -1 đến 1. Điểm số ghi nhận được là  0.0259 . Dù mang giá trị dương khẳng định các Website nhìn chung đã được xếp vào đúng cụm phù hợp hơn là cụm lân cận, nhưng con số này nằm khá sát mức 0. Thay vì phản ánh một lỗ hổng trong mã nguồn, kết quả này phản ánh chính xác các đặc thù kỹ thuật sau:

- Ma trận trọng số TF-IDF tạo ra một không gian vector thưa có kích thước lên tới hàng ngàn chiều tương ứng với độ dài từ điển văn bản. Trong không gian siêu cao chiều này, khoảng cách Euclidean giữa các điểm dữ liệu có xu hướng bị bão hòa và xấp xỉ nhau, khiến điểm Silhouette tính toán tuyến tính bị kéo giảm một cách tự nhiên.
- Việc Silhouette tiệm cận 0 phản ánh ranh giới giữa các cụm không cô lập hoàn chỉnh mà có sự giao thoa. Như đã phân tích tại Cụm 1, các Website trên Internet luôn chia sẻ chung một lượng lớn từ vựng nền tảng (như home, contact, service, information). Tập từ vựng dùng chung này hoạt động như một lực hút kéo các điểm dữ liệu về phía lõi trung tâm, tạo ra sự chồng lấn nhẹ trên mặt phẳng hình học dù bản chất chủ đề ngách của chúng có sự khác biệt.
- **Chỉ số Calinski-Harabasz Index:** 8.7505

Chỉ số Calinski-Harabasz đo lường tỷ lệ giữa độ phân tán giữa các cụm và độ phân tán nội cụm. Giá trị đạt 8.7505 là một mức điểm ổn định đối với tập dữ liệu văn bản thô chưa qua các bước giảm chiều sâu. Chỉ số này củng cố nhận định: thuật toán K-Means tự triển khai đã hoàn thành tốt nhiệm vụ phân tách các trọng tâm để tạo ra các miền nội dung có độ phủ đồng đều (từ 40 đến 85 Website ở các cụm ngách), kiểm soát tốt việc các cụm nhỏ bị quần thể trung tâm (Cụm 1) nuốt chửng.

Tóm lại**,** hệ thống chỉ số nội tại khẳng định thuật toán K-Means đã vận hành hoàn toàn chính xác theo đúng logic toán học và đạt được sự hội tụ tối ưu tại  K = 12 . Mặc dù đặc thù phức tạp và thưa thớt của không gian vector TF-IDF đặt ra nhiều thách thức cho các hàm đo khoảng cách hình học truyền thống, mô hình vẫn bóc tách thành công cấu trúc dữ liệu để phục vụ việc phân loại chủ đề Website với độ tin cậy cao.

1. <a name="_toc231591538"></a><a name="_toc231766137"></a>**Nhận xét kết quả**

Mô hình phân cụm Website bằng Kmeans đã đạt được kết quả với một số ưu điểm như:

- Tính chính xác: Quá trình tính toán khoảng cách nội cụm, gán nhãn và cập nhật tâm cụm hoạt động ổn định, minh chứng qua việc phân lập thành công 12 nhóm chủ đề Website riêng biệt với các từ khóa trung tâm sát với thực tế.
- Hiệu quả của quy trình tiền xử lý văn bản: Các bước làm sạch dữ liệu, loại bỏ từ dừng và áp dụng trọng số TF-IDF đã hoạt động hiệu quả. Việc chuyển đổi văn bản thành vector số giúp thuật toán dễ dàng tính toán khoảng cách hình học, đồng thời phương án lưu trữ dưới dạng ma trận thưa tự thiết kế đã giúp tiết kiệm đáng kể tài nguyên bộ nhớ máy tính khi xử lý tập từ vựng có số chiều lớn.
- Khả năng bóc tách ngữ nghĩa chi tiết: Mô hình không chỉ nhận diện được các nhóm chủ đề lớn như tin tức, giải trí mà còn có khả năng phân rã các ngách nội dung hẹp. Việc tách biệt thành công nhóm Website thương mại điện tử chuyên đồ mẹ và bé( cụm 8) và nhóm thời trang (cụm 10) là một điểm sáng, cho thấy sự nhạy bén của thuật toán đối với sự thay đổi tần suất của tập từ vựng đặc thù.

Tuy nhiên bên cạnh những kết quả tích cực, do giới hạn về mặt phương pháp, mô hình vẫn còn một số điểm hạn chế:

- Tính không ổn định do khởi tạo ngẫu nhiên: đồ thị độ lỗi không giảm trơn tru mà có những điểm gãy khúc tăng ngược trở lại (ví dụ từ K=8 lên K=9). Nguyên nhân là do thuật toán K-Means cơ bản chọn tâm cụm ban đầu một cách hoàn toàn ngẫu nhiên. Nếu vô tình chọn phải các Website có nội dung lai tạp làm tâm, thuật toán sẽ bị mắc kẹt tại cực tiểu địa phương, dẫn đến kết quả phân cụm của vòng lặp đó không đạt được độ tối ưu cao nhất.
- Hạn chế về chi phí tính toán: Việc không sử dụng các thư viện tối ưu hóa phép toán ma trận buộc mã nguồn phải sử dụng các vòng lặp tuần tự để tính khoảng cách từ hàng ngàn Website tới các tâm cụm ở không gian hàng vạn chiều. Điều này khiến thời gian thực thi của thuật toán khá chậm, khó đáp ứng được yêu cầu phân tích dữ liệu theo thời gian thực nếu mở rộng tập dữ liệu lên hàng triệu Website.
- Giới hạn ngữ nghĩa của kỹ thuật TF-IDF: Kỹ thuật vector hóa TF-IDF thuần túy chỉ dựa trên thống kê tần suất xuất hiện của từ ngữ mà không nắm bắt được bối cảnh hoặc các từ đồng nghĩa. Do đó, các Website sử dụng từ vựng khác nhau nhưng mang cùng một ý nghĩa có thể bị thuật toán đẩy ra xa nhau, làm giảm độ tinh khiết của một số cụm chuyên ngành.

Những hạn chế này chính là cơ sở thực tiễn quan trọng để đề tài mở ra các hướng nghiên cứu và cải tiến tiếp theo trong tương lai.


2

