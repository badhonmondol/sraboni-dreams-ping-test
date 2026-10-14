# Sraboni Dreams Ping Service

GitHub Actions দিয়ে Render-এর free tier সার্ভারকে sleep থেকে জাগিয়ে রাখার জন্য এই repo।

## কী করে

প্রতি **৫ মিনিটে** দুটো endpoint এ ping করে:

| Endpoint | কাজ |
|----------|-----|
| `/health` | Server alive রাখে |
| `/api/ping-db` | Database connection alive রাখে |

## কীভাবে কাজ করে

`.github/workflows/ping.yml` ফাইলে একটা scheduled GitHub Action আছে যেটা `curl` দিয়ে server এ request পাঠায়।

```yaml
on:
  schedule:
    - cron: '*/5 * * * *'
```

## Target Server

**https://sraboni-dream.onrender.com**

## Manual Trigger

GitHub → Actions → "Ping Sraboni Dream" → "Run workflow" বাটনে click করলে যেকোনো সময় manually run করা যাবে।
