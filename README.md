import requests

# اطلاعات ربات تلگرام
BOT_TOKEN = 'توکن_ربات_شما'  # توکن رباتی که از BotFather گرفتید
CHAT_ID = '@hey_torment'  # آیدی تلگرام شما
MESSAGE = 'سلام اکانت تلگرام می‌خوام'  # پیامی که می‌خواهید ارسال شود

# تابع برای ارسال پیام
def send_telegram_message():
    url = f"https://api.telegram.org/bot{BOT_TOKEN}/sendMessage"
    payload = {
        'chat_id': CHAT_ID,
        'text': MESSAGE
    }
    response = requests.post(url, json=payload)
    if response.status_code == 200:
        print("پیام با موفقیت ارسال شد!")
    else:
        print(f"خطا در ارسال پیام: {response.text}")

# شبیه‌سازی کلیک روی لینک
def on_link_click():
    print("لینک کلیک شد!")
    send_telegram_message()

# فرض می‌کنیم کاربر روی لینک کلیک کرده است
on_link_click()
