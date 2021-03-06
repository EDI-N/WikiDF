#############################################################
**Створення / редагування тегів**
#############################################################

Для роботи з цим методом користувач повинен бути `авторизованим <https://wiki-df.edin.ua/uk/latest/API_DOCflow/Methods/Authorization.html>`__ .

+--------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
|                       **Метод запиту**                       |                                               **HTTP POST**                                                |
+==============================================================+============================================================================================================+
| **Content-Type**                                             | text/json; charset=UTF-8 (тіло запиту/відповіді в json форматі в тілі HTTP запиту)                         |
+--------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
| **URL запиту**                                               |   https://doc.edin.ua/bdoc/tag                                                                             |
+--------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+
| **Параметри, що передаються в URL (разом з адресою методу)** | В рядку заголовка (Header) "Set-Cookie" обов'язково передається **SID** - токен, отриманий при авторизації |
+--------------------------------------------------------------+------------------------------------------------------------------------------------------------------------+

.. important:: 
    Редагування тегу відбувається аналогічним запитом за допомогою перезапису даних, обов'язково при цьому вказувати **tagId**!

**JSON-параметри в тілі HTTP запиту/відповіді**
***********************************************************

``REQUEST``

Таблиця 1 - Опис json-параметрів **запиту** метода API

+----------+--------------------+--------+---------------------------------------------------------+
| Параметр | Mandatory/Optional | Формат |                          Опис                           |
+==========+====================+========+=========================================================+
| name     | M                  | String | назва тегу                                              |
+----------+--------------------+--------+---------------------------------------------------------+
| code     | О                  | long   | унікальний код, якщо не передано створиться автоматично |
+----------+--------------------+--------+---------------------------------------------------------+

``RESPONSE``

У **відповідь** передаються дані тегу (об'єкт **Tag**).

Таблиця 2 - Опис параметрів об'єкта **Tag**

.. csv-table:: 
  :file: for_csv/Tag.csv
  :widths:  1, 12, 41
  :header-rows: 1
  :stub-columns: 0


**Приклади**
*********************************

Приклад тіла **запиту** в json форматі 

.. code:: ruby

  {
    "code": "6418c44baec34df7bc17a66a1989fa1a",
    "name": "Альбатрос"
  }

--------------

Приклад тіла **відповіді** в json форматі 

.. code:: ruby

  {
    "tagId": 409,
    "name": "Альбатрос",
    "code": "6418c44baec34df7bc17a66a1989fa1a"
  }