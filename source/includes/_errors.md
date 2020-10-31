# Errors

API'ın bu versiyonu standart HTTP status kodları ve error kodlarını dönmektedir. Error kodlarının açıklamaları aşağıda verilmiştir. API HTTP status kodları ve error kodlarına ek olarak özelleştirilmiş başka bir status kodu/error kodu dönmez. 


Error Code | Meaning
---------- | -------
400 | Bad Request -- Yapmaya çalıştığınız istek geçersiz. URL'i, header'larınızı ve varsa parametrelerinizi kontrol edin.
401 | Unauthorized -- Muhtemelen API key'iniz geçersiz.
403 | Forbidden -- Muhtemelen API key'iniz geçersiz.
404 | Not Found -- Muhtemelen URL'iniz geçersiz. .
405 | Method Not Allowed -- Yapmaya çalıştığınız istek geçersiz. URL'inizi kontrol edin.
410 | Gone -- Sunucu tarafında olmayan bir metoda istek yapıyorsunuz. Bu hatayı alıyorsanız kendi tarafınızdaki kontrolleri tamamladıktan sonra sunucu yöneticisi ile iletişime geçin.
500 | Internal Server Error -- Sunucu tarafında bir sorun yaşanıyor. Kısa bir süre sonra tekrar istek yapmayı deneyin. 500 hatası tekrarlanıyorsa, sunucu yöneticisi ile iletişime geçin.
