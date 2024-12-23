Задание:

Напишите на C# библиотеку для поставки внешним клиентам, которая умеет вычислять площадь круга по радиусу и треугольника по трем сторонам. Дополнительно к работоспособности оценим:

Юнит-тесты

Легкость добавления других фигур

Вычисление площади фигуры без знания типа фигуры в compile-time

Проверку на то, является ли треугольник прямоугольным


Вопрос №2
В базе данных MS SQL Server есть продукты и категории. Одному продукту может соответствовать много категорий, в одной категории может быть много продуктов. 
Напишите SQL запрос для выбора всех пар «Имя продукта – Имя категории». Если у продукта нет категорий, то его имя все равно должно выводиться

Предположим, у нас есть две таблицы: `Products` и `Categories`, и существует сводная таблица `ProductCategories`, которая связывает продукты и категории, тогда
чтобы получить все пары «Имя продукта – Имя категории» потребуется следующий запрос.

SELECT 
    p.ProductName, 
    c.CategoryName
    
FROM 
    Products p
    
LEFT JOIN 
    ProductCategories pc ON p.ProductID = pc.ProductID

LEFT JOIN 
    Categories c ON pc.CategoryID = c.CategoryID

ORDER BY 
    p.ProductName, c.CategoryName;
