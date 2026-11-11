# Termark 本地解密工具

在浏览器中解密 Termark 本地数据库或云同步 `.dat` 快照，查看主机、凭证及相关敏感字段。

**在线使用：** <https://youhongxing.github.io/termark-local-decryptor/>

## 使用方法

1. 打开上方页面，选择解密来源。
2. 选择 Termark 的 `termark.db` 或完整的同步 `.dat` 文件。
3. 输入对应的密钥或密码，然后点击「解密」。
4. 使用主机名或 IP 搜索记录。同步快照也可以查看完整的解密 JSON。

## 支持的来源

- **本地数据库**：支持 Termark `enc:v1:` 字段。输入 32 字节本地数据密钥，或从数据库读取参数并通过本地加密口令派生。
- **同步快照**：支持包含 `version` 和 `data` 字段的 Termark `.dat` / `.json` 快照，输入 Termark 云同步密码。
- **单个字段**：粘贴 `enc:v1:` 密文并输入本地数据密钥。

macOS 本地数据库默认位于 `~/Library/Application Support/Termark/backend/termark.db`。Windows 安装版默认位于 `%AppData%\Termark\backend`，Windows 便携版数据位于程序目录的 `data` 文件夹。

## 隐私

工具使用浏览器本地文件读取和 Web Crypto 解密。数据库、快照、密码和解密结果不会上传到此网站。请仅在可信设备上输入密钥。GitHub Pages 和这个公开仓库对所有人可见。
