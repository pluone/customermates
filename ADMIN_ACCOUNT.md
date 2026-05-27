# 预置 Admin 账号

此项目包含一个预置的 admin 账号，用于开发和测试目的。

## 登录凭证

- **邮箱**: `admin@customermates.local`
- **密码**: `admin`

## 账号详情

| 属性 | 值 |
|------|-----|
| User ID | `otMY3pkuz5OD6Yj5wVxfxsMW` |
| Account ID | `5iVWQJGjB89KWXeoZlvMlWv9` |
| 邮箱验证 | ✓ 已验证 |
| 公司 | 无（null） |

## 使用方式

### 1. 运行数据库迁移和种子数据

```bash
# 重置数据库并执行种子数据
yarn db:reset

# 或只执行种子数据（保留现有数据）
yarn prisma db seed
```

### 2. 登录到应用

1. 访问应用的登录页面
2. 输入邮箱：`admin@customermates.local`
3. 输入密码：`admin`
4. 点击登录

## 文件位置

admin 账号的数据存储在以下种子文件中：

- `prisma/seeds/authuser.json` - 用户基本信息
- `prisma/seeds/authaccount.json` - 认证账户信息（包括密码哈希）

## 密码哈希信息

密码使用 PBKDF2 加密算法存储，格式为：`salt:hash`

- **算法**: PBKDF2-SHA256
- **迭代次数**: 10,000
- **盐长度**: 16 字节
- **哈希长度**: 32 字节

## 安全提示

⚠️ **重要**: 这个预置的 admin 账号仅用于开发和测试环境。

- ❌ 不要在生产环境中使用
- ❌ 不要将这个凭证用于真实数据
- ✓ 在生产环境中应该创建强密码的管理员账号
- ✓ 确保定期更改密码

## 修改 Admin 账号

如果需要修改 admin 账号的信息（如邮箱或密码），请编辑对应的种子文件，然后重新运行种子数据。
