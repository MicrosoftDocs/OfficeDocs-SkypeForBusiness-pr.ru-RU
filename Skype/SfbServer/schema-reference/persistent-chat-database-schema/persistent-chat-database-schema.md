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
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="9c7a5-103">Схема базы данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9c7a5-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="9c7a5-104">В этом документе документироваться схема базы данных сохраняемого чата в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="9c7a5-105">База данных сохраняемой беседы относится к базе данных, соответствующей ролям сервера сохраняемой связи Skype для бизнеса Server **PersistentChatStore** (соответствующей базе данных mgc) и **PersistentChatComplianceStore** (соответствующей базе данных mgccomp).</span><span class="sxs-lookup"><span data-stu-id="9c7a5-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="9c7a5-106">Цель публикации этой схемы – обеспечить возможность построения запросов и получения рекомендация по успешному созданию отчетов об использовании чата, активных комнатах, лучших авторах и т. д.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9c7a5-p102">Мы сохраняем за собой право изменять эту схему. Корпорация Майкрософт не дает никаких гарантий в отношении полной обратной совместимости с данной опубликованной схемой.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="9c7a5-109">Следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="9c7a5-110">Нет SELECT \* // не поддерживается, так как список столбцов может увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="9c7a5-111">Изменение схемы пользователем не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="9c7a5-112">Операции записи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="9c7a5-113">Все создаваемые запросы следует тестировать с помощью баз данных соответствующего размера для проверки того, будут ли они выполняться с должной производительностью.</span><span class="sxs-lookup"><span data-stu-id="9c7a5-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="9c7a5-114">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="9c7a5-114">In this section</span></span>

- [<span data-ttu-id="9c7a5-115">Список таблиц сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9c7a5-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="9c7a5-116">Список таблиц соответствия для сервера сохраняемого чата в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9c7a5-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="9c7a5-117">Данные таблицы сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9c7a5-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="9c7a5-118">Примеры запросов к базе данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9c7a5-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

