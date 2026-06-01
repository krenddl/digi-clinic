# DigiClinic

Веб-система управления клиникой: запись к врачу, профили пациентов и врачей, чат в реальном времени и Telegram-бот. Разворачивается одной командой через Docker или автоматически через Render.

## Возможности

- Регистрация / авторизация (JWT)
- Запись пациентов к врачам, управление расписанием
- Справочники: врачи, специализации, услуги
- Направления (рефералы) между врачами
- Чат в реальном времени (SignalR)
- Telegram-бот для уведомлений и записи
- Дашборд с аналитикой

## Стек

| Слой | Технология |
|------|------------|
| Бэкенд | ASP.NET Core 8 Web API |
| База данных | PostgreSQL |
| Фронтенд | React 19 + Vite + Tailwind CSS |
| Чат | SignalR |
| Уведомления | Telegram Bot API |
| Инфраструктура | Docker, Render |

## Быстрый старт (локально)

```bash
# API
cd DigiClinicApi/DigiClinicApi
dotnet run

# Клиент
cd digiclinic/digi-clinic-client
npm install
npm run dev
```

- API: `http://localhost:5237/api/health`
- Клиент: `http://localhost:5173`

## Деплой на Render

`render.yaml` в корне репозитория автоматически создаёт три сервиса:

| Сервис | Тип |
|--------|-----|
| `digiclinic-api` | ASP.NET Core API (Docker) |
| `digiclinic-db` | PostgreSQL |
| `digiclinic-client` | React (статика) |

Шаги: Render → New → Blueprint → подключить репозиторий.