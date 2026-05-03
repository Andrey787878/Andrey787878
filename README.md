<div align="center">

# Андрей Полуянов

## DevOps / SRE инженер

<br>

<p align="center">
  <a href="https://t.me/poluyanovv">
    <img src="https://img.shields.io/badge/Telegram-@poluyanovv-30363d?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>
  <a href="mailto:andrey@poluyanov.net">
    <img src="https://img.shields.io/badge/Email-andrey%40poluyanov.net-30363d?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
  </a>
</p>

<p align="center">
  <a href="https://poluyanov.net">
    <img src="https://img.shields.io/badge/Website-poluyanov.net-30363d?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website">
  </a>
  <a href="https://habr.com/ru/users/Andrey172/">
    <img src="https://img.shields.io/badge/Habr-profile-30363d?style=for-the-badge&logo=habr&logoColor=white" alt="Habr">
  </a>
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
![Git](https://img.shields.io/badge/Git-30363d?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-30363d?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-30363d?style=for-the-badge&logo=kubernetes&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-30363d?style=for-the-badge&logo=ansible&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-30363d?style=for-the-badge&logo=terraform&logoColor=white)
![GitLab CI](https://img.shields.io/badge/GitLab_CI-30363d?style=for-the-badge&logo=gitlab&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-30363d?style=for-the-badge&logo=prometheus&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-30363d?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-30363d?style=for-the-badge&logo=redis&logoColor=white)
![Python](https://img.shields.io/badge/Python-30363d?style=for-the-badge&logo=python&logoColor=white)
![Go](https://img.shields.io/badge/Go-30363d?style=for-the-badge&logo=go&logoColor=white)

</div>

<br>

## Ключевой проект

### [Internal AI Knowledge Assistant](https://github.com/Andrey787878/ai-knowledge-assistant)

DevOps/SRE-кейс внутреннего AI-ассистента знаний компании.

Цель проекта — создать единую централизованную систему знаний, которая использует Wiki.js как базу знаний и предоставляет быстрые, структурированные ответы на вопросы сотрудников.

Стек: Wiki.js, n8n, PostgreSQL, Redis и Ollama.

**Что реализовано:**

- 2 воспроизводимых контура деплоя
- VM-контур: в Yandex Cloud на 4 виртуальных машинах
- Kubernetes-контур: single-node k3s в Yandex Cloud
- инфраструктура через Terraform
- автоматизация через Ansible
- деплой Kubernetes-сервисов через Helmfile
- 2 самописных чарта n8n queue mode и Ollama
- управление секретами через Ansible Vault и SOPS
- TLS через Let's Encrypt и ACME HTTP-01
- reverse proxy через Nginx
- Ingress Traefik, cert-manager и ClusterIssuer
- Security Groups
- Firewall на хостах
- NetworkPolicy с default deny
- PostgreSQL backup/restore
- Redis для queue mode
- smoke-проверки и runbooks
- подробная документация и архитектурные схемы

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
