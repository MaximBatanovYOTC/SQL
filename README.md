# SQL
Заполнение таблицы продукты:
USE [Mbatanov] 
GO
INSERT INTO [dbo].[Product] ([Title] ,[ProductTypeID] ,[ArticleNumber] ,[Image] ,[ProductionPersonCount] ,[ProductionWorkshopNumber] ,[MinCostForAgent])
SELECT
[Наименование продукции] ,pt.ID ,[Артикул] ,[Изображение] ,[Количество человек для производства] ,[Номер цеха для производства] ,[Минимальная стоимость для агента] FROM [dbo].[products_k_import] ki, ProductType pt where ki.[Тип продукции]=pt.Title

Заполнение таблицы materialType:
USE [Mbatanov] GO
INSERT INTO [dbo].[MaterialType] ([Title] ,[DefectedPercent])
SELECT
 distinct [ Тип материала],0
FROM [dbo].[materials_short_k_import]
