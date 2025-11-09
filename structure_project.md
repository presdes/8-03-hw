## 📁 Структура проекта и скриптов
### Корневая директория (`~/`)
```
~/
├──gitlab-setup/
│   ├── 📋 README.md                   # Основное руководство
│   ├── 🐳 docker-compose.yml          # Конфигурация инфраструктуры
│   │
│   │   # 🚀 Скрипты развертывания
│   ├── quick-deploy-4core.sh           # Автоматическое развертывание
│   ├── optimize-wsl2-4core.sh          # Оптимизация WSL2
│   ├── setup-hosts.sh                  # Настройка hosts файла
│   ├── wait-for-gitlab.sh              # Мониторинг запуска GitLab
│   │
│   │   # ⚙️ Скрипты настройки
│   ├── setup-runner.sh                 # Настройка GitLab Runner
│   ├── setup-sonarqube.sh              # Настройка SonarQube
│   ├── fix-runner-issues.sh            # Устранение проблем
│   │
│   │   # 🔍 Скрипты диагностики
│   ├── system-check.sh                 # Комплексная диагностика
│   ├── check-gitlab-status.sh          # Проверка GitLab
│   ├── check-runner-status.sh          # Проверка Runner
│   ├── troubleshoot.sh                 # Устранение неполадок
│   │
│   │   # 🗑️ Скрипты очистки
│   ├── reset-project.sh                # Безопасная очистка
│   └── full_reset_docker.sh            # Полная очистка Docker
│
└── web-dev-project/                # 🌐 Пример веб-проекта для тестирования
    ├── .gitlab-ci.yml              # ⚠️ ОБЯЗАТЕЛЬНО В КОРНЕ: Конфигурация CI/CD
    ├── sonar-project.properties    # ⚠️ ОБЯЗАТЕЛЬНО В КОРНЕ: Конфигурация SonarQube
    ├── init-project.sh             # Инициализация Git репозитория
    ├── check-project-structure.sh  # Проверка структуры проекта
    ├── setup-gitlab-project.sh     # Настройка проекта в GitLab
    ├── index.html                  # Основной HTML файл
    ├── package.json                # Конфигурация npm
    ├── css/                        # Скомпилированные стили
    │   └── style.css
    ├── src/less/                   # Исходные LESS файлы
    │   └── style.less
    ├── js/                         # JavaScript файлы
    │   └── app.js
    ├── tests/                      # Тесты
    └── dist/                       # Собранные файлы
        ├── css/
        └── js/
```

### 🚀 Быстрый старт

```bash
# Клонирование репозитория
git clone https://github.com/your-username/gitlab-sonarqube-setup.git
cd gitlab-sonarqube-setup

# Автоматическое развертывание
chmod +x scripts/deployment/*.sh
./scripts/deployment/quick-deploy-4core.sh
```

### 📊 Описание ключевых компонентов

#### 🐳 **Инфраструктура** (`docker-compose.yml`)
- Оптимизированные настройки для 4-ядерных систем
- Предварительно настроенные сервисы: GitLab, SonarQube, GitLab Runner
- Сбалансированное распределение ресурсов

#### 🚀 **Скрипты развертывания**
- `quick-deploy-4core.sh` - полное автоматическое развертывание
- `optimize-wsl2-4core.sh` - оптимизация WSL2 для 4 ядер / 16GB RAM
- `wait-for-gitlab.sh` - интеллектуальный мониторинг запуска

#### 🌐 **Готовый веб-проект**
- Полностью настроенный CI/CD пайплайн
- Интеграция с SonarQube для анализа кода
- Примеры HTML, LESS, JavaScript для тестирования

### 📍 Критические файлы

| Файл | Назначение | Расположение |
|------|------------|--------------|
| `.gitlab-ci.yml` | Конфигурация CI/CD | ⚠️ Корень проекта GitLab |
| `sonar-project.properties` | Конфигурация SonarQube | ⚠️ Корень проекта GitLab |
| `docker-compose.yml` | Конфигурация инфраструктуры | Корень репозитория |

### Подробное описание скриптов

#### 🐳 **Скрипты инфраструктуры** (`~/gitlab-setup/`)
| Скрипт | Назначение | Критичность |
|--------|------------|-------------|
| `quick-deploy-4core.sh` | 🚀 Полное автоматическое развертывание | 🔴 ВЫСОКАЯ |
| `optimize-wsl2-4core.sh` | ⚡ Оптимизация WSL2 для 4 ядер / 16GB RAM | 🔴 ВЫСОКАЯ |
| `setup-hosts.sh` | 📝 Настройка DNS записей в hosts файле | 🔴 ВЫСОКАЯ |
| `wait-for-gitlab.sh` | 🎯 Мониторинг запуска GitLab (15 мин) | 🔴 ВЫСОКАЯ |
| `check-gitlab-status.sh` | 🔍 Быстрая проверка статуса GitLab | 🟡 СРЕДНЯЯ |
| `setup-runner.sh` | 🔧 Настройка и регистрация GitLab Runner | 🔴 ВЫСОКАЯ |
| `check-runner-status.sh` | 🔍 Проверка статуса Runner | 🟡 СРЕДНЯЯ |
| `fix-runner-issues.sh` | 🛠️ Устранение проблем с Runner | 🟡 СРЕДНЯЯ |
| `setup-sonarqube.sh` | 🔧 Настройка SonarQube (инструкция) | 🔴 ВЫСОКАЯ |
| `system-check.sh` | 🔍 Комплексная диагностика всей системы | 🟢 НИЗКАЯ |
| `troubleshoot.sh` | 🛠️ Автоматическое устранение неполадок | 🟡 СРЕДНЯЯ |
| `reset-project.sh` | 🗑️ Безопасная очистка проекта | 🟡 СРЕДНЯЯ |
| `full_reset_docker.sh` | 🔥 Полная очистка Docker (ОПАСНО!) | 🔴 ВЫСОКАЯ |

#### 🌐 **Скрипты веб-проекта** (`~/web-dev-project/`)
| Скрипт | Назначение | Критичность |
|--------|------------|-------------|
| `init-project.sh` | 🎯 Инициализация Git репозитория | 🔴 ВЫСОКАЯ |
| `check-project-structure.sh` | 📋 Проверка структуры проекта | 🟡 СРЕДНЯЯ |
| `setup-gitlab-project.sh` | 🚀 Настройка проекта в GitLab | 🔴 ВЫСОКАЯ |

#### ⚠️ **Критические конфигурационные файлы**
| Файл | Расположение | Назначение |
|------|--------------|------------|
| `.gitlab-ci.yml` | ⚠️ **КОРЕНЬ** репозитория | Конфигурация CI/CD пайплайна |
| `sonar-project.properties` | ⚠️ **КОРЕНЬ** репозитория | Конфигурация SonarQube анализа |
| `docker-compose.yml` | `~/gitlab-setup/` | Конфигурация Docker инфраструктуры |

### 🎯 Рекомендуемая последовательность выполнения

```bash
# 1. Инфраструктура (из ~/gitlab-setup/)
./quick-deploy-4core.sh        # Автоматическое развертывание
./wait-for-gitlab.sh           # Мониторинг запуска
./setup-runner.sh              # Настройка Runner
./setup-sonarqube.sh           # Инструкция по SonarQube

# 2. Веб-проект (из ~/web-dev-project/)
./init-project.sh              # Инициализация Git
./setup-gitlab-project.sh      # Загрузка в GitLab

# 3. Проверка (из ~/gitlab-setup/)
./system-check.sh              # Комплексная диагностика
```

### 📍 Важные замечания по расположению

1. **Скрипты инфраструктуры** должны находиться в `~/gitlab-setup/`
2. **Скрипты проекта** должны находиться в `~/web-dev-project/`
3. **Критические файлы** (`.gitlab-ci.yml`, `sonar-project.properties`) ⚠️ ОБЯЗАТЕЛЬНО в корне репозитория GitLab
4. GitLab автоматически обнаруживает `.gitlab-ci.yml` при пуше в репозиторий
5. SonarScanner ищет `sonar-project.properties` в корне проекта

Эта структура обеспечивает четкое разделение ответственности и легкое управление всей системой! 🚀
