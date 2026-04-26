# 📮 RE:Set 留言墙

<div align="center">
  <img src="https://img.shields.io/badge/版本-2.0-547443?style=flat-square&logo=github">
  <img src="https://img.shields.io/badge/数据库-Supabase-3b82f6?style=flat-square&logo=supabase">
  <img src="https://img.shields.io/badge/部署-GitHub%20Pages-222222?style=flat-square&logo=githubpages">
  <img src="https://img.shields.io/badge/开源协议-MIT-547443?style=flat-square">
</div>

<p align="center">
  <strong>✨ 一个温暖、复古的在线留言墙 ✨</strong><br>
  便利贴白板墙 · 私信聊天室 · 全球数据互通 · 管理员系统
</p>

<p align="center">
  <a href="#-在线演示">在线演示</a> •
  <a href="#-功能特性">功能特性</a> •
  <a href="#-技术架构">技术架构</a> •
  <a href="#-快速部署">快速部署</a> •
  <a href="#-管理员指南">管理员指南</a>
</p>

---

## 🎨 在线演示

> 🌐 访问地址：`https://scmccamp.github.io/RE-set_-/`

---

## ✨ 功能特性

### 📌 便利贴白板墙
- **纸质质感** - 米黄色便利贴，随机倾斜，还原真实白板体验
- **网格布局** - 自适应卡片排列，美观整洁
- **实时同步** - 所有人看到的留言完全相同，全球数据互通

### 💬 私信聊天系统
- **联系人列表** - 自动保存所有对话过的用户
- **气泡对话框** - 类似微信/iMessage 的聊天体验
- **实时刷新** - 5秒自动轮询，无需手动刷新
- **消息删除** - 可删除自己发送的消息

### 👑 管理员系统
- **隐身入口** - 点击右上角用户头像 → 输入密码进入
- **用户管理** - 修改任意用户昵称、删除用户及其所有数据
- **用户列表** - 查看所有注册用户，支持搜索
- **全局删除** - 管理员可删除任何公开留言和私信

### 🔒 数据安全
- **昵称唯一性** - 每个用户只能设置一次昵称，不可更改
- **私密性** - 私信仅发送者和接收者可见
- **云端存储** - 所有数据存储在 Supabase，永久保存

---

## 🛠️ 技术架构

| 层级 | 技术 | 说明 |
|------|------|------|
| 前端 | HTML5 + CSS3 + JavaScript | 纯原生，无框架依赖 |
| 后端 | Supabase | PostgreSQL 数据库 + REST API |
| 部署 | GitHub Pages | 免费静态托管 |
| 认证 | 管理员密码验证 | 前端验证，简单易用 |

### 数据库结构

```sql
-- 公开留言表
CREATE TABLE public_messages (
  id SERIAL PRIMARY KEY,
  username TEXT NOT NULL,
  content TEXT NOT NULL,
  timestamp BIGINT NOT NULL
);

-- 私信表
CREATE TABLE private_messages (
  id SERIAL PRIMARY KEY,
  "fromUser" TEXT NOT NULL,
  "toUser" TEXT NOT NULL,
  content TEXT NOT NULL,
  timestamp BIGINT NOT NULL
);
