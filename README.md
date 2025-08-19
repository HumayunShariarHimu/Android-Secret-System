# USSD-DEEP-LINK
# অ্যান্ড্রয়েড USSD, Hyperlink ও Deep Linking গাইড

এই ফাইলে সব তথ্য একত্রে দেওয়া হলো। এখানে আছে:  
- USSD কোড ব্যবহার  
- Hyperlink এবং Deep Linking  
- URL Encode (#, *) ব্যবহার  
- Secret / Advanced কৌশল এবং Root পদ্ধতি  
- HTML ডেমো ওয়েবপেজ  
- নিরাপত্তা সীমাবদ্ধতা এবং নোটস

USSD বা ফোন কোড সরাসরি চালাতে Android সিস্টেমে APK ছাড়া সম্ভব নয়। তবে ওয়েব, PWA বা Deep Link ব্যবহার করে **Dialer প্রি-fill** করা সম্ভব। সাধারণ নিয়ম হলো `tel:` URI ব্যবহার করা এবং `#` কে `%23` encode করা।  

উদাহরণ:  
<a href="tel:*123%23">ব্যালেন্স চেক (*123#)</a>  
<a href="tel:*247%23">বিকাশ মেনু (*247#)</a>  
<a href="tel:*121*1%23">গ্রামীনফোন অফার (*121*1#)</a>  
<a href="intent://*123%23/#Intent;scheme=tel;end">Deep Link দিয়ে চালাও</a>  
<a href="intent://*123%23/#Intent;scheme=tel;end">Deep Link দিয়ে চালাও</a>  

Dialer pre-fill হবে, ইউজারকে কল দিতে হবে। APK ছাড়া অটো execution সম্ভব নয়।  

URL Encoding  
# → %23  
* → %2A (optional)  
সব ব্রাউজার এবং Android ভার্সনে কাজ করতে URL Encode ব্যবহার করা আবশ্যক।  

Secret / Advanced Tips  
Rooted Android → service call phone দিয়ে USSD অটো রান সম্ভব:  
su -c "service call phone 1 s16 '*123#'"  

Normal মোবাইলে শুধুমাত্র pre-fill করা সম্ভব। Call করতে ইউজারকে চাপতে হবে।  

সারসংক্ষেপ  
tel: URI দিয়ে ফোন/USSD কোড pre-fill করা যায়।  
# সবসময় %23 encode করতে হবে।  
Deep Linking / Intent URL দিয়ে Dialer বা অ্যাপ trigger করা যায়।  
অটো কল/USSD execution APK বা Root ছাড়া সম্ভব নয়।  
Web/PWA থেকে শুধুমাত্র pre-fill করা সম্ভব।  
Rooted ডিভাইসে service call phone দিয়ে অটো রান করা সম্ভব।
