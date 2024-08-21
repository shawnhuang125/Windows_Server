# Windows Server 升級為Domain Controler 及網域配置
- 1.打開 Server Manager
- 登錄到你的 Windows Server 虛擬機。
- 打開 Server Manager（服務器管理員）。這通常會在你登錄後自動打開。如果沒有，點擊左下角的「開始」按鈕，然後選擇「Server Manager」。
- ![螢幕擷取畫面 2024-08-20 104748](https://github.com/user-attachments/assets/8e3667f2-5825-4544-be94-d89c39182b26)
- 2.添加 Active Directory Domain Services 角色
- 在 Server Manager 的首頁，點擊右上角的 "Manage"，然後選擇 "Add Roles and Features"（添加角色和功能）。
- ![螢幕擷取畫面 2024-08-20 104815](https://github.com/user-attachments/assets/f4943bca-ee69-447a-b39f-017f043cf0ed)
- 在 "Before you begin" 頁面，點擊 "Next" 繼續。
- ![螢幕擷取畫面 2024-08-20 104836](https://github.com/user-attachments/assets/47185fbe-0e9e-4b37-8b44-eaa1ac67e4ac)

- 在 "Installation Type"（安裝類型）頁面，選擇 "Role-based or feature-based installation"（基於角色或功能的安裝），然後點擊 "Next"。
![螢幕擷取畫面 2024-08-20 104856](https://github.com/user-attachments/assets/f48c9181-2f87-4628-8231-3a4b18fa0de2)

- 在 "Server Selection"（服務器選擇）頁面，確保選中了當前的伺服器，然後點擊 "Next"。
![螢幕擷取畫面 2024-08-20 104924](https://github.com/user-attachments/assets/68bb7879-fab6-4587-9fdd-9d61ee0f180f)

- 在 "Server Roles"（服務器角色）頁面，找到並勾選 "Active Directory Domain Services"。
- ![螢幕擷取畫面 2024-08-20 105054](https://github.com/user-attachments/assets/bb6284a4-9741-45f6-bb55-db29174317fe)

- 出現提示時，點擊 "Add Features"（添加功能）來安裝所需的其他功能，然後點擊 "Next"。
- 在 "Features"（功能）頁面，直接點擊 "Next"，因為安裝 AD DS 已經包含了所需的功能。
- ![螢幕擷取畫面 2024-08-20 105054](https://github.com/user-attachments/assets/517c7ab8-9494-4453-95bd-d49118127663)

- 在 "AD DS"（Active Directory Domain Services）頁面，會看到一些關於 AD DS 的信息，直接點擊 "Next"。
![螢幕擷取畫面 2024-08-20 105128](https://github.com/user-attachments/assets/c7dea0c9-9c77-46fa-ac20-b49e4dac684d)
- 在 "Confirmation"（確認）頁面，檢查要安裝的角色和功能，然後點擊 "Install" 開始安裝。
- ![螢幕擷取畫面 2024-08-20 105150](https://github.com/user-attachments/assets/ee7044a9-bcad-4016-800f-316f5244c74c)

- 3.配置 Active Directory Domain Services
- 安裝完成後，在 Server Manager 的頂部，會看到一個通知，提示你進行更多配置。點擊 "Promote this server to a domain controller"（將此服務器提升為域控制器）。
- ![螢幕擷取畫面 2024-08-20 105415](https://github.com/user-attachments/assets/fdf694a8-345b-4bda-a76a-0bf591331986)

- 在 "Deployment Configuration"（部署配置）頁面，你有幾個選項：
- ![螢幕擷取畫面 2024-08-20 105526](https://github.com/user-attachments/assets/5465823e-bf0e-4fb4-a67b-f1b765cdec82)

- 添加一個新森林（Add a new forest）：這是在新的 AD 網域中創建一個新的根網域。輸入你的根網域名（例如 example.local），然後點擊 "Next"。
- ![螢幕擷取畫面 2024-08-20 105806](https://github.com/user-attachments/assets/11830490-201b-44af-8be9-5747de721927)

- 在 "Domain Controller Options"（域控制器選項）頁面，設置以下參數：
- ![螢幕擷取畫面 2024-08-20 105920](https://github.com/user-attachments/assets/e84c3ed4-36db-4709-b518-144e930dacff)

- Forest functional level 和 Domain functional level：選擇相應的功能級別。對於最新的功能，可以選擇 -Windows Server 2016 或 Windows Server 2019。
- Domain Name System (DNS) server：確保選中該選項以安裝 DNS 服務器。
- Global Catalog (GC) 和 Read only domain controller (RODC)：默認情況下，選擇 Global Catalog，並且不選 RODC。
- Directory Services Restore Mode (DSRM) 密碼：設置一個 DSRM 密碼，這個密碼將在需要從備份中還原 AD 時使用。
- 在 "DNS Options" 頁面，如果看到一個 DNS 委派警告，可以忽略並點擊 "Next"。
- ![螢幕擷取畫面 2024-08-20 105940](https://github.com/user-attachments/assets/ccec65d2-43f2-40bb-a98d-872b88d75d6d)

- 在 "Additional Options" 頁面，驗證 NetBIOS 名稱，然後點擊 "Next"。
- ![螢幕擷取畫面 2024-08-20 110026](https://github.com/user-attachments/assets/33c8cdfe-6f0f-4edc-b567-e479d6b1dd08)

- 在 "Paths" 頁面，確認數據庫、日誌文件和 SYSVOL 的路徑，這些通常保持默認即可，然後點擊 "Next"。
- ![螢幕擷取畫面 2024-08-20 110108](https://github.com/user-attachments/assets/39b1c4b3-5e0e-4f7f-be0a-96cf64b1a0f9)

- 在 "Review Options" 頁面，檢查你的配置，如果一切正確，點擊 "Next"。
- ![螢幕擷取畫面 2024-08-20 110145](https://github.com/user-attachments/assets/cb0417ce-4bb9-47e3-b6ed-979d592b67ad)

- 在 "Prerequisites Check" 頁面，等待預檢完成，如果沒有錯誤，點擊 "Install" 來開始安裝。
- ![螢幕擷取畫面 2024-08-20 110217](https://github.com/user-attachments/assets/1b2456eb-e961-4cfc-a1ca-91b9a9c3d381)
- ![螢幕擷取畫面 2024-08-20 110235](https://github.com/user-attachments/assets/a71a01d9-fec9-4f88-8f03-73ee5c6cbb6e)
- 4.完成安裝並重啟伺服器

- 安裝完成後，伺服器會自動重啟以應用更改。
- 重啟後，伺服器將作為網域控制器運行，你可以開始配置和管理 Active Directory。

- 5.確認Windows AD 的架構、配置、以及 DNS 相關的功能都是正常的。
- 導覽列輸入CMD,按ENTER。進入Windows AD的cmd。
```
dcdiag /v
```
- ![圖片1](https://github.com/user-attachments/assets/1ea31cef-6a4e-4d07-9649-cfb19366b813)
- ![圖片2](https://github.com/user-attachments/assets/87b5c8fd-f5dd-4c67-9ef9-d00ea6795b8e)

