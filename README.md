# Termark Local Decryption Tool | Termark 本地解密工具

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

## 实现依据

本工具依据 Termark 官方加密说明实现，并按本地数据和云同步两种格式分别处理：

- [本地加密与数据恢复说明](https://www.termark.app/zh/docs/local-encryption)：本地数据密钥、本地敏感字段加密和便携版口令派生。
- [云同步说明](https://www.termark.app/zh/docs/cloud-sync)：同步密码派生密钥及同步快照加密。

## 隐私

工具使用浏览器本地文件读取和 Web Crypto 解密。数据库、快照、密码和解密结果不会上传到此网站。请仅在可信设备上输入密钥。GitHub Pages 和这个公开仓库对所有人可见。


## English

Decrypt Termark local databases and cloud sync `.dat` snapshots in your browser.

**Open the tool:** <https://youhongxing.github.io/termark-local-decryptor/>

### Usage

1. Open the page and select a source.
2. Choose a `termark.db` file or a complete sync `.dat` snapshot.
3. Enter the matching local data key, local encryption passphrase, or sync password, then select **Decrypt**.
4. Search for a host by name or IP address. For sync snapshots, you can also view the full decrypted JSON.

### Supported sources

- **Local database:** Termark `enc:v1:` fields. Enter the 32-byte local data key, or derive it from the local encryption passphrase and KDF parameters stored in the database.
- **Sync snapshot:** Termark `.dat` / `.json` snapshots with `version` and `data` fields. Enter the Termark cloud sync password.
- **Single field:** Paste an `enc:v1:` ciphertext and enter the local data key.

Default database locations are `~/Library/Application Support/Termark/backend/termark.db` on macOS, `%AppData%\Termark\backend` on installed Windows builds, and the `data` folder next to the application on Windows portable builds.

### Implementation references

This tool follows Termark’s official encryption documentation and handles local data and cloud sync formats separately:

- [Local Encryption and Data Recovery](https://www.termark.app/docs/local-encryption) covers local data keys, encrypted fields, and portable-build passphrase derivation.
- [Cloud Sync](https://www.termark.app/docs/cloud-sync) covers sync-password key derivation and snapshot encryption.

### Privacy

The tool reads files and decrypts data in your browser. It does not upload database files, snapshots, passwords, or decrypted results to this website. Enter keys only on a device you trust. This repository and its GitHub Pages site are public.
