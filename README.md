# Ideal Home Mess - Private WhatsApp Bot (Render.com Deployment)

আইডিয়াল হোম মেসের জন্য সম্পূর্ণ প্রাইভেট, নিজস্ব WhatsApp বট ইঞ্জিন। এটি Render.com-এ ২৪/৭ ফ্রিতে চলবে।

---

## 🌟 সুবিধা
1. **১০০% ফ্রি ও কোনো সীমাবদ্ধতা নেই:** মেটার মতো ২৪ ঘণ্টার মেসেজিং উইন্ডো সীমাবদ্ধতা নেই।
2. **জিরো ব্যান ঝুঁকি:** থার্ড-পার্টি শেয়ার্ড সার্ভার নেই। শুধুমাত্র গুগল শিটে থাকা বর্ডারদের মেসেজ পাঠানো হবে।
3. **ক্লাউড সেশন সিঙ্ক:** Render রিস্টার্ট হলেও গুগল শিট থেকে সেশন রিকভার হবে; বারবার QR স্ক্যান করা লাগবে না।
4. **স্বয়ংক্রিয় নোটিফিকেশন:** বাজারের দায়িত্ব, বাজার অনুমোদন, টাকা জমা রশিদ এবং মাস শেষের ব্যালেন্স রিপোর্ট সরাসরি পৌঁছে যাবে।

---

## 🚀 Render.com-এ ডিপ্লয় করার ৩টি সহজ ধাপ

### ধাপ ১: GitHub-এ আপলোড (Push)
1. আপনার GitHub অ্যাকাউন্টে একটি নতুন Private বা Public রিপোজিটরি তৈরি করুন (যেমন: `idealhome-whatsapp-bot`)।
2. এই `whatsapp-server` ফোল্ডারের কোডগুলো সেখানে পুশ করুন:
   ```bash
   cd whatsapp-server
   git init
   git add .
   git commit -m "feat: ideal home whatsapp bot"
   git branch -M main
   git remote add origin https://github.com/আপনার_ইউজারনেম/idealhome-whatsapp-bot.git
   git push -u origin main
   ```

---

### ধাপ ২: Render.com-এ ডিপ্লয়
1. [Render.com](https://render.com)-এ ফ্রি অ্যাকাউন্ট খুলুন বা লগইন করুন।
2. ড্যাশবোর্ড থেকে **New +** বাটনে ক্লিক করে **Web Service** সিলেক্ট করুন।
3. আপনার GitHub রিপোজিটরি সিলেক্ট করুন।
4. নিচের সেটিংসগুলো দিন:
   - **Name:** `idealhome-bot` (বা যেকোনো নাম)
   - **Language:** `Node`
   - **Branch:** `main`
   - **Build Command:** `npm install`
   - **Start Command:** `node server.js`
   - **Instance Type:** `Free`
5. **Environment Variables** সেকশনে নিচের ভেরিয়েবলটি যুক্ত করুন:
   - **Key:** `GOOGLE_SCRIPT_URL`
   - **Value:** `https://script.google.com/macros/s/AKfycbw6IdTXV95MJUMjTp3ZyDDIHASz9zOIlQ6fgkrxWFru1h5TZKYsHmSgRbc0KV090w9SCg/exec`
6. নিচে **Deploy Web Service** বাটনে ক্লিক করুন।

---

### ধাপ ৩: মেস অ্যাপে লিংক ও QR স্ক্যান
1. ডিপ্লয় শেষ হলে Render আপনাকে একটি লাইভ URL দিবে (যেমন: `https://idealhome-bot.onrender.com`)।
2. মেস ওয়েব অ্যাপে যান > **ম্যানেজার প্যানেল** > **WhatsApp বট কানেক্ট / QR Code** বাটনে ক্লিক করুন।
3. **বট হোস্টিং ও গেটওয়ে সেটিংস** ড্রপডাউনে আপনার Render URL-টি পেস্ট করে **সেটিংস সেভ করুন** বাটনে চাপুন।
4. পর্দায় দেখানো QR কোডটি আপনার মেসের অফিসিয়াল ফোনের WhatsApp থেকে স্ক্যান করুন:
   - WhatsApp ওপেন করুন > **Linked Devices** > **Link a Device**
5. সাথে সাথে স্ট্যাটাস **সংযুক্ত (Live)** হয়ে যাবে এবং বট সম্পূর্ণ প্রস্তুত হয়ে যাবে! 🎉
