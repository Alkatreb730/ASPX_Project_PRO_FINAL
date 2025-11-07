# Ali Smart Global Markets – ASPX 🌍

## وصف مختصر / Short Description
منصة تحليل أسواق عالمية ثنائية اللغة (عربي - English) بنمط داكن، تعرض مؤشرات وأسهم وعملات وسلع وعملات رقمية وبيانات اقتصادية، وتوفر إشارات تداول كل 60 ثانية، توقع لحظي، حاسبات وتحويلات، ومساعد صوتي ذكي.

A bilingual (Arabic-English) dark-themed financial analytics platform. Provides indices, stocks, FX, commodities, crypto, economic data, 60s buy/sell signals, instant forecasts, calculators, converters, and a voice AI assistant.

## محتويات الحزمة / Package Contents
- README.md
- .env.example
- config.json
- docs/ (structure_diagram.png, dashboard_layout.md, ai_extensions.md)
- frontend/ (index.html, app.js, style.css)
- backend/ (server.js, package.json)
- LICENSE.txt

## المتطلبات لتشغيل محلياً / Local Run (Development)
1. نسخ المشروع:
   ```bash
   git clone <repo> || unzip ASPX_Project.zip
   cd ASPX_Project
   ```

2. إعداد المتغيرات (انسخ .env.example إلى .env واملأ المفاتيح):
   ```
   cp .env.example .env
   ```

3. تشغيل الخادم (Node.js backend) والمقدمة (frontend):
   ```bash
   cd backend
   npm install
   npm run dev
   ```
   ثم افتح المتصفح: http://localhost:3000

## ملاحظات مهمة / Notes
- الملفات في هذا ZIP هي scaffold وMVP starter. تحتاج لربط مفاتيح الـAPIs الحقيقية في `.env`.
- التصميم بنمط داكن Dark Theme مع عناصر جاهزة للتمديد.
- جميع الإشارات والتحليلات يجب وضع تحذير قانوني: "معلومات تعليمية/استشارية فقط" قبل تفعيل أي أوامر تداول حقيقية.

## Footer / توقيع
Developed & Designed by Ali Al_Qatrib Qa – ASPX Founder ©2025
التطوير والتصميم: علي القاطرِب QA – مؤسس ASPX ©2025


## Production & Deployment

Use docker-compose for production-ready local deployment:

```bash
docker-compose up --build -d
```

Fill `.env.production` with real API keys before deploying. Frontend will be available at http://localhost:8080 and backend at http://localhost:3000


## ML Service & CI/CD

The project includes a simple ML microservice (backend/ml_service) using FastAPI.
To run ML service locally:

```bash
cd backend/ml_service
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

CI/CD: The workflow `.github/workflows/deploy.yml` builds Docker images and pushes them to your Docker registry.
Set the following GitHub Secrets before using the workflow:
- DOCKER_REGISTRY
- DOCKER_USERNAME
- DOCKER_PASSWORD

Also set API keys as repository secrets or in your deployment platform's config:
- FINNHUB_API_KEY, COINGECKO_API_KEY, TRADINGECONOMICS_KEY, NEWSAPI_KEY, OPENAI_API_KEY, ELEVENLABS_API_KEY
