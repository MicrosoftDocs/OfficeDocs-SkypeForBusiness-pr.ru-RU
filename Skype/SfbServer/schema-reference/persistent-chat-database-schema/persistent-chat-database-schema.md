---
title: Схема базы данных сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Здесь приведена схема базы данных сохраняемого сеанса беседы в Скайп для Business Server.
ms.openlocfilehash: 5e10f47a7eeb04de08766bae2957773db35d88f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930010"
---
# <a name="persistent-chat-database-schema"></a>Схема базы данных сохраняемого чата
 
Здесь приведена схема базы данных сохраняемого сеанса беседы в Скайп для Business Server.
  
База данных Persistent Chat ссылается на базу данных, соответствующий Скайп для ролей Business Server Тыловой сервер **PersistentChatStore** (в соответствии в базу данных mgc) и **PersistentChatComplianceStore** (соответствующий для базы данных mgccomp). Цель публикации этой схемы — позволяют создавать запросы и получить некоторые полезные сведения о создания полезных отчетов об использовании чата, активных комнат, верхней плакатов и т. д.
  
> [!IMPORTANT]
> Мы оставляем за собой право изменения этой схемы. Корпорация Майкрософт не никаких гарантий на обслуживание полную обратную совместимость с этой опубликованную схему. 
  
Воспользуйтесь следующими рекомендациями:
  
- Нет ВЫБЕРИТЕ\* / / поддерживается, поскольку список столбцов может расти.
    
- Изменения схемы не поддерживаются.
    
- Операции записи не поддерживаются.
    
- Тестирование любых запросов, созданных с помощью размера баз данных, чтобы убедиться в том, что запросы можно выполнить на уровне в соответствии со своими потребностями.
    
## <a name="in-this-section"></a>Содержание

- [Список таблиц сервера сохраняемого чата](list-of-persistent-chat-server-tables.md)
    
- [Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Данные таблицы сервера сохраняемого чата](persistent-chat-server-table-details.md)
    
- [Примеры запросов к базе данных сохраняемого чата](sample-persistent-chat-database-queries.md)
    

