# מתחילים מ-image בסיס שיש בו Python 3.11
FROM python:3.11-slim
#יוצר תיקיית app בתוך ה-container ועובד בה
WORKDIR /app
#מעתיקים לתוך התיקיה הנוכחית את רשימת הספריות שהקוד צריך
COPY requirements.txt .
#מתקינים את הספריות מהרשימה
RUN pip install --no-cache-dir --trusted-host pypi.org --trusted-host files.pythonhosted.org -r requirements.txt
# מעתיקים את הקוד - אחרי הספריות, כדי שה-cache י
COPY app.py .
# מתעד שהשרת מאזין בפורט 8000 (לא פותח אותו)
EXPOSE 8000
# הפקודה שרצה כשה-container עולה: מפעילה את השרת
CMD ["python", "app.py"]