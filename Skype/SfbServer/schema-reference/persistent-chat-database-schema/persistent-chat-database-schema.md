---
title: Схема базы данных сохраняемого чата
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: В этом документе засвечивается схема базы данных сохраняемого чата в Skype для бизнеса Server.
ms.openlocfilehash: 6f35e947f1cc0c36d6be743d57934453053f4e5c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759351"
---
# <a name="persistent-chat-database-schema"></a>Схема базы данных сохраняемого чата
 
В этом документе засвечивается схема базы данных сохраняемого чата в Skype для бизнеса Server.
  
База данных сохраняемой чат ссылается на базу данных, соответствующую ролям Skype для бизнеса Server Back End **Server PersistentChatStore** (соответствующие базе данных mgc) и **PersistentChatComplianceStore** (соответствующие базе данных mgccomp). Цель публикации этой схемы – обеспечить возможность построения запросов и получения рекомендация по успешному созданию отчетов об использовании чата, активных комнатах, лучших авторах и т. д.
  
> [!IMPORTANT]
> Мы сохраняем за собой право изменять эту схему. Корпорация Майкрософт не дает никаких гарантий в отношении полной обратной совместимости с данной опубликованной схемой. 
  
Следуйте приведенным ниже рекомендациям.
  
- Нет SELECT \* // поддерживается, так как список столбцов может расти.
    
- Изменение схемы пользователем не поддерживается.
    
- Операции записи не поддерживаются.
    
- Все создаваемые запросы следует тестировать с помощью баз данных соответствующего размера для проверки того, будут ли они выполняться с должной производительностью.
    
## <a name="in-this-section"></a>В этом разделе

- [Список таблиц сервера сохраняемого чата](list-of-persistent-chat-server-tables.md)
    
- [Список таблиц сохраняемого соответствия требованиям chat Server в Skype для бизнеса Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Данные таблицы сервера сохраняемого чата](persistent-chat-server-table-details.md)
    
- [Примеры запросов к базе данных сохраняемого чата](sample-persistent-chat-database-queries.md)
    

