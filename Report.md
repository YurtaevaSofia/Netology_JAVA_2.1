# Отчёт о тестировании кода о трансфере денег

## Краткое описание

Код, прилагаемый в репозитории, запускается. В случае, если сумма текущего баланса превышает значение около 2140000000, выдается результат, не соответствующий ожидаемому. 



## Описание тестов

Проводилось функциональное тестирование кода.
Тестовые пары значений:
* currentBalance = 2000000000, transferSumm = 50000000   -   фактический результат 2050000000 соответствует ожидаемому
* currentBalance = 2000000000, transferSumm = 100000000   -   фактический результат 2100000000 соответствует ожидаемому
* currentBalance = 2000000000, transferSumm = 140000000   -   фактический результат 2140000000 соответствует ожидаемому
* currentBalance = 2000000000, transferSumm = 150000000   -   фактический результат -2144967296 НЕ соответствует ожидаемому
* currentBalance = 2000000000, transferSumm = 200000000   -   фактический результат -2094967296 НЕ соответствует ожидаемому
* currentBalance = 2000000000, transferSumm = 500000000   -   фактический результат -1794967296 НЕ соответствует ожидаемому

## Результаты

Баг-репорт https://github.com/YurtaevaSofia/Netology_JAVA_2.1/issues/1#issue-634482887

## Общие рекомендации

Заменить тип переменной currentBalance с int на long.

** Тестирование производилось в следующем окружении: **
* MacOS Sierra весрия 10.12.6, 64-разрядный
* 11.0.7