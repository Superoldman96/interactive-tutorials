Regular Expressions (कभी-कभी संक्षिप्त में regexp, regex, या re कहा जाता है) एक उपकरण है जो टेक्स्ट में पैटर्न मिलाने के लिए उपयोग किया जाता है। Python में, हमारे पास re मॉड्यूल है। नियमित अभिव्यक्तियों के अनुप्रयोग व्यापक हैं, लेकिन वे काफी जटिल होते हैं, इसलिए जब किसी विशेष कार्य के लिए regex का उपयोग करने पर विचार करें, तो विकल्पों के बारे में सोचें, और regexes का सहारा अंतिम उपाय के रूप में लें।

एक उदाहरण regex है `r"^(From|To|Cc).*?python-list@python.org"` अब एक स्पष्टीकरण:
कैरेट `^` लाइन की शुरुआत में टेक्स्ट का मिलान करता है। निम्नलिखित समूह, जिसमें `(From|To|Cc)` होता है, का अर्थ है कि लाइन को उन शब्दों में से एक से शुरू होना पड़ेगा जो पाइप `|` द्वारा विभाजित किए गए हैं। इसे OR ऑपरेटर कहा जाता है, और regex का मिलान तब होगा जब लाइन समूह में से किसी भी शब्द से शुरू होती है। `.*?` का मतलब है कि अन-ग्रीडिली किसी भी संख्या के वर्णों का मिलान करें, नई पंक्ति `\n` वर्ण को छोड़कर। अन-ग्रीडी हिस्सा जितना कम दोहराव संभव हो उतना कम मिलान करने का अर्थ है। `.` वर्ण का अर्थ है कोई भी गैर-नई-पंक्ति वर्ण, `*` का मतलब है 0 या अधिक बार दोहराना, और `?` वर्ण इसे अन-ग्रीडी बनाता है।

तो, निम्न पंक्तियाँ उस regex द्वारा मेल खाएंगी:
`From: python-list@python.org`
`To: !asp]<,.      python-list@python.org`

re सिंटैक्स के लिए एक पूर्ण संदर्भ [python docs](http://docs.python.org/library/re.html#regular-expression-syntax "RE syntax) पर उपलब्ध है।

एक "उचित" ईमेल-मिलान regex के उदाहरण के रूप में (जैसा कि अभ्यास में एक है), [यह देखें](http://www.ex-parrot.com/pdw/Mail-RFC822-Address.html)