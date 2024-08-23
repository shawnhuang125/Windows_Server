# Add PC To Domain Step By Step
## 1. 設定網路設定
- 網路模式：確保Windows 10 和Windows Server 虛擬機器都連接到同一個網路。可使用VirtualBox 的「內部網路（Internal Network）」或「橋接網路（Bridged Adapter）」模式。
- 1-1.進入虛擬機設置後,找到"網路",選擇「橋接網路（Bridged Adapter）」,然後選擇自己電腦的有線網路介面卡
- ![螢幕擷取畫面 2024-08-23 150953](https://github.com/user-attachments/assets/6dfa3412-a12f-4664-8429-55a1c82adc87)
- 1-2.這邊是使用「橋接網路（Bridged Adapter）」模式
- ![螢幕擷取畫面 2024-08-23 151039](https://github.com/user-attachments/assets/25fc4728-a5cf-4a52-b801-fb9c1b4283a4)
- ![圖片8](https://github.com/user-attachments/assets/97f092f2-f1f9-4cda-b622-4f6019d5bc75)
## 2. 檢查網路連接
- 2-1.在Windows 10 上，嘗試ping Windows Server 的IP 位址，以確保它們之間的網路通訊正常。
```
ping 192.168.1.xxx
```
- ping 192.168.1.xxx回復成功
![螢幕擷取畫面 2024-08-23 151211](https://github.com/user-attachments/assets/907cc952-0be7-4351-bddf-5f096eb547b1)
## 3. 配置Windows 10 的DNS
- DNS 設定：在Windows 10 虛擬機器中，將DNS 伺服器設定為Windows Server 的IP 位址。這個操作可以在網路介面卡的屬性中完成。
- 3-1.windows 10的桌面點擊控制台
- ![螢幕擷取畫面 2024-08-23 153223](https://github.com/user-attachments/assets/8fbffb5c-01c1-43c3-a703-41362ceea568)
- 3-2.進入控制台
- ![圖片7](https://github.com/user-attachments/assets/8d5e0937-feb3-4b2f-b792-06c5ac531a1f)
- 3-3.開啟網路共用中心
- ![圖片6](https://github.com/user-attachments/assets/5eb73a82-4acb-4bfb-8ed6-f71795cee596)
- 3-4.開啟「網路和共用中心」 > 「變更介面卡設定」。
- ![圖片5](https://github.com/user-attachments/assets/d3598e09-ebdb-4587-bf09-2bad93db51de)

- 3-5.右鍵點選網路介面卡，選擇「內容」。
- ![圖片4](https://github.com/user-attachments/assets/f544eca5-7e4e-416f-8e0e-e01b2f098ed1)

- 3-6.記得關掉IPv6服務,確保造訪的DNS服務器為本地架設的Winodws Server的DNS服務器位址
- ![圖片9](https://github.com/user-attachments/assets/5330b103-499d-4d9b-9afd-2e5ca65098ae)
- 3-7.雙擊「Internet 協定版本4 (TCP/IPv4)」。
- ![圖片9](https://github.com/user-attachments/assets/7365dbaf-d644-4951-b31e-ca9a66a80dae)
- 3-8.在「首選DNS 伺服器位址」中，輸入Windows Server 的IP 位址。
```
192.168.1.xxx
```
- ![圖片2](https://github.com/user-attachments/assets/eb340dec-59cf-4ac6-8091-49a758d44085)
## 4. 確認可造訪Winodws Server的DNS伺服器,將Windows 10 加入網域
- 4-1.進入導覽列搜尋cmd,左鍵點擊開啟
- ![螢幕擷取畫面 2024-08-23 150515](https://github.com/user-attachments/assets/0ff2ac06-054b-427e-8be7-867aca95898a)
- 4-2.輸入指令ping Winodws Server確認在同一個網路下可以互相通信
```
nslookup xxx.local
```
- ![螢幕擷取畫面 2024-08-23 142425](https://github.com/user-attachments/assets/7cb2667a-d163-4348-8a59-04d5fd7a0b20)

- 4-3.開啟導覽列,輸入Powershell
- ![螢幕擷取畫面 2024-08-23 150705](https://github.com/user-attachments/assets/062f7975-8806-48b2-8797-0282191f1000)
- 4-4.右鍵點擊,選擇"以管理員身分執行"
![螢幕擷取畫面 2024-08-23 150705](https://github.com/user-attachments/assets/c8fdcaad-9bca-417f-92f7-d88bcf05042b)
- 4-5.輸入指令加入Domain
- 4-6.輸入管理員密碼
```
Add-Computer -DomainName "xxxx.local" -Credential "xxxx\Administrator" -Force -Restart
```
![螢幕擷取畫面 2024-08-23 150752](https://github.com/user-attachments/assets/f6e7d5bb-8b90-4d56-8a16-077f037e7f36)
- 4-7.系統自動重新啟動,應用更改設置
- 4-8.若沒有設置用戶密碼,直接按"-->"
- 4-9.進入後即成功加入網域
- 5.確認PC已加入Domain
- 5-1.進入windows server 虛擬機,登入管理員密碼
- 5-2.進入導覽列輸入"Server Manager"
- ![螢幕擷取畫面 2024-08-23 143231](https://github.com/user-attachments/assets/e6f8cec1-85b8-476d-b88b-6d37d9c2bdf4)

- 5-3.點擊"TOOLS"
- ![圖片1](https://github.com/user-attachments/assets/9f75b004-6c4f-46c4-b4bf-7cf72d2d11af)

- 5-4.看到"Active Directory Users And Computers"
- ![螢幕擷取畫面 2024-08-23 145501](https://github.com/user-attachments/assets/7ced7d9c-d381-41a4-a527-f9be48db68c6)
- 5-5.點擊xxxxx.local
- 5-6.底下會展開目錄,找到"Computers",雙擊即可看到Domain底下的PC名稱
- ![螢幕擷取畫面 2024-08-23 143334](https://github.com/user-attachments/assets/7ce8fb44-bd3c-4023-8571-5031da4be31a)

