# Experssion 
|Experssion|Usage|
|----------|-----|
|/^hello/|ရှေ့ဆုံးတွင်ပါရန်|
|/hello/i|Case Sensitive မဖြစ်ရန်|
|/hello$/|နောက်ဆုံးတွင်ပါရန်|
|/h.llo/|. နေရာတွင်ကြိုက်တဲ့စာလုံးဖြစ်နိုင်|
|/h*llo/|* နေရာတွင် လုံးဝမပါလည်းရ တခုထက်ပါလည်းရ|
|/ha?e?llo/|a or e or nothing|
|/hello\?/|ပါမပါစစ်ရန်|
|/h[ae]llo/|Only a or e|
|/[^h]ello/|hနဲ့စတာဖြစ်လို့မရ|
|/[A-Z]ello/|A to Z ဖြင့်စ၍ရ|
|/[a-z]ello/|a to z ဖြင့်စ၍ရ|
|/[a-zA-z]ello/|A to Z or a to z ဖြင့်စ၍ရ|
|/[0-9]ello/i|0-9ဖြင့်စ၍ရ|
|/[a-zA-z0-9]ello/|A to Z (or) a to z (or) 0 to 9 ဖြင့်စ၍ရ|
|/[h]{2}ello/|h နှစ်ခါပါရန်|
|/[h]{2,5}ello/|h နှစ်ခါ မှ ငါးခါထိ ပါရန်|
|/[h]{2,}ello/|h နှစ်ခါ မှ ငါးခါထိ ပါရန်|
|/([h]e){3}llo/|first letter-h and second letter-e for three times|
|/W/|A-Z a-z 0-9 ဖြစ်၍ရ|
|/W+/|A-Z a-z 0-9 ဖြစ်၍ရ(one or more characters)|
|/\W/|A-Z a-z 0-9 ဖြစ်၍မရ(no word character)|
|/d/|Any Digit|
|/d+/|Any Digit or more|
|/\D/|None Digit|
|/S/|White Space|
|/\S/|No White Space|
|/hell|b/|word boundary|
|/x(?=y)/|X followed by Y|
|/x(?!y)/|X  Not followed by Y|