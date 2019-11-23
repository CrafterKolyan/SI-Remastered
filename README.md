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
-1. Подумать над тем, чтобы переписать всё на Java для platform independency.  
0. Поискать другие аналоги своей игры (~~узнать зарубежное название игры~~ **Jeopardy!** [(полный список)](https://ru.wikipedia.org/wiki/Jeopardy!#%D0%9C%D0%B5%D0%B6%D0%B4%D1%83%D0%BD%D0%B0%D1%80%D0%BE%D0%B4%D0%BD%D1%8B%D0%B5_%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8_%D0%B8%D0%B3%D1%80%D1%8B) и проверить на наличие необходимого софта)  
1. ~~Отформатировать код (Tab -> 4 spaces)~~ (пишем по [Microsoft C# Coding Conventions](https://docs.microsoft.com/ru-ru/dotnet/csharp/programming-guide/inside-a-program/coding-conventions))
2. Скомпилировать хоть что-то
3. Скомпилировать SIGame (видимо придётся написать кучу кода, т.к. исходник SIGame не выложен)
4. Почекать чё там с нажатием кнопки (почему оно как-то странно работает?)
5. Переделать систему пересылки вопросов (читай ниже)
### Система пересылки вопросов
5.0 Придумать какую-то синхронизацию времени мастера и слейвов.  
5.1. Ведущий (мастер) зашифровывает каждый вопрос в паке и пересылает игрокам (слейвам). Для различных вопросов - различные ключи.  
5.2. Перед каждым вопросом игрокам высылается только ключ для расшифровки данного вопроса.  
5.2.5 **Начало уязвимого участка**  
5.3. Игроки высылают ответ ведущему, что они успешно расшифровали вопрос  
5.4. Ведущий высылает время показа вопроса  
5.5. Игроки показывают вопрос в необходимое время.  
5.5.5 **Конец уязвимого участка**  
6. Поднять свой сервер для SIGame  
7. Покрыть тестами основной функционал кода  
7.1. Выбрать фреймворк  
7.2. Подумать как писать тесты с использованием запущенного клиента и сервера (почитать, как вообще это делают)  
7.3. Сделать GitHub Action или настроить TravisCI / CircleCI для автоматического запуска тестов  

## Приятные бонусы
*.siq* - это просто *.zip* архив с известной структурой.

## Related projects
https://github.com/chlange/jeopardy  
https://github.com/denvaar/jeopardy-game  
https://github.com/tpavlek/Jeopardy  
https://github.com/legacybass/Jeopardy  
https://github.com/mvbattista/jeopardy  
