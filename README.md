## GitLab Branching & Merge Request

এই ডকুমেন্টে GitLab-এ নতুন Project তৈরি করা থেকে শুরু করে Branch তৈরি, কাজ করা এবং Merge Request-এর মাধ্যমে Main Branch-এ Merge করা পর্যন্ত পুরো প্রক্রিয়া ধাপে ধাপে দেখানো হয়েছে।

---

## ধাপ ১: নতুন Project তৈরি করা

1. **Projects** এ ক্লিক করুন
2. **New project** এ ক্লিক করুন
3. **Create blank project** এ ক্লিক করুন
4. Project name দিন: `daw`
5. **Create project** এ ক্লিক করুন

---

## ধাপ ২: প্রথম File তৈরি করা (Main Branch-এ)

1. **New file** এ ক্লিক করুন
2. File name দিন: `index.html`
3. নিচের Code টি লিখুন:

```html
<h2>Branches & Merging</h2>
```

4. **Commit changes** এ ক্লিক করুন
5. Commit message দিন: `Group leader`

---

## ধাপ ৩: Project Clone করা

Local machine-এ Project টি Clone করার জন্য Terminal-এ নিচের Command গুলো চালান:

```bash
git clone git@gitlab.com:wasuit-group/merge.git
```

```bash
cd merge
code .
```

এতে করে VS Code-এ Project Folder টি খুলে যাবে।

---

## ধাপ ৪: নতুন Branch তৈরি করা

VS Code-এর Terminal Open করে নতুন Branch তৈরি করুন:

```bash
git checkout -b css
```

কোন Branch-এ আছেন তা যাচাই করতে:

```bash
git branch
```

---

## ধাপ ৫: নতুন Branch-এ কাজ করা

`style.css` নামে একটি নতুন File তৈরি করুন এবং নিচের Code টি লিখুন:

```css
* {
    margin: 0;
    padding: 0;
}
```

---

## ধাপ ৬: পরিবর্তন Commit ও Push করা

Terminal-এ নিচের Command গুলো একে একে চালান:

```bash
git add .
git commit -m 'style file added'
git push -u origin css
```

এতে `css` Branch টি Remote Repository-তে Push হয়ে যাবে।

---

## ধাপ ৭: Merge Request তৈরি করা

1. GitLab-এ যান এবং **Create merge request** এ ক্লিক করুন
2. আবার **Create merge request** এ ক্লিক করুন
3. তারপর **Merge** বাটনে ক্লিক করুন

![Merge Request](https://imgur.com/j4RfB2j.png)

Merge হয়ে গেলে **main** Branch-এ গিয়ে দেখুন `style.css` File টি যোগ হয়েছে কিনা।

---

## ধাপ ৮: Local-এ Main Branch Update করা

VS Code-এর Terminal-এ গিয়ে নিচের Command গুলো চালান:

```bash
git branch
git switch main
git merge css
```

এতে করে Local `main` Branch-এও `css` Branch-এর সব পরিবর্তন যুক্ত হয়ে যাবে।

---
