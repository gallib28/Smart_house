מפת דרכים מפורטת לפרויקט הבית החכם

מטרה

לפתח מערכת חכמה המאפשרת שליטה על מתגים חכמים (לאורות ולדוד מים) וצפייה בצילומי מצלמות IP דרך אפליקציה מותאמת אישית. המערכת תתבסס על שרת Raspberry Pi (RPI) ותספק שליטה מלאה על המכשירים.

שלב 1: הגדרת תשתית החומרה

משימות:

	1.	רכישת ציוד:
	•	מתגים חכמים תואמי Wi-Fi/RTSP (למשל: Shelly/Tuya/Sonoff).
	•	מצלמת IP (למשל: TP-Link Tapo C200 או דגם אחר תואם RTSP).
	•	Raspberry Pi (גרסה 4 מומלצת, עם לפחות 4GB RAM).
	•	ספק כוח יציב ל-RPI.
	•	כרטיס microSD בנפח 32GB ומעלה.
	2.	חיבור המתגים והמצלמה:
	•	חבר את המתגים ואת המצלמה לרשת ה-Wi-Fi.
	•	בדוק שניתן לשלוט בהם באמצעות האפליקציה היצרנית (כשלב ראשוני).
	3.	הגדרת RPI:
	•	התקן מערכת הפעלה Raspbian Lite (ללא GUI).
	•	הגדר חיבור רשת (Wi-Fi או כבל Ethernet).
	•	ודא שה-RPI מוגדר עם IP סטטי.

יכולות טכנולוגיות נדרשות:

	•	ידע בסיסי ברשתות.
	•	התקנה ראשונית של מערכת הפעלה ל-RPI.

שלב 2: הגדרת שרת על ה-RPI

משימות:

	1.	התקנת תוכנות נדרשות:
	•	התקן שרת MQTT (למשל: Mosquitto) לשליטה במתגים.
	•	התקן שרת Nginx (או Flask) לטובת ה-API והאפליקציה.
	•	התקן את ספריית MotionEyeOS או ZoneMinder לניהול המצלמות.
	2.	אינטגרציה עם המתגים:
	•	חבר את המתגים לשרת MQTT.
	•	כתוב סקריפט Python לשליחת פקודות MQTT למתגים (לדוגמה: הדלקת/כיבוי אור).
	3.	אינטגרציה עם המצלמה:
	•	משוך את זרם הווידאו (RTSP) מהמצלמה.
	•	בדוק את השידור בעזרת VLC או ffmpeg.

יכולות טכנולוגיות נדרשות:

	•	ידע בסיסי בפרוטוקול MQTT.
	•	ניסיון בסיסי עם Python.
	•	יכולת לעבוד עם פרוטוקולי וידאו (RTSP).

שלב 3: פיתוח צד שרת (Backend)

משימות:

	1.	בניית API לשליטה על המתגים והמצלמות:
	•	השתמש ב-Flask או FastAPI ליצירת API.
	•	כתוב פונקציות:
	•	להדלקת/כיבוי מתגים (דרך MQTT).
	•	להצגת שידור וידאו מהמצלמה (RTSP).
	2.	אינטגרציה עם בסיס נתונים:
	•	התקן MySQL או SQLite על ה-RPI.
	•	צור טבלה לניהול הגדרות (לדוגמה: מצב מתגים, זמני הפעלה).
	3.	אבטחת API:
	•	הוסף אימות JWT לטובת אבטחת הגישה.

יכולות טכנולוגיות נדרשות:

	•	תכנות צד שרת ב-Python.
	•	עבודה עם בסיסי נתונים (SQL).
	•	אבטחת API באמצעות JWT.

שלב 4: פיתוח צד לקוח (Frontend)

משימות:

	1.	עיצוב האפליקציה:
	•	עיצוב דף כניסה (Login).
	•	עיצוב דף ראשי להצגת מצב מתגים ותצוגת מצלמות.
	2.	כתיבת קוד:
	•	השתמש ב-HTML, CSS, JavaScript.
	•	השתמש ב-Framework כמו React או Vue.js לממשק מתקדם.
	3.	אינטגרציה עם ה-API:
	•	שליחת בקשות API לשליטה במתגים.
	•	משיכת נתונים עבור תצוגת מצלמות.

יכולות טכנולוגיות נדרשות:

	•	פיתוח צד לקוח עם React/Vue.js.
	•	אינטגרציה של Frontend עם API.

שלב 5: בדיקות ושיפורים

משימות:

	1.	בדיקות מערכת:
	•	בדוק שליטה מלאה על המתגים דרך האפליקציה.
	•	ודא שהווידאו מהמצלמות זורם בצורה חלקה.
	2.	תיקוני באגים ושיפורים:
	•	פתר בעיות חיבור או עיכוב.
	•	שפר את ביצועי המערכת (לדוגמה: שמירת cache לזרם וידאו).
	3.	הוספת תכונות:
	•	הוספת תזמונים אוטומטיים למתגים.
	•	שליחת התראות (Notifications) לטלפון.

יכולות טכנולוגיות נדרשות:

	•	בדיקות תוכנה (QA).
	•	יכולת לזהות ולפתור בעיות ביצועים.

שלב 6: פריסה ושימוש יומיומי

משימות:

	1.	העברת המערכת לסביבת ייצור:
	•	ודא שה-RPI מוגן (גישה עם SSH בלבד).
	•	התקן UPS למניעת הפסקות חשמל.
	2.	שימוש ותחזוקה:
	•	השתמש באפליקציה לניהול הבית.
	•	עדכן את המערכת בהתאם לצרכים המשתנים.

סיכום: טכנולוגיות וכלים נדרשים

	1.	תוכנות:
	•	Raspberry Pi OS (Lite).
	•	Flask/FastAPI.
	•	MySQL.
	•	MotionEyeOS או ZoneMinder.
	•	MQTT (Mosquitto).
	2.	שפות תכנות:
	•	Python (ל-Backend).
	•	JavaScript (ל-Frontend).
	3.	חומרה:
	•	Raspberry Pi.
	•	מתגים חכמים.
	•	מצלמת IP.

אם תצטרך הסבר על שלב מסוים או דוגמה לקוד, אני כאן לעזור!
