# Lighthouse Role

Устанавливает и настраивает Lighthouse - веб-интерфейс для мониторинга.

## Переменные

| Параметр | Описание | Значение по умолчанию |
|----------|----------|----------------------|
| `lighthouse_version` | Ветка репозитория | `master` |
| `lighthouse_install_dir` | Папка установки | `/opt/lighthouse` |
| `lighthouse_web_dir` | Веб-директория | `/var/www/html/lighthouse` |

## Пример использования

```yaml
- hosts: lighthouse
  roles:
    - lighthouse-role