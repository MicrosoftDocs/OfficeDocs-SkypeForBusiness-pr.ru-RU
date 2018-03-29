---
title: Добавление баз данных в группы обеспечения доступности AlwaysOn в Скайп для Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Сводка: Узнайте, как добавить дополнительные Скайп для сервера баз данных для существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Добавление баз данных в группы обеспечения доступности AlwaysOn в Скайп для Business Server 2015
 
**Сводка:** Узнайте, как добавить дополнительные Скайп для сервера баз данных для существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server 2015.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Добавление баз данных для группы обеспечения доступности AlwaysOn

1. Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn. Сбое в первичной реплике.
    
2. В построителе топологий задайте полное доменное имя SQL Server из группы обеспечения доступности AlwaysOn полное доменное имя основного узел этой группы.
    
  - Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.
    
  - Разверните Скайп для сервера, топологии и **Хранилища SQL Server**. Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.
    
  - В нижней части страницы в поле **Полное доменное имя SQL Server** введите в поле полное имя основного узла группы обеспечения доступности AlwaysOn.
    
3. Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.
    
4. Используйте для добавления новой базы данных к группе обеспечения доступности AlwaysOn SQL Server Management Studio.
    

