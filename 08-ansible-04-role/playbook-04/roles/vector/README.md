# Vector Role

Устанавливает и настраивает Vector - легковесный сборщик логов.

## Переменные

| Параметр | Описание | Значение по умолчанию |
|----------|----------|----------------------|
| `vector_version` | Версия Vector | `0.34.0` |
| `vector_install_dir` | Папка установки | `/opt/vector` |
| `vector_config_dir` | Папка конфигов | `/etc/vector` |
| `clickhouse_host` | Адрес ClickHouse | Обязательный параметр |

## Пример использования

```yaml
- hosts: vector
  roles:
    - role: vector-role
      vars:
        clickhouse_host: "{{ hostvars['clickhouse-01']['ansible_host'] }}"