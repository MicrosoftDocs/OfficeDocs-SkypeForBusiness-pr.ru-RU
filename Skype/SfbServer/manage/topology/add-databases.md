---
title: Добавление баз данных в группы обеспечения доступности AlwaysOn в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Сводка: Узнайте, как добавить дополнительные Скайп для сервера баз данных для существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server.'
ms.openlocfilehash: e5217ba16234ea96f205d8ee89b6d31ac6b2df6c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372062"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a>Добавление баз данных в группы обеспечения доступности AlwaysOn в Скайп для Business Server
 
**Сводка:** Узнайте, как добавить дополнительные Скайп для сервера баз данных в существующей группы обеспечения доступности AlwaysOn в Скайп для Business Server.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Добавление баз данных для группы обеспечения доступности AlwaysOn

1. Откройте SQL Server Management Studio и перейдите к группе обеспечения доступности AlwaysOn. Сбое в первичной реплике.
    
2. В построителе топологий задайте полное доменное имя SQL Server из группы обеспечения доступности AlwaysOn полное доменное имя основного узел этой группы.
    
   - Откройте построитель топологий, выберите **загрузить топологию из существующего развертывания**и нажмите **кнопку ОК**.
    
   - Разверните Скайп для сервера, топологии и **Хранилища SQL Server**. Щелкните правой кнопкой мыши хранилище SQL для создания группы обеспечения доступности AlwaysOn и выберите команду **Изменить свойства**.
    
   - В нижней части страницы в поле **Полное доменное имя SQL Server** введите в поле полное имя основного узла группы обеспечения доступности AlwaysOn.
    
3. Опубликуйте топологию. В меню **Действие** щелкните **Топология**, затем **Опубликовать**. После этого нажмите кнопку **Далее** на странице подтверждения.
    
4. Используйте для добавления новой базы данных к группе обеспечения доступности AlwaysOn SQL Server Management Studio.
    

