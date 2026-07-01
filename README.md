<div align="center">

# Андрей Полуянов

## DevOps / SRE инженер

<br>

<p align="center">
  <a href="https://t.me/poluyanovv"><img src="https://img.shields.io/badge/Telegram-@poluyanovv-30363d?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"></a>
  <a href="mailto:andrey@poluyanov.net"><img src="https://img.shields.io/badge/Email-andrey@poluyanov.net-30363d?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
</p>

<p align="center">
  <a href="https://poluyanov.net"><img src="https://img.shields.io/badge/Website-poluyanov.net-30363d?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website"></a>
  <a href="https://habr.com/ru/users/Andrey172/"><img src="https://img.shields.io/badge/Habr-Andrey172-30363d?style=for-the-badge&logo=habr&logoColor=white" alt="Habr"></a>
</p>

</div>

---

## Обо мне

Начинающий DevOps / SRE инженер.

Не ограничиваюсь теорией: учусь через практику и строю полноценные инфраструктурные проекты.

Пишу статьи на темы, связанные с DevOps. В процессе работы над ними глубоко разбираюсь в конкретных вопросах, а затем в интересной форме делюсь полученными знаниями.

Люблю работать в команде: обсуждать идеи, предлагать решения и вместе искать лучший подход. Легко нахожу общий язык в коллективе и ценю возможность развиваться в сильной инженерной среде.

---

## Навыки

<div align="center">

![Linux](https://img.shields.io/badge/Linux-30363d?style=for-the-badge&logo=linux&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-30363d?style=for-the-badge&logo=gnubash&logoColor=white)
![Git](https://img.shields.io/badge/Git-30363d?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-30363d?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-30363d?style=for-the-badge&logo=kubernetes&logoColor=white)
![Helm](https://img.shields.io/badge/Helm-30363d?style=for-the-badge&logo=helm&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-30363d?style=for-the-badge&logo=ansible&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-30363d?style=for-the-badge&logo=terraform&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab_CI-30363d?style=for-the-badge&logo=gitlab&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-30363d?style=for-the-badge&logo=githubactions&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-30363d?style=for-the-badge&logo=prometheus&logoColor=white)
![Alertmanager](https://img.shields.io/badge/Alertmanager-30363d?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-30363d?style=for-the-badge&logo=grafana&logoColor=white)
![Loki](https://img.shields.io/badge/Loki-30363d?style=for-the-badge&logo=grafana&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-30363d?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-30363d?style=for-the-badge&logo=redis&logoColor=white)
![Python](https://img.shields.io/badge/Python-30363d?style=for-the-badge&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-30363d?style=for-the-badge&logo=go&logoColor=white)

</div>

<br>

## Ключевой проект

### [Internal AI Knowledge Assistant](https://github.com/Andrey787878/ai-knowledge-assistant)

DevOps/SRE-кейс внутреннего AI-ассистента знаний компании.

Цель проекта - создать единую централизованную систему знаний, которая использует Wiki.js как базу знаний и предоставляет быстрые, структурированные ответы на вопросы сотрудников с помощью локальной LLM-модели.

Стек: Wiki.js, n8n, PostgreSQL, Redis и Ollama.

#### Что реализовано:

**Инфраструктура**

- `2` воспроизводимых контура деплоя: VM-контур и Kubernetes-контур.
- `1` эксплуатационный этап, который добавляет к Этапу B CI/CD и observability.
- `1` отдельная VM для runner GitHub Actions.
- `4` VM в Этапе A: `wiki`, `db`, `n8n`, `ollama`.
- `1` публичная VM в Этапе A: только `wiki` имеет публичный IP и выполняет роль edge + bastion.
- `1` публичная VM в Этапе B: только VM кластера `k3s` имеет публичный IP и служит бастионом для runner.
- `7` Helmfile-слоев в Этапе B: `platform`, `observability`, `postgres`, `redis`, `wiki`, `ollama`, `n8n`.
- `2` собственных Helm-чарта: `n8n` и `ollama`.
- Резервное копирование и восстановление `PostgreSQL` реализовано на обоих этапах, с проверкой целостности и явным подтверждением восстановления.
- `2` документированных контура с отдельными runbook'ами, эксплуатационной
  документацией и архитектурными схемами.

**CI/CD**

- `1` GitHub Actions CI workflow с `5` независимыми job: repository sanity,
  secret scan, Terraform, Helm, Ansible syntax.
- `2` GitHub Actions CD workflow для kubernetes-контура: `cd-k3s-auto` и
  `cd-k3s-manual`.
- `1` CI quality gate перед автоматической выкладкой в production и перед
  ручной выкладкой выбранного `ref`.
- `5` n8n workflow: `agent_query_main`, `memory_read`, `memory_write`, `agent_chat_ui`, `agent_smoke_e2e`.

**Observability**

- `3` кастомных Grafana дашборда в observability-слое: `Observability Overview`, `n8n Runtime`, `Public Endpoints / Edge`.
- `6` групп алерт-правил: внутренняя доступность, внешний пользовательский путь, зависимости, runtime `n8n`, self-monitoring, ingress HTTP.
- `2` публичные синтетические HTTPS-пробы.
- `5` внутренних blackbox-проверок для `n8n`, `wiki`, `ollama`, `postgres`, `redis`.
- `13` SLI/SLO зафиксировано на этапе C: `9` сервисных и пользовательских, `2` по внутренним зависимостям, `2` по самому контуру наблюдаемости.
- Все `4` золотых сигнала покрыты на Этапе C: latency, traffic, errors и saturation.

[![Repository](https://img.shields.io/badge/Open_Repository-30363d?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Andrey787878/ai-knowledge-assistant)

---

## Публикации

### [Как я уменьшил Docker-образ Go-приложения с 1.92 GB до 9 MB](https://habr.com/ru/articles/962318/)

Написал техническую статью на Хабре про оптимизацию Docker-образа для Go: пошагово разобрал оптимизацию от наивного подхода до multi-stage с использованием Alpine, scratch, distroless в качестве runtime-образов. Бонусом продемонстрировал подход с использованием UPX-сжатия.

Статья получила заметный отклик: **30k+ просмотров**, **280+ добавлений в закладки**, **рейтинг +81**.

[![Read on Habr](https://img.shields.io/badge/Read_on_Habr-30363d?style=for-the-badge&logo=habr&logoColor=white)](https://habr.com/ru/articles/962318/)

---

## Сайт

В более интерактивном формате с моим опытом и достижениями можно ознакомиться на сайте:

[![Open Website](https://img.shields.io/badge/Open_Website-30363d?style=for-the-badge&logo=googlechrome&logoColor=white)](https://poluyanov.net)

---

## GitHub статистика

<div align="center">

<img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=Andrey787878&theme=transparent" />

</div>
