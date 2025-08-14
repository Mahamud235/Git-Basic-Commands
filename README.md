# 🚀 Git Bash দিয়ে লোকাল প্রজেক্ট GitHub-এ Push করার ফুল প্রসেস

## 1️⃣ ফাইল বা ফোল্ডার তৈরি (Optional)
```bash
touch "File Name"
touch "File Name.Extension"
```

---

## 2️⃣ প্রজেক্ট ফোল্ডার VS Code-এ ওপেন করতে হবে
- প্রজেক্ট ফোল্ডারে ঢুকে **VS Code** দিয়ে ওপেন করতে হবে।

---

## 3️⃣ Git Bash টার্মিনাল ওপেন করতে হবে
- VS Code থেকে টার্মিনাল ওপেন করতে হবে  
- **Git Bash** আগে থেকেই ইনস্টল & কনফিগার করা থাকতে হবে

---

## 4️⃣ Git Init করতে হবে
```bash
git init
```
> **নোট:**  
> - এই কমান্ড দিতে হবে শুধু তখনই যখন ওই ফোল্ডারে আগে কখনো `git init` করা হয়নি।  
> - একবার `git init` + Push হয়ে গেলে একই ফোল্ডারের জন্য আর এই কমান্ড লাগবে না।

---

## 📂 কেস A — রিমোট Repo-তে আগে থেকেই ফাইল আছে  
(যেমন: README.md, LICENSE ইত্যাদি)

**Step 1 — Remote সেট করতে হবে**
```bash
git remote add origin https://github.com/Mahamud235/Git-Basic-Commands.git
```

**Step 2 — লোকাল Branch main করতে হবে**
```bash
git branch -M main
```

**Step 3 — রিমোট ফাইল আগে টেনে নিতে হবে (Merge না করে Rebase ভালো)**
```bash
git pull origin main --rebase
```

**Step 4 — লোকাল ফাইলগুলো স্টেজ করতে হবে**
```bash
git add .
```

**Step 5 — কমিট করতে হবে**
```bash
git commit -m "V.01"
```

**Step 6 — প্রথমবার Push করতে হবে (Upstream সেট করে)**
```bash
git push -u origin main
```

---

## 📂 কেস B — রিমোট Repo খালি (কোনো ফাইল নেই)

**Step 1 — লোকাল ফাইলগুলো স্টেজ করতে হবে**
```bash
git add .
```

**Step 2 — কমিট করতে হবে**
```bash
git commit -m "V.01"
```

**Step 3 — Remote সেট করতে হবে**
```bash
git remote add origin https://github.com/Mahamud235/Git-Basic-Commands.git
```

**Step 4 — লোকাল Branch main করতে হবে**
```bash
git branch -M main
```

**Step 5 — প্রথমবার Push করতে হবে (Upstream সেট করে)**
```bash
git push -u origin main
```

---

## 🔄 পরেরবার শুধু ফাইল চেঞ্জ করলে  
(Upstream একবার সেট হয়ে গেলে)

```bash
git add .
git commit -m "Change details here"
git push
```

---

## 💡 কিছু দরকারি নোট
- `.gitignore` দিয়ে অপ্রয়োজনীয় ফাইল বাদ দিতে হবে  
- `git add .` = সব নতুন বা পরিবর্তিত ফাইল স্টেজ করা  
- `git commit` = পরিবর্তন লোকাল history-তে সেভ করা  
- প্রথমবার Push-এ `-u origin main` দরকার, পরেরবার শুধু `git push` দিলেই হবে
