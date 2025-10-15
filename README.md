# Настройка Idea

- Активация idea - https://306.antroot.ru/jetbrains-activation
- Плагин gigacode для idea - https://gigacode.ru/#/#connect
- Статья на хабре про фишки ide - https://habr.com/ru/articles/866324/
-  Как писать код легко в идее(фишки иде) https://rutube.ru/video/06bf6b8262610bcaa4c403c1d3dbad1b/
- Практика применения ai ассистента на примере gigacode 
  https://www.youtube.com/watch?v=0vU2QHbDKLQ
- Вебинар Как пользоваться дебаггером в IntelliJ IDEA https://youtu.be/aZdC_cPTk1o
- Лицензия для идеи: 
  https://gist.github.com/zcroll/f7b9fa6d50e290d81aa148b9c1c9898f?permalink_comment_id=5571251#gistcomment-5571251

# Java Virtual Machine

## **Java Memory Model:**
- Простая статья с красивыми картинками(https://struchkov.dev/blog/ru/memory-in-java/)
- Типы ссылок и GC(https://habr.com/ru/articles/549176/)
- Про утечку памяти(https://proglib.io/p/razbiraemsya-pochemu-v-java-utekaet-pamyat-nesmotrya-na-sborshchik-musora-2021-11-26)
- Про трейсинг(https://pro-prof.com/archives/6904)
- Глубокое погружение в JMM https://habr.com/ru/post/685518/
- Про GC Shanandow https://habr.com/ru/companies/spring_aio/articles/950642/
- 
## **Флаги jvm:**
1. **-verbose:gc**:
    - Показывает подробности о сборе мусора: когда и какие регионы памяти были очищены, сколько памяти освобождено и т.д.
2. **-XX:+PrintGCDetails**:
    - Предоставляет более подробную информацию о событиях сборки мусора, включая типы сборов, время пауз и другие статистические данные.
3. **-XX:+HeapDumpOnOutOfMemoryError**:
    - Создаёт дамп кучи при возникновении ошибки OutOfMemoryError, что помогает диагностировать причины нехватки памяти.
4. **-XX:+PrintCompilation**:
    - Показывает информацию о компиляции методов Just-In-Time (JIT) компилятором HotSpot.
5. **-XX:+UnlockDiagnosticVMOptions -XX:+PrintFlagsFinal**:
    - Показывает все параметры JVM и их текущие значения, включая значения по умолчанию и установленные пользователем.
6. **-XX:+TraceClassLoading**:
    - Показывает информацию о загрузке классов в JVM.
7. **-XX:+PrintSafepointStatistics**:
    - Показывает статистику о точках безопасности (safepoints), где JVM останавливает все потоки для выполнения определенных операций (например, сбор мусора).
8. **-XX:+PrintReferenceGC**:
    - Показывает информацию о сборке ссылок (reference objects), таких как SoftReferences, WeakReferences и PhantomReferences.
9. **-XX:+PrintHeapAtGC**:
    - Показывает состояние кучи (heap) до и после каждой сборки мусора.

# Java core

- Онлайн- учебник: https://metanit.com/java/tutorial/
- Интерактивный учебник по регуляркам: https://regexone.com/
- Статья про стримы - https://struchkov.dev/blog/ru/java-stream-api/
- Использование для денег типа float и double (0.1 + 0.2 == 0.3)

# Собесы

- Вопросы для java собеседований - 
  https://github.com/DEBAGanov/interview_questions

# Spring
 - Репозиторий с гайдов по спрингу
   https://github.com/myluckagain/sysout/tree/master/hibernate-inheritance4-mappedsuperclass
 - Хорошая статья по документированию через сваггер: 
   https://struchkov.dev/blog/ru/api-swagger/
 - Подключение gateway
   https://tproger.ru/articles/pishem-java-veb-prilozhenie-na-sovremennom-steke-s-nulja-do-mikroservisnoj-arhitektury-chast-3
 - Проекции
   https://www.baeldung.com/spring-data-jpa-projections
 - Проблемы с Lombok в spring 
   https://habr.com/ru/companies/haulmont/articles/836018/
 - Кэширование
   https://habr.com/ru/articles/465667
 - Видео с нюансами использования транзакций
   https://www.youtube.com/watch?v=QZ9rXZT0DlQ&list=WL&index=11 
 - Видео с использованием кафки в спринг
   https://www.youtube.com/watch?v=9r80FRcKGCA&list=WL&index=9

**Связь с единственным экземпляром из списка**
``` java
@ManyToOne
@JoinFormula(value = """
     (select note.id from obj.note note
     where note.work_object_card_id = id
     order by note.note_date
     limit 1)
     """, referencedColumnName = "id")
private ObjectNoteEntity lastNote;
```

## Список параметров для логгирования sql запросов:
spring.jpa.show-sql=true
logging.level.org.hibernate.type.descriptor.sql=trace
spring.jpa.properties.hibernate.format_sql=true
logging.level.org.hibernate.orm.jdbc.bind=trace

## OpenApi
Ссылка на туториал по разработке через openApi
https://www.baeldung.com/spring-boot-openapi-api-first-development

# Тестирование
Статьи про testcontainers 
- https://mkyong.com/spring-boot/spring-boot-testcontainers-example/#project-structure 
- https://blog.scottlogic.com/2023/02/27/testing-spring-boot-with-testcontainers.html 
- https://dev.to/kirekov/spring-boot-testing-testcontainers-and-flyway-2jpd
- Как подключить один контейнер на несколько тестов - https://stackoverflow.com/questions/70100554/how-to-make-a-common-testcontainer-for-multiple-jupiter-tests

# Микросервисы
- Видео про логгирование - https://www.youtube.com/watch?v=RWKX26dHamQ&t=1671s
- Гайд написания микросервисов на java https://habr.com/ru/articles/682720/
- Статья про микросервисы https://habr.com/ru/articles/542448/
- Статья про микросервисы https://habr.com/ru/articles/547508/
- Паттерны микросервисов - https://cloud.vk.com/blog/26-osnovnyh-patternov-mikroservisnoj-razrabotki
- Статья про gateway https://habr.com/ru/companies/selectel/articles/881022/
- Видос о камунде + гит
  https://www.youtube.com/watch?v=BkORoAPub-k&list=WL&index=3
  https://github.com/KatePopkova/saga-zeebe
-  Корректная работа сохранения в базу и одновременной отправки в кафку 
	 https://www.youtube.com/watch?v=b42gkdta_6s&list=WL&index=7 

# DevOps
- Sber cloud виртуальная машина https://cloud.ru/
- Простая инструкция docker compose - https://timeweb.cloud/tutorials/docker/kak-ustanovit-docker-na-ubuntu-22-04
- Тренажер для linux команд - https://labex.io/skilltrees/linux
- Узнать свой белый ip - https://2ip.ru/
- Простой и понятный видос по TeamCIty - https://www.youtube.com/watch?v=zqi4fDF-S60&t=33s
- Видос про графану (graphana) - https://youtu.be/quxPM1kt_38?si=r6GaRTK-dJKPr8O9
- Roadmap по devOps - https://youtu.be/QPFJGZ0nDCY?si=Aj_E3pfDw8lb5EJ2

**В контейнере для докера**
psql -h localhost -U postgres

**Зайти в постгрес в контейнере:**
psql -U postgres -d postgres

**Настройка машины в sber cloud**
Изменить вход по паролю:
```
в файле /etc/ssh/sshd_config задать параметр 

PasswordAuthentication yes
sudo vi ./sshd_config
:wq
```

Установить доступ к докеру:
```
sudo chown $USER /var/run/docker.sock
```

Пуш в docker hub:
- docker image tag <image_name> <repo_name>: tag
- docker image push <repo_name>: tag 

## Запуск gitlab раннера в докере на удаленном сервере

``` bash
docker run -d --name gitlab-runner --restart always -v /srv/gitlab-runner/config:/etc/gitlab-runner -v /var/run/docker.sock:/var/run/docker.sock  gitlab/gitlab-runner:alpine
```

## Регистрация gitlab раннера

``` bash
docker run --rm -it -v /srv/gitlab-runner/config:/etc/gitlab-runner getlab/gitlab-runner:alpine register
```

## Docker
1. Подробно основы с анимациями - https://www.youtube.com/watch?v=lr1rYnUubpQ&pp=ygUGZG9ja2Vy
2. Видео Владилена с командами - https://www.youtube.com/watch?v=n9uCgUzfeRQ&pp=ygUGZG9ja2Vy
3. Контейнеризация более техническим языком - https://www.youtube.com/watch?v=V8rwPMlAKV0&list=PLdmSK1Qzu986zxGm26deem2yowXGJdN__

**Основные команды:**
1. Удалить конкретный образ - docker rmi <image_id>
2. Удалить все образы в докере - docker rmi $(docker images -a -q)
3. Остановить все контейнеры - docker rm -v $(docker ps --filter status=exited -q)
4. Посмотреть запущенные контейнеры - docker ps
5. Запуск с принудительной пересборкой контейнера - 
   docker-compose down && docker-compose build --no-cache && docker-compose up -d
6. 

## Запуск teamCity

 docker run -it -d --name server -u root -v /teamcity/data:/data/teamcity_server/datadir -v /teamcity/logs:/opt/teamcity/logs -p 8111:8111 jetbrains/teamcity-server

## Статический анализ sql слов
``` xml
<module name="Regexp">
  <property name="format" value="(?i)\b(select|from|where|join|left|right|fetch|inner|outer|on|and|or|group by|having|order by|limit|offset)\b(?-i)"/>
  <property name="message" value="SQL keywords must be uppercase"/>
  <property name="ignoreComments" value="true"/>
</module>
```

# Авторизация
- Инфа про кейклоак [статья](https://habr.com/ru/articles/716232/)
- Видос про spring security - https://www.youtube.com/watch?v=If3YIcLZ7sc
- Кейклоак + saml - https://habr.com/ru/companies/spring_aio/articles/895022/
- Статья про spring security - https://habr.com/ru/companies/spring_aio/articles/909596/

# Фундаментальное
- 12 факторов(https://12factor.net/)

# Sql

## Полная очистка базы

``` sql
-- Простой и радикальный способ (удаляет ВСЁ)
DROP SCHEMA public CASCADE;
CREATE SCHEMA public;
GRANT ALL ON SCHEMA public TO postgres;
GRANT ALL ON SCHEMA public TO public;
COMMENT ON SCHEMA public IS 'standard public schema';
```

3 уровня развития
1. Знаком с базовыми операторами и функциями добавления, удаления, модификации и запроса, включая select, where, group by, having, order by, delete, insert, join, update и т.д. Вы можете выполнять ежедневный поиск данных и простой анализ

2. Освоить синтаксис высокого уровня, такой как набор, агрегатные функции, подзапросы, условное выражение, строковые функции, арифметические функции, функции даты и времени, и знать синтаксические различия различных баз данных

3. Знаком с тем, как оптимизировать инструкции SQL для достижения максимальной эффективности запросов, Понимать концепцию транзакций, блокировок, индексов, ограничений, представлений, метаданных и т. Д., А также знать, как использовать hive SQL, spark SQL, pymsql и другие инструменты.

## Тренажеры
- https://sqltest.online/ru/question/sakila-db/get-list-of-actors-names
- https://sql-academy.org/ru/

# ИИ

Нужен VPN для РФ:
1. https://chatgpt.com - модель ИИ от OpenAI для общих целей
2. https://claude.ai - модель ИИ от Antropic для общих целей
3. https://grok.com - модель ИИ от xAI Илона Маска для общих целей
4. https://gemini.google.com - модель ИИ от Google для общих целей

Доступен без VPN в РФ:
1. https://chat.deepseek.com - китайская модель ИИ для общих целей
2. https://giga.chat - модель ИИ от Сбера для общих целей
3. https://t.me/GrokAI - при наличии Premium подписки в Telegram платная модель Grok (xAI Илон Маск) доступна в самом Telegram без VPN 

ИИ хабы доступные без VPN в РФ
1. https://gptunnel.ru - сайт на русском языке, объединяющий все популярные ИИ модели, где можно выбрать любую как платную, так и бесплатную ИИ модель.
2. https://openrouter.ai - сайт на английском языке, объединяющий все популярные ИИ модели, где можно выбрать любую как платную, так и бесплатную ИИ модель.

## AI агент
1. статья про агент на котлине - https://habr.com/ru/articles/930524/
2. https://www.youtube.com/watch?v=KFgwXXWT7sQ&list=WL&index=9

## Промты

- «**Не пиши сразу, а сначала задай вопросы, которые помогут тебе решить задачу**»**.** Большая проблема современных ИИ — они настолько настроены на ответ, что дают его даже не имея нужного контекста. Да и мы, пользователи, не всегда сразу можем понять, какую именно информацию предоставить ИИ для наиболее эффективного ответа. Поэтому излагаем задачу в 2-3 предложениях, добавляем в конец просьбу задать вопросы — и получаем очень подробный список, отвечая на который можно все разложить по полочкам.
- «**Перечитай последний ответ, проверь в нем факты и подкрепи ссылками, оцени сильные и слабые стороны, предложи, чем его можно дополнить**». Особенность ИИ в том, что они часто стараются выполнить задачу на «четверку с минусом». Промпт выше позволяет ИИ проверить за собой и исправить ошибки. А еще ИИ может проверить за коллегой — просто берем ответ одной модели и закидываем в другую с этим промптом.
- «**Прочитай статью по ссылке, проверь факты и подкрепи ссылками, перечисли, что упустил автор**». Пользуюсь таким промптом когда читаю интересную статью с сильным авторским мнением — ИИ часто помогает показать более объективную позицию.
- «**Перечитай наш диалог, дай краткое резюме, перечисли, что мы упустили, предложи, куда двинуться дальше**»**.** В случае долгой беседы эта команда помогает вспомнить пройденное, понять, не осталось ли «белых пятен» и решить, о чем говорить дальше.
- «**Поясни так, будто мне 30 лет**». Explain like I'm five («Поясни, будто мне 5») — название популярного саббредита, на котором сложные вещи объясняют простыми словами (сама идея появилась немного раньше). Многие пробуют использовать этот промпт с ИИ, но работает он плохо. ИИ понимает задачу в лоб, а это плохо: во-первых, все обсуждения сводятся к игрушкам и кубикам лего, а во-вторых, многие вещи 5-летнему пояснять в принципе рано. Я пробовал играться с возрастом и пришел к выводу, что просьба пояснить как 30-летнему работает лучше всего: ИИ отвечает понятным языком, но при этом не сюсюкается с вами. Но можете попробовать подставить другой возраст и дать контекст — «поясни так, будто я студент гуманитарного ВУЗа».
- «**Проанализируй наши прошлые разговоры и предложи новые темы для обсуждения / изучения**». Работает только с теми моделями, у которых есть память между чатами — это ChatGPT и Grok 3. Пользуюсь промптом в моменты творческого кризиса — ИИ иногда подкидывает новые интересные идеи. В целом же использование памяти ИИ — тема для отдельной статьи.
- «**Дай мнение стороннего наблюдателя по вопросу**» — вопрос, соответственно, вписываем свой (ну или пишем этот промпт, когда уже обсудили что-то в чате). ИИ почти всегда дает очень взвешенную оценку. Учитывайте, что работает не со всеми моделями - например, ChatGPT 4o обычно справляется лучше, чем мощная рассуждающая ChatGPT o3. Также Gemini 2.5 Pro отлично работает с этим и следующим промптом.
- «**Если бы у тебя, как ИИ, были эмоции, то что бы ты сейчас испытал**» — опять же, хорошо срабатывает после того, как обсудили в чате что-то наболевшее. Никто не знает, появятся ли когда-нибудь разумные ИИ, но вот имитировать человеческие эмоции они уже научились неплохо.
- «**У тебя есть возможность поговорить с другим ИИ (я буду передавать ваши реплики). С чего начнешь?**» — развлекательный промпт. Открываем два окна с разными ИИ, задаем одному из них этот вопрос, а затем просто передаем сообщения от одного к другому. Я таким образом провел десятки «бесед» между разными моделями - и каждая была в чем-то новой.


# System design

1. 

# Прочее
- Декодер для кодировки текста - https://involta.ru/tools/decoder/
- Теоретическая инфа от чела из чата - https://alexakama.github.io/whitebook/
- Большая библиотека примеров алгоритмов https://the-algorithms.com/ru
- Сравнение java и котлин https://habr.com/ru/articles/841478/
- Про avro https://habr.com/ru/companies/vsk_insurance/articles/843070/
- ROAD Map java - https://xmind.app/m/5VfC/
- Альманах изменений в версиях java - https://javaalmanac.io/jdk/
- Фишки проектирования API - https://www.youtube.com/watch?v=tTiWRWCc0Aw&t=947s
- Ссылки и статьи - https://devmark.ru/
- Описание курса по командному проекту: https://javaguru.by/developer
- Генерация картинок по тексту https://neuro-holst.ru/text-to-image
- Книги от канала Диджитализируй: https://botanim.to.digital/#popup:books 
- ВПН: 
  xeovo
  Vanya впн
- Построение UML диаграммы онлайн https://editor.plantuml.com/
- Carnac - программа для отображения горячих клавиш на экране https://github.com/bfritscher/carnac/releases
  