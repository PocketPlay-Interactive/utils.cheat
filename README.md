# Utils.Cheat

Thư viện hỗ trợ kiểm tra checksum và che giấu dữ liệu bộ nhớ cho Unity (C#).

## Tính năng
- Tạo và kiểm tra checksum cho giá trị số nguyên
- Che giấu (obfuscate) giá trị int, float, string
- So sánh chuỗi đã che giấu
- Xoá file .meta và thư mục rỗng bằng script Python

## Hướng dẫn sử dụng

### 1. MemoryChecksum
```csharp
int value = 123;
int checksum = MemoryChecksum.GenerateChecksum(value);
bool isValid = MemoryChecksum.VerifyChecksum(value, checksum);
```

### 2. MemoryObfuscation
```csharp
int obf = MemoryObfuscation.ObfuscateInt(100);
int restored = MemoryObfuscation.DeobfuscateInt(obf);

float obfF = MemoryObfuscation.ObfuscateFloat(123.45f);
float restoredF = MemoryObfuscation.DeobfuscateFloat(obfF);

string obfStr = MemoryObfuscation.ObfuscateString("Hello123");
string restoredStr = MemoryObfuscation.DeobfuscateString(obfStr);
```

### 3. Xoá file .meta bằng Python
Chạy script sau trong thư mục `_Python`:
```bash
python RemoveAllMeta.py
```

## Cài đặt qua Unity Package Manager
1. Đưa thư mục này lên GitHub.
2. Trong Unity, mở Window > Package Manager > Add package from git URL...
3. Dán đường dẫn:
```
https://github.com/<your-username>/Utils.Cheat.git
```

## License
MIT
