# sql_coursework
Курсовая итоговая работа Болдыревой Алёны по теме СУБД (MySQL). Архитектура базы данных на примере сервиса чартера яхт.

Yacht Hunter – это сервис для аренды яхт по всему миру. Это реально существующий проект, который доступен по адресу yachthunter.com.

Основная функция сервиса – это просмотр каталога яхт, доступных направлений и возможность оставить заявку на бронирование той или иной лодки. Прямого бронирования нет, как и эквайринга. Обратная связь осуществляется посредством модальных окон. Есть личный кабинет, который позволяет пользователю просматривать сохраненные в избранное яхты. Также для зарегистрированных пользователей предусматривается дополнительная скидка на аренду. 

Также есть направления, которые имеют 3 уровня вложенности – регионы (акватории), страны и локации в странах (часто – города или побережья). У каждой яхты есть описание, спецификации (длина, год постройки и рефита, регионы плавания, игрушки и развлечения на борту и так далее) и фотографии. Система администрирования у сервиса написана на PHP + Laravel, она предусматривает справочники для игрушек и удобств на яхте – их мы в таблицах обозначим через dic_, а также хранит все данные по заявкам и зарегистрированным пользователям. Важно: у нас есть просто зарегистрированные пользователи, а есть клиенты – те, кто осуществил бронирование или заказал обратный звонок через форму обратной связи. При этом система позволяет добавить к клиенту лодку, по которой была осуществлена заявка/бронь.

Базовые таблицы в базе данных Yacht hunter – это: яхты (yachts), регионы (regions), страны (countries), локации (locations), пользователи (users) – кто зарегистрировался в системе, клиенты (customers) – кто оставил заявку или осуществил бронирование по телефону, форма заявки (callback_form), справочник игрушек (dic_toys), сами игрушки (toys), справочник удобств на яхте (dic_amenties), сами удобства (amenties), фотографии (yachts_photos) и часто задаваемые вопросы (questions), которые в свою очередь разделены по категориям (questions_category).

Разумеется, это далеко не все таблицы в базе данных Yacht Hunter, но для курсового проекта мы рассмотрим именно их. Опишем каждую таблицу, заполним их тестовыми данными и напишем скрипты для выборок.
