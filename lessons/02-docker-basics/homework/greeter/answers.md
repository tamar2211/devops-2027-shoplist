# תשובות - שיעור 2
 
 1. docker build -t greeter:v1 lessons/02-docker-basics/homework/greeter
 2. docker run   -d -p 9000:8000 --name greeter greeter:v1
 3. docker run -d -p 9000:8000 --name greeter -e GREETING=Shalom greeter:v1
 4. {"message":"Shalom, Rivka!"}
 5.  [1/5] FROM python:3.11-slim      ← cached
    [2/5] WORKDIR /app               ← cached
    [3/5] COPY requirements.txt .    ← cached
    [4/5] RUN pip install ...        ← cached
    [5/5] COPY app.py .              ← נבנה מחדש
    כל השינויים מתרחשים רק בשלב 5 ולכן כל מה שלפניו לא השתנה ונלקח מהcache לכן התקנת הספריות היא לפני העתקת הקוד כדי ששינוי בקוד לא יתקין שוב את הספריות.

    