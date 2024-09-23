# TikTok

## 1. Тема и целевая аудитория

### Тема

TikTok - сервис для создания и просмотра коротких видео

### Целевая аудитория

- TikTok насчитывает 1,66 миллиарда ежемесячных активных пользователей по всему миру. [[2](#использованные-источники)]
- На сегодняшний день TikTok скачали более 4,92 миллиарда раз. [[1](#использованные-источники)]
- Страны с наибольшим количеством пользователей TikTok. [[1](#использованные-источники)]

| Страна               | Количество пользователей TikTok |
|----------------------|---------------------------------|
| Соединенные Штаты    | 148.92 миллиона                 |
| Индонезия            | 127,5 миллиона                  |
| Бразилия             | 101 миллион                     |
| Мексика              | 74,15 миллиона                  |
| Вьетнам              | 67,72 миллиона                  |
| Российская Федерация | 58,59 миллиона                  |
| Пакистан             | 54,38 миллиона                  |
| Филиппины            | 49,09 миллиона                  |
| Таиланд              | 44,38 миллиона                  |
| Турция               | 37,73 миллиона                  |
| Бангладеш            | 37,36 миллиона                  |
| Саудовская Аравия    | 35,1 миллиона                   |
| Египет               | 32,94 миллиона                  |

### Ключевой функционал
- Регистрация и авторизация
- Просмотр видео в ленте
- Подписки на других пользователей
- Добавление в друзья
- Чат
- Отправка/получение видео
- Комментирование видео
- Публикация видео
- Реакции
- Добавить видео в избранное

### Ключевые продуктовые решения
- Дополнительные реакции смайликами
- Рекомендации, основанные на местоположении пользователя (видео людей, находящихся поблизости в городе или районе)
- История просмотров

## 2. Расчет нагрузки

### Основные данные для расчета нагрузки
- MAU - 1,66 млрд. пользователей [[2](#использованные-источники)]
- DAU - 600 млрд. пользователей [[2](#использованные-источники)]
- С ноября 2021 по январь 2022 года в TikTok регистрировалось более 650 тысяч новых пользователей каждый день (это почти 8 новых аккаунтов в секунду).[[7]()]
- Среднее время пользования приложением за день 58 мин. [[3](#использованные-источники)]
- В день пользователи выкладывают 34 млн. видео [[5](#использованные-источники)]
- Средний размер 15 сек. видео 4мб. [[4](#использованные-источники)]
- Максимальный размер видео 287.6 МБайт [[6](#использованные-источники)]
- Коэффициент соотношения пикового трафика к среднему k=1.65

### Публикация видео
#### Продуктовые метрики
Средний месячный размер хранилища пользователя равен:
4 МБ * (34 млн видео в день / 600 млн пользователей) * 30 дней = 6.8 МБ.

Следовательно, средний размер хранилища пользователя(за 5 лет):
6.8МБ * 12 месяцев * 5 лет = 408 МБ (0.39 ГБ)

Среднее количество действий пользователя в день:
34 млн видео в день / 600 млн пользователей = 0.06 видео в день

#### Технические метрики
Пользователь в среднем выкладывает 0.06 видео в день.
Следовательно, среднее количество запросов в секунду равно:
0.06 * 600000000 / (24 * 60 * 60) = 416 RPS

Размер хранения публикаций видео:
0.39 ГБ * 600000000 / 1024 / 1024 = 228515 Тб (223 Пб)

Максимальный размер видео в TikTok составляет 287,6 мегабайта. Пиковое потребление данных приходится на одни сутки. Поскольку пользователи из разных часовых поясов смотрят видео в разное время, средний трафик равномерно распределяется в течение суток. Поэтому коэффициент, на который нужно умножить средний трафик, чтобы получить пиковый, можно взять равным 1,65:
(287.6 * 8 / 1000 / 1000) Тбит * 34 млн/д / (24 * 60 * 60) * 1.65 = 1.4939 Тбит/с

Суммарный суточный трафик:
34 млн/д * 4 МБ / 1024 = 132812 Гб/д (129,7 Тб/д)

### Просмотр ленты

#### Продуктовые метрики
Средний размер хранилища пользователя:
довольно незначительный: хранить идентификаторы пользователя и просмотренные им видео, поэтому можно не учитывать.

Средний размер видео 15 секунд, следовательно, при том что среднее время в приложении в день 58 минут, пользователь в среднем смотрит:
60 / 15 * 58 = 232 действий/день

#### Технические метрики
Размер хранения не учитываем из-за незначительных данных.

Пользователь в среднем смотрит 284 видео в день, среднее количество запросов в секунду равно:
345 * 600000000 / (24 * 60 * 60) = 2395833 RPS

За 5 минут постоянно листая в среднем получается 150 МБ на все запросы для просмотра ленты.
Пиковое потребление в течение суток. Трафик по часам распределяется равномерно, потому что пользователи из разных часовых поясов, поэтому средний трафик от пикового не отличается, поэтому возьмем небольшой коэфицент k=1.65, на который умножим этот средний трафик, и получим пиковый:
((((150 МБ / (5 * 60) секунд) Мб/с * 8 / 1000 / 1000) Тбит/с * (90 * 60)c) Тбит * 600 млн/д) Тбит/д / (24 * 60 * 60) Тбит/с * 1.65 = 247.5 Тбит/с

Суммарный суточный трафик:
((150 МБ / (5 * 60)) МБ/с / 1024 Гб/c * (90 * 60 c/д)) Гб/д * 600млн = 1582031250 Гб/день (1508 Пб/день)

### Регистрация
С ноября 2021 по январь 2022 года в TikTok регистрировалось более 650 тысяч новых пользователей каждый день, следовательно:
650000 / 24 / 60 / 60 = 7.52 регистраций/секунду

### Авторизация
Предположим, что авторизуются пользователи в 10 раз чаще, чем регистрируются, поэтому имеем:
7.52 * 10 = 75.2 авторизаций/секунду

### Реакции/комментарии
Мы ранее получили, что пользователь в среднем смотрит 284 видео в день. При том, что пользователь в среднем лайкает каждое 10 видео и комментирует каждое 50ое, получаем в среднем на пользователя:
284 / 20 = 14,2 лайков/день на пользователя
284 / 70 = 4,05 комментария/день на пользователя

Теперь посчитаем RPS и RPD для лайков и комментариев:
18 * 600000000 = 8 520 000 000 лайков/день
8 520 000 000 / 24 / 60 / 60 = 98611 лайков/секунду

4,05 * 600 000 000 = 2 430 000 000 комментариев/день
2 430 000 000 / 24 / 60 / 60 = 28125 комментариев/секунду

### Итоговые таблицы

#### Продуктовые метрики:
| Действие         | Средний размер хранилища пользователя (ГБайт) | Среднее количество действий пользователя в день |
|------------------|-----------------------------------------------|-------------------------------------------------| 
| Публикация видео | 0.39                                          | 0.05                                            |
| Просмотр ленты   | Незначителен                                  | 284                                             |

#### Технические метрики
| Действие         | Размер хранения (Тб) | Пиковое потребление в течении суток (Тбит/с) | Суммарный суточный трафик (Гбайт/д) |
|------------------|----------------------|----------------------------------------------|-------------------------------------|
| Публикация видео | 228515               | 1.4939                                       | 132812 Гбайт/д                      | 
| Просмотр ленты   | Незначителен         | 247.5                                        | 1582031250                          |

#### RPS
| Действие         | RPS     |
|------------------|---------| 
| Публикация видео | 416     |
| Просмотр ленты   | 2395833 |
| Регистрация      | 7.52    |
| Авторизация      | 75.2    |
| Реакции          | 98611   |
| Комментарии      | 28125   |

#### Глобальная балансировка нагрузки

### Географическое расположение дата-центров
![img.png](https://i.imgur.com/cOflQWC.png)

На основе данных из раздела «Распределение аудитории по странам» можно сделать вывод, что наиболее значительная часть пользователей TikTok проживает в Северной и Южной Америке (США, Мексика, Бразилия) и Индонезии.

В Европе аудитория TikTok распределена относительно равномерно. Особенность азиатского рынка заключается в том, что TikTok заблокирован в Индии, а в Китае используется его локальная версия — Douyin, которая в этом обзоре не рассматривается.

Учитывая эти данные, целесообразно расположить дата-центры в крупных городах США, равномерно распределив их по стране:
- Нью-Йорк
- Лос-Анджелес
- Даллас

Следующей по числу пользователей является Индонезия, поэтому там также следует разместить несколько дата-центров:
- Джакарта
- Медан

В Бразилии, где также велика аудитория TikTok, разместим дата-центры в ключевых городах:
- Бразилиа
- Сан-Паулу

Несмотря на близость Мексики к США, разумно установить дата-центр и там, так как количество пользователей TikTok в Мексике довольно велико:
- Мехико

Россия также входит в число стран с большим числом пользователей, поэтому добавим дата-центр:
- Москва

Для Европы предложим следующее размещение дата-центров в крупнейших городах:
- Лондон (обеспечивает покрытие большей части Европы)
- Анкара (охватывает как часть Европы, так и страны Ближнего Востока)

В Азии, чтобы обеспечить максимальный охват, разместим дата-центры в удалённых друг от друга крупных городах:
- Ханой
- Токио

Для покрытия небольшой аудитории в Африке целесообразно разместить дата-центр в одном из крупных городов, расположенном ближе к центру континента:
- Лагос

### DNS
Для DNS балансировки будем использовать Latency-based DNS. Сервер выдает адрес ближайшего к пользователю ДЦ с минимальным RTT.
Т.к. tiktok предоставляет видеоконтент, нам нужно обеспечить быстрое воспроизведение видео с минимальными задержками. Latency-based будет направлять пользователей на ближайший по задержке сервер, что критично для стриминга и воспроизведения видео.

### BGP
Будем использовать BGP Anycast, чтобы для нескольких дата-центров находящихся в одной стране можно было выдавать один ip адрес, а пользователь будет направляться на ближайший дата-центр

### Использованные источники

1. [How Many People Use TikTok (2024 Statistics)
By Shubham Singh / August 20, 2024](https://www.demandsage.com/tiktok-user-statistics/)
2. [TikTok Revenue and Usage Statistics (2024)](https://www.businessofapps.com/data/tik-tok-statistics/)
3. [Average Time Spent on TikTok Statistics (2024)](https://explodingtopics.com/blog/time-spent-on-tiktok)
4. [How Much Data Does TikTok Use & How to Reduce it?](https://blog.talkhome.co.uk/technology/how-much-data-does-tiktok-use/https://blog.talkhome.co.uk/technology/how-much-data-does-tiktok-use/)
5. [How Many Video Are Uploaded to TikTok Per Day?](https://techjury.net/blog/how-many-videos-are-uploaded-to-tiktok-daily/)
6. [Ideal TikTok Vide Size: Ultimate Guide To TikTok Video Sizes (2024)](https://www.shopify.com/au/blog/tiktok-video-size)
7. [Сколько пользователей в TikTok? (сентябрь 2024)](https://inclient.ru/tiktok-stats/)
