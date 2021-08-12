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
description: В этом документе засвечивается схема базы данных сохраняемого чата в Skype для бизнеса Server.
ms.openlocfilehash: bc314413d2bb7a3d5916396f1e8f281d2217e9058d087dcec8bcc486ee7f172f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280932"
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
    
## <a name="in-this-section"></a>Содержание

- [Список таблиц сервера сохраняемого чата](list-of-persistent-chat-server-tables.md)
    
- [Список таблиц сохраняемого соответствия требованиям chat Server в Skype для бизнеса Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Данные таблицы сервера сохраняемого чата](persistent-chat-server-table-details.md)
    
- [Примеры запросов к базе данных сохраняемого чата](sample-persistent-chat-database-queries.md)
    

