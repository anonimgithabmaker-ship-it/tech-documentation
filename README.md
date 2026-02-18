# tech-documentation
# VetClinic — Система управления ветеринарной клиникой
# Описание проекта

VetClinic — это десктопное приложение для автоматизации работы ветеринарной клиники. Программа предназначена для ветеринарных врачей, администраторов и владельцев клиник, которые хотят упростить учёт пациентов, ведение медицинских карт и планирование приёмов.

 Основные возможности:
- Управление клиентами**: добавление, редактирование, удаление, поиск владельцев животных.
- Учёт питомцев**: привязка к владельцу, вид, порода, дата рождения, история болезней.
- Запись на приём**: планирование визитов к ветеринару с проверкой доступности времени.
- Фильтрация и поиск**: быстрый поиск по имени, телефону или другим параметрам.
- Статистика**: отображение ключевых показателей (количество клиентов, питомцев, записей).
- Экспорт/импорт данных**: сохранение и загрузка информации в формате JSON.
- Современный интерфейс**: JavaFX с кастомными CSS-стилями, поддержка тёмной темы.


  Установка и запуск

 Системные требования
- Операционная система: Windows 10/11, macOS 12+, Linux (Ubuntu 20.04+)
- Java Runtime: версия 17 или выше ([скачать](https://adoptium.net/))
- База данных: PostgreSQL 14 или выше
- Оперативная память: минимум 4 ГБ (рекомендуется 8 ГБ)
- Свободное место: 500 МБ

 Пошаговая инструкция

 1. Клонирование репозитория
```bash
git clone https://github.com/your-username/vetclinic.git
cd vetclinic

Structure:
vetclinic/
├── .gitignore                  # Игнорируемые файлы (target, .idea, логи)
├── LICENSE                     # Лицензия MIT
├── README.md                   # Документация проекта (этот файл)
├── pom.xml                     # Конфигурация Maven (зависимости, сборка)
├── database/                   # SQL-скрипты для базы данных
│   └── schema.sql              # Создание таблиц и тестовые данные
├── screenshots/                 # Скриншоты для README
│   ├── main-window.png
│   ├── add-client.png
│   └── statistics.png
└── src/
    ├── main/
    │   ├── java/com/vetclinic/
    │   │   ├── Main.java                    
    │   │   ├── controller/                   
    │   │   │   ├── MainController.java
    │   │   │   └── ClientController.java
    │   │   ├── model/                        
    │   │   │   ├── Client.java
    │   │   │   ├── Pet.java
    │   │   │   └── Appointment.java
    │   │   ├── view/                         
    │   │   │   ├── MainView.java
    │   │   │   ├── AddEditDialog.java
    │   │   │   └── AboutDialog.java
    │   │   ├── db/                            
    │   │   │   └── DatabaseConnection.java
    │   │   └── util/                          
    │   │       ├── FileManager.java
    │   │       └── Validator.java
    │   └── resources/
    │       ├── css/
    │       │   └── style.css                 
    │       └── fxml/
    │           └── main.fxml                   
    └── test/                                   
        └── java/

Opptions for database:
sudo -u postgres psql

CREATE DATABASE vetclinic_db;

\c vetclinic_db;

\i database/schema.sql

\q

Opptions for maven:
mvn clean compile
mvn javafx:run
java -jar target/vetclinic-1.0-SNAPSHOT.jar

