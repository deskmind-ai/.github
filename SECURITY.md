# Security · 安全

Please **do not** open a public issue for a security problem. Use GitHub's private vulnerability reporting instead:
open the **Security** tab of the affected repository and choose **Report a vulnerability**. If you can't use GitHub, email
security@deskmind.dev. We aim to acknowledge reports within 7 days.

安全问题请**不要**公开提 issue：在对应仓库的 **Security** 页点「Report a vulnerability」私下报告，无法使用 GitHub 时也可发邮件到 security@deskmind.dev。我们争取 7 天内回复。

Things we especially care about · 我们尤其关注：
- anything that could send screen contents or user data off the machine unexpectedly
  任何可能意外把屏幕内容或用户数据发出本机的问题；
- the desktop driver (Hands) acting outside the requested task or sandbox
  桌面驱动（Hands）越出任务或沙箱范围执行操作；
- secrets or personal data present in released files
  已发布文件中出现密钥或个人数据。
