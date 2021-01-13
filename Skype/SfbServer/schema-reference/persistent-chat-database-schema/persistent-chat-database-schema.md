---
title: Схема базы данных сохраняемого чата
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: В этом документе документироваться схема базы данных сохраняемого чата в Skype для бизнеса Server.
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809879"
---
# <a name="persistent-chat-database-schema"></a>Схема базы данных сохраняемого чата
 
В этом документе документироваться схема базы данных сохраняемого чата в Skype для бизнеса Server.
  
База данных сохраняемой беседы относится к базе данных, соответствующей ролям сервера сохраняемой связи Skype для бизнеса Server **PersistentChatStore** (соответствующей базе данных mgc) и **PersistentChatComplianceStore** (соответствующей базе данных mgccomp). Цель публикации этой схемы – обеспечить возможность построения запросов и получения рекомендация по успешному созданию отчетов об использовании чата, активных комнатах, лучших авторах и т. д.
  
> [!IMPORTANT]
> Мы сохраняем за собой право изменять эту схему. Корпорация Майкрософт не дает никаких гарантий в отношении полной обратной совместимости с данной опубликованной схемой. 
  
Следуйте приведенным ниже рекомендациям.
  
- Нет SELECT \* // не поддерживается, так как список столбцов может увеличиваться.
    
- Изменение схемы пользователем не поддерживается.
    
- Операции записи не поддерживаются.
    
- Все создаваемые запросы следует тестировать с помощью баз данных соответствующего размера для проверки того, будут ли они выполняться с должной производительностью.
    
## <a name="in-this-section"></a>В этом разделе:

- [Список таблиц сервера сохраняемого чата](list-of-persistent-chat-server-tables.md)
    
- [Список таблиц соответствия для сервера сохраняемого чата в Skype для бизнеса Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Данные таблицы сервера сохраняемого чата](persistent-chat-server-table-details.md)
    
- [Примеры запросов к базе данных сохраняемого чата](sample-persistent-chat-database-queries.md)
    

