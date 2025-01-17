### Исследование базы данных ClickHouse мобильного приложения розничной сети

Имеем в наличии следующие данные:
1. Таблица installs - содержит данные об установках приложения по дням;
    * DeviceID — идентификатор устройства, на которое было установлено приложение;
    * InstallationDate — дата установки приложения;
    * InstallCost — цена установки приложения в рублях;
    * Platform — платформа, на которой было установлено приложение (iOS/ Android);
    * Source — источник установки приложения (магазин приложения/ рекламная система/ переход с сайта).
2. Таблица events — содержит данные о том, как активно пользователи просматривают товары в приложении по дням;
    * DeviceID — идентификатор устройства, на котором используется приложение;
    * AppPlatform — платформа, на которой используется приложение (iOS/ Android);
    * EventDate — дата, за которую собрана статистика;
    * events — количество просмотров всех товаров за этот день у этого DeviceID.
3. Таблица checks — содержит данные о покупках пользователей в приложении по дням;
    * UserID — идентификатор пользователя;
    * Rub — суммарный чек пользователя на дату;
    * BuyDate — дата, за которую собрана статистика.
4. Таблица devices - таблица соответствия DeviceID к UserID. Это необходимо для объединения данных о просмотрах и установках с покупками, поскольку на этапах установки приложения и просмотра каталога пользователь еще может быть не авторизован.

Ход исследования наглядно представлен в файле .ipynb