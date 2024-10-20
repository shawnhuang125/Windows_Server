# Windows Server 安裝與配置
## 安裝指南
### 安裝 Windows Server OVA | [Winodws Server 2022官方網站](https://www.microsoft.com/zh-tw/evalcenter/download-windows-server-2022)
- 導入下載好的ISO檔
- ![image](https://github.com/user-attachments/assets/96806c41-b2e9-4a2b-a76b-3ba3a69e6674)
- ![image](https://github.com/user-attachments/assets/025e1d16-ee2e-401c-ba98-c3343e638d21)
- 啟動後，將進入 Windows Server 的安裝界面。選擇安裝語言、時區和鍵盤配置。
- ![image](https://github.com/user-attachments/assets/854a7178-e863-46d0-a347-48c07e3ce62d)
- ![image](https://github.com/user-attachments/assets/dd24640d-649a-4dca-8fcc-782058fe5644)
- ![image](https://github.com/user-attachments/assets/4d295b70-5d36-4c25-9f25-09baa0d34d30)
- ![image](https://github.com/user-attachments/assets/a93199ea-952e-47b1-8b28-89d18f5f9c39)
- ![image](https://github.com/user-attachments/assets/15804629-7e98-4b96-943c-3bec43ea34a6)
- ![image](https://github.com/user-attachments/assets/ecf2c0af-b7c4-4fe7-94ba-7e8f261d80d0)
- ![image](https://github.com/user-attachments/assets/8bc1a1af-8ad0-4fcd-8434-1961c5188b69)
- 
- 選擇磁碟：選擇要安裝的磁碟，如果需要，您可以分區或格式化磁碟。
- ![image](https://github.com/user-attachments/assets/2593e65f-c9d2-4c7b-99a4-4497e3b44dc4)
- 開始安裝：確認安裝配置後，安裝程序將開始將 Windows Server 安裝到指定磁碟。
- ![image](https://github.com/user-attachments/assets/aefbe514-20ff-4035-97e5-b6d526c72b78)
### 1.從 [Microsoft 官方網站](https://www.microsoft.com/zh-tw/evalcenter/download-windows-server-2022)下載
- 訪問 [Microsoft 官方網站](https://www.microsoft.com/zh-tw/evalcenter/download-windows-server-2022)：
- ![image](https://github.com/user-attachments/assets/89494bbc-3fd3-49ee-a0fb-f1f42215936d)
- 典籍下載後可能會需要註冊才能下載(點擊下載後,若直接開始下載請忽略)
  - 您可能需要用 Microsoft 賬號登錄並註冊才能下載 ISO 檔案。
  - 選擇 “ISO” 作為下載格式。
  - 提交註冊信息後，您將獲得下載鏈接。
### 2.創建啟動媒體(灌PC)
- 您需要將 ISO 檔寫入到 USB 驅動器或 DVD，以便用來啟動和安裝 Windows Server。
- 使用 USB 驅動器
- 準備 USB 驅動器：需要一個容量至少為 8GB 的 USB 驅動器，並確保驅動器裡的數據已經備份，因為創建過程會格式化它。
- 使用工具創建啟動盤：
- 使用 Rufus 工具或 Windows 的內建工具 來創建啟動盤。
- 打開 Rufus，選擇您的 USB 驅動器，然後選擇剛下載的 ISO 檔案。
- 點擊 “Start” 來開始創建啟動盤。
- 使用 DVD
- 燒錄 ISO 檔：如果您打算使用 DVD，請使用燒錄軟件（如 Windows 自帶的光碟刻錄工具或第三方軟件）來將 ISO 檔燒錄到 DVD 上。
### 3.設定 BIOS/UEFI 以從啟動媒體啟動(灌PC)
- 進入 BIOS/UEFI：在服務器或電腦啟動時，通常按下 F2, F10, F12, Delete 或 Esc 鍵進入 BIOS 或 UEFI 設置。
- 設置啟動順序：在 BIOS/UEFI 中，將 USB 驅動器或 DVD 設置為首選啟動設備。
- 保存並重啟：保存 BIOS/UEFI 設置並重啟服務器，系統將從您創建的啟動媒體啟動。
### 4.開始安裝 Windows Server
- 選擇安裝類型：啟動後，將進入 Windows Server 的安裝界面。選擇安裝語言、時區和鍵盤配置。
- 輸入產品金鑰：根據要求輸入 Windows Server 的產品金鑰（有些版本可能會跳過這一步）。
- 選擇安裝版本：選擇要安裝的版本（例如：標準版、數據中心版等），並決定是否安裝帶桌面體驗的版本。
- 選擇安裝類型：選擇 “自訂：僅安裝 Windows (進階)” 以執行全新安裝。
- 選擇磁碟：選擇要安裝的磁碟，如果需要，您可以分區或格式化磁碟。
- 開始安裝：確認安裝配置後，安裝程序將開始將 Windows Server 安裝到指定磁碟。
## 配置
### 5.完成初始配置
- 設置管理員帳戶：安裝完成後，系統會要求您設置管理員帳戶密碼。
- 首次登錄：使用管理員帳戶登錄到新安裝的 Windows Server 系統。
- 配置網絡：配置網絡設置，包括 IP 地址、子網掩碼、默認網關和 DNS 伺服器。
- 執行 Windows 更新：更新系統以安裝最新的安全更新和修補程序。
### 6.安裝和配置角色及功能
- 使用 Server Manager：打開 Server Manager，添加所需的角色（如 AD DS、DNS、DHCP 等）和功能。
- 配置角色和功能：按照需求進行詳細的配置，如設定域控制器、配置 DHCP 範圍、設置文件伺服器等。
