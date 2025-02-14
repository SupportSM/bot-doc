# 8. C++




## 8.1. Редактор формул

Редактировать формулы на C++ вы можете во вкладке Formulas, которая находится в дереве по пути:
Portfolios - "название портфеля" - Formulas;
Portfolios - "название портфеля" - "название инструмента" - Formulas;
В первом случае будут отображены поля Trade formula, Extra field#1 и Extra field#2.
Во втором Count formula, Ratio buy formula, Ratio sell formula.

В редакторе формул существует возможность тестового выполнения выбранной формулы (кнопка Test), при этом на момент вычисления формулы создаётся временная копия портфеля, НО если вы в формуле изменяете значения полей портфеля, и у вас существует портфель с тем же именем, то изменения применятся к этому порфтелю.



## 8.2. Важно

При написании формул на языке программирования C++ на код накладываются некоторые ограничения:
вы пишете только тело соответствующих функций, все функции должны возвращать значение типа double.
запрещено использование некоторых символов и слов: "\001", "#nl", "#tab".
вы можете получить доступ к любому портфелю робота, к инструменту портфеля робота, а также к инструменту биржи, который фигурирует хотя бы в одном из ваших порфтелей.
вы можете изменять значения некоторых полей порфтелей и инструментов портфелей. При изменении занчений каких-то полей, вы можете "сломать" работу штатного алгоритма робота, имейте это в виду. В связи с этим для экстренного отключения торговли и выключения всех расчётов по формулам в меню действий с портфелями предусмотрен пункт Stop formulas.
портфель (структура portfolio) содержит методы data() и extra() которые позволяют получить доступ к словарям, в которые можно сохранять данные между вызовами формул.
Важно: если значение поля какой-либо бумаги еще не было получено с биржи или для бумаги с данной биржи нельзя получить значение этого поля, то вы получите 0. Нужно понимать что, например, на пустом стакане вы можете получить 0 в качестве цены бида или оффера, поэтому всегда проверяйте значения на равенство нулю в тех ситуациях, где это критично (например, при делении или при нахождении среднего арифметического бида и оффера).

Важно: рекомендуется пользоваться именно даннйо версией API формул, т.к. она дает больше возможностей и быстрее работает.