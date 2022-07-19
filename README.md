# swisschess
Bốc thăm hệ thụy sĩ cho đấu giải cờ vua

Object: Người chơi, gồm tên,STT,Ván 1-7 array, bao gồm [trắng/đen;thắng/hòa/thua],điểm,hệ số

Pairing ngẫu nhiên ván đầu tiên của cặp 1-1

Sau mỗi ván đấu, thực hiện pairing bao gồm điểm rồi đến hệ số của các cặp từ cao nhất tới thấp nhất
assign trắng win và đen win hệ số cho mỗi vòng. V1 thấp hơn,V7 cao nhất(vẫn ưu tiên tính điểm trước)
  V1-V7 trắng: 2 4 6 8 10 12 14
  V1-7 đen: 3 5 7 9 11 13 15
  V1-7 nghỉ: 1 3 5 7 9 11 13
Cần tìm hiểu các vấn đề
  Cách lưu danh sách được nhập vào file Json
  Cách lấy data Json và xuất ra cặp đấu
  function vòng (v1-v7,trắng,đen,kết quả:1 0/0.5 0.5/0-1)
  Xuất page có tên là thứ hạng, list theo thứ tự từ điểm, tới hệ số
  function pairing, cho mỗi người 1 số điểm hệ số ngẫu nhiên từ 0.01-0.99 1 cách random
    Như vậy pairing sẽ từ cao xuống thấp, nếu Xn cao nhất, thì lấy Xn-1 cặp với X
    Do function đánh ngẫu nhiên 0.01-0.99, nên kết quả bốc thăm random sẽ được định đoạt ngay sau khi assign object
    function hệ số random+vào
    function loại trừ X gặp Xn-1 nếu function check(x,Xn-1)==true
    Do điểm random rất ít, nên chỉ cần thắng/thua là sẽ vượt lên ngay
FUnction đen trắng, vòng 1 ngẫu nhiên? 
  Function đen trắng (X,Y) trả về 1 trắng 1 đen, ưu tiên nếu trước đó đã cầm đen/trắng(ngược)>Trắng cho người ít điểm hơn
Thứ tự thực hiện 
  1: Lấy các object là người chơi
  2: Assign hệ số 0.01-0.99 trên dưới ngẫu nhiên
  3: Random trắng đen V1
  4: Pairing 
  5: Từ Xn(nhất), check nếu Xn-1 chưa gặp, (pairing,function đen trắng(X,Y) ) tiếp tục xuống dưới
  6: Xuất bảng ranking, sorting từ cao>hệ số
  7
