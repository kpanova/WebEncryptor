# WebEncryptor

Web-приложение для шифрования сообщений.

# База данных

База данных создается при первом запуске приложения с использованием подхода Code First в Entity Framework.

Таблица шифрования заполняется с помощью сдвига символов на N.

Используется N=10:

![Пример базы данных](https://i.imgur.com/FNI1mny.png)

# Серверная часть

Серверная часть осуществляет кодирование символов в соответствии с таблицей шифрования из базы данных.

Пример сообщения:
> Ваше сообщение теперь зашифровано.

Получим:
> Мквп ышшлгпчтп ьпщпъж сквтюъшмкчш.

Старое сообщение сохраняется в базу данных:

![Старое сообщение](https://i.imgur.com/It2ROBj.png)

# Клиентская часть

Клиентская часть сделана с использованием фреймворка Bootstrap.

Вид страницы:

![Клиентская часть 1](https://i.imgur.com/X6HGUlm.png)

После ввода сообщения и нажатия кнопки "Отправить", отправляется POST-запрос с содержимым поля ввода.

После обработки POST-запроса зашифрованное сообщение добавляется в `textarea` защищенное от записи.

![Клиентская часть - зашифрованное сообщение](https://i.imgur.com/laGKZSe.png)

Следующее сообщение после обработки добавится в `textarea`.

![Клиентская часть - зашифрованное сообщение 2](https://i.imgur.com/LiLmyvk.png)

# Добавление базы данных в "Обзреватель серверов" в Visual Studio 2015+

Перевод раздела [Description - LocalDB](https://msdn.microsoft.com/library/hh510202(v=sql.110).aspx#Anchor_1) на сайте msdn.

>После установки LocalDB становится экземпляром SQL Server Express, который способен создавать и открывать базы данных SQL Server. Файлы системной базы данных, как правило, хранятся в каталоге AppData пользователя, который обычно скрыт. Например, C:\Users\<пользователь>\AppData\Local\Microsoft\Microsoft SQL Server Local DB\Instances\LocalDBApp1\. Файлы пользовательской базы данных хранятся в месте, указанном пользователем, как правило, в папке C:\Users\<пользователь>\Мои документы\.

Или же можно ввести в командной строке команду `sqllocaldb i` в ответ получим иснтанцию:

![Командная строка](https://i.imgur.com/pPbbiUh.png)

После этого добавляем подключение базы данных, указывая нашу инстанцию:

![Добавление локальной базы данных](https://i.imgur.com/d3cFCan.png)

После обновление наша база данных появитсе в списке баз данных.
