# Schedule Check

একটি browser-side static website, যা একাধিক training schedule থেকে instructor-দের সময়ের overlap খুঁজে দেখায়। কোনো server বা account লাগে না।

## চালু করা

`index.html` browser-এ খুলুন। `.docx` পড়তে Mammoth.js CDN থেকে load হয়, তাই প্রথমবার Word file import করার সময় internet connection দরকার। CSV import কোনো অতিরিক্ত parser ব্যবহার করে না। Hosting-এর জন্য folder-টি যেকোনো static host-এ প্রকাশ করলেই হবে।

## Import format

- Word: schedule-এ `Date`, `Time`, `Topic`, এবং `Instructor’s Name` শিরোনামের table থাকতে হবে। ফাঁকা date cell আগের তারিখ ধরে নেয়। Instructor ছাড়া row বাদ যায়।
- CSV: header হিসেবে `date,start,end,instructor` আবশ্যক; `topic` এবং `training` ঐচ্ছিক। সময় 24-hour `HH:MM` format-এ দিন।

একই তারিখে ভিন্ন imported schedule-এ একই instructor-এর সময় পরস্পর overlap করলে conflict দেখায়। Break, instructor-হীন session, এবং একই imported file-এর ভেতরের clash বাদ থাকে। Imported data ওই browser-এর local storage-এ থাকে; অন্য device বা browser-এ নিজে থেকে sync হয় না।

`Teacher load` view-তে imported schedule মিলিয়ে প্রতিটি instructor-এর মোট class time (ঘণ্টায়) এবং session count bar chart-এ দেখায়।
