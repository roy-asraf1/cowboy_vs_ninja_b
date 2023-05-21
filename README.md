# cowboy_vs_ninja_a

בתרגיל זה ניצור סימולציה של קרב בין נינגות ובוקרים

# חלק 1 Point

תחילה, נכתוב מחלקה שתעזור לנו לשמור מיקום על לוח המשחק. המיקום נתון כשתי קורדינאטות מסוג double ששומרות
את מיקום היחידה לאורך הצירים x ו - y בהתאם.
על ממשק המחלקה לתמוך בפעולות הבאות:

קונסטרקטור מקבל את שתי הקואורדינאטות –

מרחק distance
מקבלת נקודה ומחשבת את המרחק בין שתי הנקודות –

הדפסה print
מדפיסה את שתי הקואורדינטות בין סוגריים. -

לזוז ל moveTowards
מקבלת נקודת מקור, נקודת יעד ומרחק. הפונקציה מחזירה את הנקודה הקרובה ביותר לנקודת היעד, –
שנמצאת כל היותר במרחק הנתון מנקודת המקור

# חלק 2 Character

מחלקה זו מציינת דמות. לדמות יש מיקום )מסוג Point (, נקודות פגיעה )מיוצג ע"י מספר שלם( ושם שמיוצג ע"י מחרוזת
תווים.
פונקציות המוגדרות על דמות:

האם חייisAlive()
מחזיר ערך בוליאני האם הדמות בחיים )כלומר יש לה יותר מאפס נקודות פגיעה( – –

מרחק distance
מקבל פוינטר לדמות אחרת ומחזיר את המרחק בין הדמויות ) – – double .)

 פגע hit
מקבל מספר שלם. מחסיר את כמות נקודות הפגיעה המתאים מהדמות. לא מחזיר דבר. –

שם getName()
מחזיר את שם הדמות. -

מיקום getLocation()
מחזיר את מיקום הדמות. -

הדפסה print()
מדפיס את שם הדמות, את מספר נקודות הפגיעה שלה, ואת הנקודה בה הדמות נמצאת. אם הדמות מתה מספר - -
נקודות הפגיעה לא יודפס, ושם הדמות יופיע בסוגריים. לפני השם תופיע אות שמציינת את סוג הדמות: N לנינג'ה ו - C
לבוקר.

עבור בוקרים מוגדר גם הפרמטר "כמות כדורים" )מספר שלם( בוקר תמיד נוצר עם שישה כדורים ו 110 נקודות פגיעה. -
הפונקציות הבאות מוגדרות עבור בוקרים בלבד:

לירות shoot 
מקבל מצביע לאוייב. אם הבוקר לא מת ונשארו לו כדורים, הבוקר יורה באויב, מחסיר מהאויב 10 נקודות פגיעה –
ומאבד כדור אחד. אחרת, לא ייגרם לאויב כל נזק.

בדיקת מחסנית hasboolets()
מחזיר – Boolean שמציין האם נשארו כדורים באקדח של הבוקר.

טעינה מחדש reload()
טוען את האקדח בשישה כדורים חדשים.

עבור נינג'ות מוגדר הפרמטר מהירות )מספר שלם(
הפונקציות הבאותת מוגדרות עבור נינג'ות בלבד:

תזוזה move 
מקבלת מצביע לאוייב ומתקדמת לעבר האוייב. הנינג'ה מתקדמת מרחק השווה למהירות שלה. –

שיסוף slash()
– – מקבלת מצביע לאוייב. אם הנינג'ה בחיים והאוייב במרחק של פחות ממטר אחד הנינג'ה תגרום לאוייב נזק של 40
נקודות פגיעה. אחרת, לא ייגרם לאוייב כל נזק.

יש שלושה סוגים של נינג'ות:

YoungNinja
נעות במהירות 14 . נוצרות עם 100 נקודות פגיעה. –

TrainedNinja
נעות במהירות 12 . נוצרות עם 120 נקודות פגיעה. –

OldNinja
נעות במהירות 8. נוצרות עם 150 נקודות פגיעה.

# חלק 3 team

מחלקה זו היא קבוצה של עד עשרה לוחמים, כאשר לוחם יכול להיות נינג'ה או בוקר. לכל קבוצה מוגדר מנהיג שהוא אחד
הלוחמים.
כאשר קבוצה נוצרת, היא מקבלת מצביע למנהיג.
פונקציות המוגדרות לגבי קבוצה:

הוספה add() 
מקבלת מצביע לבוקר או נינג'ה, ומוסיפה אותו לקבוצה. –

תקיפה attack()
מקבלת מצביע לקבוצה אויבת. תקיפת הקבוצה האויבת תיעשה בצורה הבאה: –
תחילה יש לבדוק האם מנהיג הקבוצה התוקפת בחיים. אחרת יש לבחור מנהיג חדש, שהוא הדמות החיה הקרובה – –
ביותר )מבחינת מיקום( למנהיג המת.
אחר כך הקבוצה תיבחר קורבן מתוך קבוצת האויבים הקורבן הוא חבר קבוצת האויבים החי שעומד קרוב ביותר – – -
למנהיג הקבוצה התוקפת.
כל החברים החיים של הקבוצה התוקפת יתקפו את הקורבן הנבחר. בוקרים שיש להם כדורים באקדח יירו בקורבן,
ובוקרים שאין להם כדורים יטענו את הנשק שלהם. נינג'ות שנמצאות במרחק פחות ממטר אחד מהקורבן ישספו את
הקורבן, ונינג'ות שנמצאות רחוק יותר יתקדמו לעבר הקורבן. בכל שלב, אם הקורבן מת ייבחר קורבן חדש )שיהיה,
שוב, דמות האויב החיה הקרובה ביותר למנהיג הקבוצה התוקפת.
אם אין חברים חיים בקבוצה התוקפת או בקבוצת האויב התקיפה תסתיים. –

האם חיי stillAlive()
מחזירה מספר שלם כמות חברי הקבוצה שנותרו בחיים. – –

הדפסה print()
עוברת על כל הדמויות בקבוצה ומדפיסה את פרטיהן. –

דיסטרקטור משחרר את הזכרון שהוקצה לכל הדמויות החברות בקבוצה. –


מעבר על כל חברי הקבוצה (לצורך תקיפה, הדפסה, או השוואה) יתבצע תמיד בסדר הבא: קודם כל מעבר על כל הבוקרים,
ואחר כך מעבר על כל הנינג'ות. בתוך כל קבוצה המעבר יתבצע על פי סדר ההוספה של הדמויות. מטרת הדרישה לפצל בין - -
בוקרים לנינג'ות בחלק זה היא להקל עליכם. אם אתם מוצאים שהדרישה מסבכת את המימוש חשבו על מימוש אחר. –
כאשר מחפשים את הדמות הקרובה ביותר, ושתי דמויות נמצאות במרחק זהה, תיבחר הדמות הראשונה שנבדקה ביניהן.

# team2 

זהה לteam אך המעבר על הדמויות יהיה לפי סדר ההוספה ללא אבחנה של בוקרים או נינגות

# SmartTeam

זהה לteam המעבר על הדמויות יהיה לפי בחירתכם לפי איזה סדר שתראו לנכון לממש
מותר ורצוי בשלב זה "לתשאל" את הקבוצה השניה על מיקומי הכוחות והסטאטוס שלהם כמו גם להתחשב במצב הקבוצה התוקפת כדי למקסם נזק. 
כאשר מטלה זו תיבדק במעבדה סטודנטים עם אלגוריתם חכם, יצירתי, יעיל ואפקטיבי יזכו בנקודות בונוס 
(אי אפשר לעבור את ה10 מקסימום ועדין ניתן לקבל 10 עם אלגוריתם פשוט אבל אלגוריתם טוב יכפה על טעויות במקומות אחרים) 



**חלק ב**: יש לכתוב: 

*מימוש מלא למטלה כדי שהטסט יעבור.
  
כיתבו את כל הקבצים הדרושים כך שהפקודות הבאות יעבדו ללא שגיאות:

<div dir='ltr'>

	bash grade

</div>

מומלץ גם להריץ:

<div dir='ltr'>

    make tidy
    make valgrind

</div>

אין לשנות קבצים קיימים אלא רק להוסיף קבצים חדשים.

בהצלחה
