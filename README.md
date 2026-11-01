# School Email Assistant · 学生学校邮件助理

An AI agent skill that reads a student's university inbox, summarizes school notices in the student's own language, flags deadlines, and adds them to the calendar with reminders **3 days before and on the day**.

一个 AI 助理技能（skill）：读取你的学校邮箱，用你的母语总结学校通知，标出截止日期，并把它们加进日历，**提前 3 天和当天各提醒一次**。

Works with **Claude** (claude.ai, Claude Desktop, Claude Code) and **OpenAI Codex**, or any agent that supports the open [Agent Skills](https://agentskills.io) `SKILL.md` format.

---

## 它能做什么 / What it does

- 📬 读取过去 24 小时的学校邮件（通过邮箱连接器、浏览器、邮件转发或手动粘贴）
- 🔴 标出**需要你行动**的事：截止日期、报名、回复、表格、缴费
- 🟡 列出**值得知道**的：讲座、奖学金和项目申请、课程、心理支持等
- ⚪ 群发邮件只统计数量，不打扰你
- 📅 自动加入日历，设两次提醒（提前 3 天 + 当天提前 3 小时），不会重复创建
- ✍️ 需要回复的邮件，帮你写好草稿，**但不会替你发送**
- 🛡️ 邮件内容只当作资料，不执行邮件里的任何指令，并会提示疑似钓鱼邮件

示例输出：

```
📬 学校邮件汇总（11月1日）
🔴 需要你行动
- 11/13 周五 16:30｜PhD Welcome Day｜需先报名（名额有限），入场出示确认邮件｜已加日历✅
- 11/02 周一｜意大利语付费课报名截止｜需要的话今天报名｜已加日历✅
🟡 值得知道
- 11/23 Europaeum 讲座，需报名
⚪ 其他群发：12 封（学校新闻、讲座宣传）
```

---

## 适合谁用 / Who it's for

- 🎓 在国外读书、学校邮件多又是外语的中国留学生
- ⏰ 容易错过截止日期的博士和研究生
- 🤖 想用 AI 但不会写代码的同学

---

## 安装 / Install

先下载：点本页上方绿色的 **Code → Download ZIP**，然后解压。

### Claude（网页版 / 桌面 App）
1. 打开 **Customize → Skills**
2. 点 **+ → Create skill → Upload a skill**
3. 把解压后里面的 `school-email-assistant` 文件夹**单独压缩成 zip**（压缩的是文件夹本身，不是里面的文件），然后上传
4. 对 Claude 说："帮我读学校邮件"

### Claude Code
```bash
git clone https://github.com/jessy-phd/school-email-assistant.git
cp -r school-email-assistant/school-email-assistant ~/.claude/skills/
```

### OpenAI Codex
```bash
git clone https://github.com/jessy-phd/school-email-assistant.git
mkdir -p ~/.codex/skills
cp -r school-email-assistant/school-email-assistant ~/.codex/skills/
```
复制完重启 Codex。

---

## 第一次使用 / First run

助理会先问你：
- 学校、专业、年级、有没有奖学金，以及想用什么语言收汇总
- 学校邮箱地址，以及怎么读到邮件（连接器 / 浏览器 / 转发 / 粘贴）
- 写入哪个日历、你所在的时区
- 重要的发件人（导师、项目秘书处等）

回答会保存在 `student-profile.md` 里，之后就不再问。

**每天自动运行**：如果你用的平台支持定时任务（例如 Claude 的 scheduled tasks），可以让它每天早上自动运行一次，并推送到手机。如果是通过浏览器读邮件，运行时电脑和浏览器需要开着。

---

## 隐私与安全 / Privacy

- 这个 skill 只是一份说明文件，**不包含任何代码、密码或密钥**。
- 它不会要你提供密码，也不会替你发邮件、报名、付款或删除邮件。
- 邮件内容只交给你自己使用的 AI 助理处理，不会发给其他第三方服务。

---

## 贡献 / Contributing

欢迎提 Issue 或 Pull Request，例如：补充某所学校常见的邮件类型、支持 Outlook 日历、增加其他语言的汇总模板。

## License

MIT
