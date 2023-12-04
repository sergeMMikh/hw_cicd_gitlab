# Домашнее задание к занятию «GitLab» - Михалёв Сергей

## Задание 1

1. Разверните GitLab локально, используя Vagrantfile и инструкцию, описанные в [этом репозитории](https://github.com/netology-code/sdvps-materials/tree/main/gitlab).
2. Создайте новый проект и пустой репозиторий в нём.
3. Зарегистрируйте gitlab-runner для этого проекта и запустите его в режиме Docker. Раннер можно регистрировать и запускать на той же виртуальной машине, на которой запущен GitLab.

### Решение
Скриншоты с настройками раннера в проекте:
* <img src="images/Task_1_2.jpg" alt="Task_1_2" width="500" height="auto">
* <img src="images/Task_1_1.jpg" alt="Task_1_1" width="500" height="auto">

---

### Задание 2

1. Запушьте [репозиторий](https://github.com/netology-code/sdvps-materials/tree/main/gitlab) на GitLab, изменив origin. Это изучалось на занятии по Git.
2. Создайте .gitlab-ci.yml, описав в нём все необходимые, на ваш взгляд, этапы.

В качестве ответа в шаблон с решением добавьте:

### Решение
- Pipeline

```yaml
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script: 
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
```
- Cкриншоты с успешно собранными сборками.
   * <img src="images/Task_2_1.jpg" alt="Task_1_2" width="500" height="auto">
   * <img src="images/Task_2_4.jpg" alt="Task_2_2" width="700" height="auto">
   * <img src="images/Task_2_3.jpg" alt="Task_2_3" width="700" height="auto">


---
