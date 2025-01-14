# 學習指引
## 基礎知識打底
- 熟悉網路基礎[計算機網路](https://github.com/shawnhuang125/Computer_Network.md/blob/main/README.md)
- 了解網路基礎概念（如 IP 地址、子網、DNS、DHCP 等）。
- 理解域、域控制器、工作組的概念及其差異。
- 學習 TCP/IP 協議，尤其是 DNS 的作用，因為 AD 強烈依賴 DNS 進行名稱解析。
- Windows Server 基礎：
- 學習 Windows Server 操作系統的基本操作，了解伺服器角色、功能、和管理工具。
- 熟悉 Windows Server 的安裝、配置和基本管理（如使用伺服器管理員、遠端桌面連線等）。
- AD 相關概念：
- 了解 Active Directory 的基本結構，包括域、樹、森林、組織單位 (OU)、用戶、組、電腦等。
- 學習 LDAP 協議的基本概念，因為 AD 使用 LDAP 進行目錄服務。
## 實踐操作練習
- [安裝與配置](https://github.com/shawnhuang125/Windows_Server/blob/main/AD_DS_Setup.md)：
- 實際安裝 Windows Server，並在虛擬機或測試環境中配置 Active Directory。
- 熟悉 AD 的安裝步驟和[AD基本配置](https://github.com/shawnhuang125/Windows_Server/blob/main/AD_DS_Setup.md)，學會創建域和域控制器。
- 用戶與群組管理：
- 學習如何在 AD 中[創建用戶](https://github.com/shawnhuang125/Windows_Server/blob/main/Add_PC_To_Domain.md)、管理用戶帳戶和群組，並配置相應的權限。
- 熟悉 ADUC 工具的使用，瞭解如何組織和管理組織單位 (OU)。
- 群組策略 (GPO)：
- 學習群組策略的基本概念，瞭解如何創建和應用 GPO 來管理用戶和電腦設定。
- 實際操作 GPMC 工具，設置並部署基本的安全策略和環境配置。
- DNS 與網路服務：
- 深入學習 DNS 的配置與管理，了解其在 AD 中的重要性。
- 掌握如何排除 DNS 問題，並確保名稱解析的準確性和可靠性。
- AD 複製與健康狀況監控：
- 學習 AD 複製的基本概念，了解如何檢查和解決複製問題。
- 掌握 AD 的健康狀況監控工具和技術，如使用 repadmin 和 dcdiag 進行診斷。
## 進階學習與應用
- 高級功能與架構設計：
- 了解和實踐 AD 信任關係的設置及跨域管理。
- 學習如何設計和實施多站點的 AD 架構，掌握站點和服務的配置。
- 瞭解和配置證書服務 (Active Directory Certificate Services, AD CS) 以實現安全通信。
- 備份與恢復：
- 掌握 AD 的備份和恢復策略，了解如何進行系統狀態的備份和災難恢復。
- 熟悉 DSRM 模式及其應用場景，學會使用 Windows Server Backup 進行定期備份。
- 安全性強化：
- 學習如何加強 AD 的安全性，配置審計策略和登錄事件監控。
- 了解和實踐權限管理，確保用戶和組有適當的權限，防止未經授權的訪問。
