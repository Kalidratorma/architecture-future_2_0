# Task3 (TechRadar и Roadmap)

## 1. TechRadar

| Quadrant                  | Adopt (использовать)                        | Trial (пробовать)                         | Assess (оценивать)                       | Hold (сдерживать)                      |
|----------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------|----------------------------------------|
| **Languages & Frameworks** | Java, Go, Python                           | Scala (Spark jobs)                        | Rust (streaming)                          | Power Builder                          |
| **Data Management**        | Lakehouse (Delta/Iceberg/Hudi), SQL        | Feature Store (Feast), dbt                | Graph DB (Neo4j)                          | MS SQL Server 2008 (DWH)               |
| **Integration & Messaging**| Kafka/Pulsar, CDC (Debezium)               | gRPC, AsyncAPI                            | NATS                                      | Apache Camel (старый ESB)              |
| **Analytics & BI**         | Power BI, Semantic Layer (Metrics-as-Code) | Superset, Looker                          | Tableau                                   | Кастомные отчёты в Power Builder       |
| **Infra & DevOps**         | Kubernetes, Docker, Terraform              | ArgoCD, dbt test, Great Expectations      | DataOps platforms (Prefect)               | On-prem ESB монолит                    |
| **Security & Governance**  | IAM (RBAC/ABAC), Vault/KMS, Lineage tools  | Data Catalog (Amundsen/DataHub)           | Masking engines (Protegrity)              | Отсутствие централизованной политики   |

---

## 2. Roadmap

### Этап 1 (0–3 месяца): Подготовка
- Создать публичный репозиторий и зафиксировать архитектурные решения.
- Определить домены и назначить ответственных команд.
- Развернуть базовую инфраструктуру: Kubernetes + Lakehouse (в облаке или on-prem).
- Начать каталогизацию данных (DataHub/Amundsen).  
  **Результат:** понятные границы доменов, готовая дата-платформа (MVP).

### Этап 2 (3–6 месяцев): Первые доменные продукты
- Запустить ingestion/CDC для Финтеха и Клиник.
- Настроить Streaming (Kafka/Pulsar).
- Разработать Finance Data Products (транзакции, KPI) и Clinics Data Products (обезличенные агрегаты).
- Настроить Semantic Layer для ключевых метрик.  
  **Результат:** первые витрины в портале; критичные отчёты перестают зависеть от DWH.

### Этап 3 (6–9 месяцев): Расширение
- Подключить Pharma и Med-Electronics домены.
- Реализовать телеметрию оборудования и витрины Pharma.
- Запустить Feature Store для AI/ML (частично).
- Внедрить мониторинг качества данных (Great Expectations).  
  **Результат:** расширенный охват бизнес-направлений, первые AI/ML сценарии.

### Этап 4 (9–12 месяцев): Консолидация
- Финализировать Semantic Layer (все основные метрики и KPI).
- BI-пользователи массово переходят на портал самообслуживания.
- Legacy DWH локализован, остаются только ограниченные отчёты.
- Единая политика доступа, маскирования и аудит.  
  **Результат:** портал самообслуживания как основной инструмент, снижение нагрузки на легаси.

---

## 3. Обоснование изменений

- **Lakehouse + Streaming** — масштабируемость и отказ от узкого места SQL 2008.
- **Data Products по доменам** — независимое развитие, быстрый time-to-market.
- **Semantic Layer** — единый источник правды для KPI, исключает дублирование.
- **Data Governance** — минимизация рисков PHI/PII, прозрачный lineage и доступы.
- **Observability** — предсказуемость и контроль SLA.
- **Legacy Isolation** — постепенный отказ от монолита, минимизация рисков миграции.

---
