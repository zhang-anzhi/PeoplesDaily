# People's Daily

> 每日自动获取人民日报电子版

## 使用方式

```bash
python main.py
```

文件将保存在 `./data` 目录下。

提供适当的命令行参数可以启用上传至阿里云 OSS 和发送邮件功能，详细帮助请使用 `--help` 参数查看。

### 指定日期

提供 `--date` 参数可以获取指定日期的电子版，格式为 `YYYY-MM-DD`。

```bash
python main.py --date 2021-01-01
```

### 定时任务

您还可以启动定时任务，每天自动获取电子版并发送邮件。

```bash
python main.py --cron-enabled
```

启用定时任务后，邮件参数通过环境变量提供：

| 环境变量 | 说明 |
| --- | --- |
| OSS_ENABLED | 是否启用 OSS 上传 |
| OSS_ACCESS_KEY_ID | OSS Access Key ID |
| OSS_ACCESS_KEY_SECRET | OSS Access Key Secret |
| OSS_ENDPOINT | OSS Endpoint |
| OSS_BUCKET_NAME | OSS Bucket Name |
| OSS_IS_CNAME | OSS 是否使用自定义域名 |
| OSS_REGION | OSS Region |
| EMAIL_ENABLED | 是否启用邮件发送 |
| EMAIL_SMTP_SERVER | SMTP 服务器 |
| EMAIL_SMTP_PORT | SMTP 端口 |
| EMAIL_SMTP_USE_SSL | 是否使用 SSL |
| EMAIL_SMTP_USER | SMTP 用户名 |
| EMAIL_SMTP_PASSWORD | SMTP 密码 |
| EMAIL_SENDER | 发送者 |
| EMAIL_RECIPIENTS | 接收者，多个用 `,` 分隔 |
| EMAIL_WITH_ATTACHMENT | 是否发送附件 |

### Docker Image

定时任务已发布在 `zhanganzhi/peoplesdaily`，数据文件保存在 `/peoplesdaily/data`，邮件参数通过环境变量提供。
