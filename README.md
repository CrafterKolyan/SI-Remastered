# Набор проектов для SIGame

Для компиляции вам понадобится Visual Studio 2019 и выше.

* *SIPackages* - чтение и запись игровых пакетов SIGame
* *SIEngine* - движок SIGame, проводящий отыгрыш пакетов
* *Notions* - вспомогательные функции по работе со строками
* *QTxtConverter* - библиотека для импорта текстовых файлов с вопросами
* *SIData* - базовые данные SIGame
* *SICore* - проекты коммуникации и игровой логики
* *SIUI* - модель и отображение игрового табло
* *SImulator* - модель и отображение СИмулятора (приложения для игры при помощи проектора)
* *SIQuester* - модель и отображение редактора вопросов SIGame

## План работ
0. Поискать другие аналоги своей игры (узнать зарубежное название игры и проверить на наличие необходимого софта)
1. Отформатировать код (Tab -> 4 spaces) (пишем по (https://docs.microsoft.com/ru-ru/dotnet/csharp/programming-guide/inside-a-program/coding-conventions)[Microsoft C# Coding Conventions])
2. Скомпилировать хоть что-то
3. Скомпилировать SIGame (видимо придётся написать кучу кода, т.к. исходник SIGame не выложен)
4. Переделать систему пересылки вопросов (читай ниже)
### Система пересылки вопросов
4.0 Придумать какую-то синхронизацию времени мастера и слейвов.
4.1. Ведущий (мастер) зашифровывает каждый вопрос в паке и пересылает игрокам (слейвам). Для различных вопросов - различные ключи.
4.2. Перед каждым вопросом игрокам высылается только ключ для расшифровки данного вопроса.
4.2.5 **Начало уязвимого участка**
4.3. Игроки высылают ответ ведущему, что они успешно расшифровали вопрос
4.4. Ведущий высылает время показа вопроса
4.5. Игроки показывают вопрос в необходимое время.
4.5.5 **Конец уязвимого участка**
5. Поднять свой сервер для SIGame

## Приятные бонусы
*.siq* - это просто *.zip* архив с известной структурой.
