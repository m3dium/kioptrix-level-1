# kioptrix-level-1

Dùng nmap scan:

![image](https://user-images.githubusercontent.com/72652376/181724626-a872bab4-aead-463d-868e-414a30b6c329.png)

![image](https://user-images.githubusercontent.com/72652376/181724670-8609bd9c-0a9e-4ce8-9ce0-0a239c5b1024.png)

Có rất nhiều thông tin, cho nên ta xử lý từ các port thông dụng có thể khai thác trước

Thử đục vào port 139 (SMB) đầu tiên:

Dùng 1 module trong msf để scan version của smb thu được

![image](https://user-images.githubusercontent.com/72652376/181725822-19062b25-b545-4571-9bef-67f01a088af7.png)

Tìm kiếm xem có thể khai thác được phiên bản này không thì hiện ngay ra quả RCE nhưng phiên bản samba <2.2.8

![image](https://user-images.githubusercontent.com/72652376/181725958-dd8df994-7df5-4530-b331-354ae0ee6d35.png)

Thậm chí còn có hẳn 1 module trong mfs để khai thác

![image](https://user-images.githubusercontent.com/72652376/181726534-9a9a85ae-22ac-4f4a-907b-e8731fc641aa.png)

![image](https://user-images.githubusercontent.com/72652376/181726650-3a342f37-ee4f-4d15-b99f-a441bcd1b8fd.png)

Module này dùng overflow để thực thi shell_reverse

![image](https://user-images.githubusercontent.com/72652376/181726975-ba03298b-90c3-465f-bcc2-83a653ec5a7b.png)

kiểm tra id thì có thể thấy đang ở root. DONE !


Tiếp tục kiểm tra tới port 80

![image](https://user-images.githubusercontent.com/72652376/181728309-6b0442dd-c211-495b-bf58-229dc2c2b33a.png)

mình tìm được đoạn mã C thực hiện khai thác https://github.com/heltonWernik/OpenLuck 

![image](https://user-images.githubusercontent.com/72652376/181731962-9a4de370-f190-4710-a40e-4d680bd88c01.png)

Nhưng chỉ dừng ở user ubuntu


