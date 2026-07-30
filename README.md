# RicohCounterAgent — Updates

Kho phát hành bản cập nhật cho **Ricoh Counter Agent** (đọc counter máy photocopy Ricoh qua SNMP).

Kho này **chỉ chứa file cập nhật**, không chứa mã nguồn và không chứa bất kỳ khóa/mật khẩu nào.
Agent trên máy khách đọc kho này 6 giờ một lần, tải về khi có bản mới hơn và tự vá.

| File | Ý nghĩa |
|---|---|
| `version.txt` | Số phiên bản mới nhất. Agent chỉ vá khi số này **lớn hơn** bản đang chạy. |
| `Update.zip` | 3 file nhị phân thay đổi + `version.txt`. |
| `Update.sha256` | SHA-256 của `Update.zip`. Agent đối chiếu trước khi vá, sai thì hủy. |
| `whatsnew.txt` | Ghi chú bản phát hành. |

Kho phải để **public**: agent cố tình không mang theo token nào, vì file `.exe` phát cho khách
thì ai cũng moi được token ra.

Phát hành bản mới (chạy trên máy phát triển):

```powershell
installer\release-agent.ps1 -Bump patch -UpdatesRepo <đường dẫn kho này> -Push
```
