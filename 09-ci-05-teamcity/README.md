# Домашнее задание к занятию 11 «Teamcity», Марченко Николай

## Подготовка к выполнению

1. В Yandex Cloud создайте новый инстанс (4CPU4RAM) на основе образа `jetbrains/teamcity-server`.
2. Дождитесь запуска teamcity, выполните первоначальную настройку.
3. Создайте ещё один инстанс (2CPU4RAM) на основе образа `jetbrains/teamcity-agent`. Пропишите к нему переменную окружения `SERVER_URL: "http://<teamcity_url>:8111"`.
4. Авторизуйте агент.
5. Сделайте fork [репозитория](https://github.com/aragastmatb/example-teamcity).
6. Создайте VM (2CPU4RAM) и запустите [playbook](./infrastructure).

## Основная часть

1. Создайте новый проект в teamcity на основе fork.
2. Сделайте autodetect конфигурации.
3. Сохраните необходимые шаги, запустите первую сборку master.
4. Поменяйте условия сборки: если сборка по ветке `master`, то должен происходит `mvn clean deploy`, иначе `mvn clean test`.
5. Для deploy будет необходимо загрузить [settings.xml](./teamcity/settings.xml) в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.
8. Мигрируйте `build configuration` в репозиторий.
9. Создайте отдельную ветку `feature/add_reply` в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово `hunter`.
11. Дополните тест для нового метода на поиск слова `hunter` в новой реплике.
12. Сделайте push всех изменений в новую ветку репозитория.
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.
14. Внесите изменения из произвольной ветки `feature/add_reply` в `master` через `Merge`.
15. Убедитесь, что нет собранного артефакта в сборке по ветке `master`.
16. Настройте конфигурацию так, чтобы она собирала `.jar` в артефакты сборки.
17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.
18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
19. В ответе пришлите ссылку на репозиторий.


## Решение

Ссылка на репозиторий:

https://github.com/Doskaks/example-teamcity/tree/master


1_2 fork autodetect

![1_2 fork autodetect](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/1_2%20fork%20autodetect.jpg)

3_первая сборка

![3_первая сборка](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/3_%D0%BF%D0%B5%D1%80%D0%B2%D0%B0%D1%8F%20%D1%81%D0%B1%D0%BE%D1%80%D0%BA%D0%B0.jpg)

5-7_сборка по master

![5-7_сборка по master](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/3_%D0%BF%D0%B5%D1%80%D0%B2%D0%B0%D1%8F%20%D1%81%D0%B1%D0%BE%D1%80%D0%BA%D0%B0.jpg)

7_nexus сборка по master

![7_nexus сборка по master](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/7_nexus%20%D1%81%D0%B1%D0%BE%D1%80%D0%BA%D0%B0%20%D0%BF%D0%BE%20master.jpg)

13_тесты feature_add_reply

![13_тесты feature_add_reply](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/13_%D1%82%D0%B5%D1%81%D1%82%D1%8B%20feature_add_reply.jpg)

17_повторная сботка master

![17_повторная сборка master](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/17_%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%B0%D1%8F%20%D1%81%D0%B1%D0%BE%D1%80%D0%BA%D0%B0%20master.jpg)

17_nexus повторная сборка по master

![17_nexus повторная сборка по master](https://github.com/Doskaks/mnt-homeworks/blob/MNT-video/09-ci-05-teamcity/17_nexus%20%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%B0%D1%8F%20%D1%81%D0%B1%D0%BE%D1%80%D0%BA%D0%B0%20%D0%BF%D0%BE%20master.jpg)





---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
