---
title: Схема базы данных сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: В этом разделе документируется схема базы данных сохраняемого чата в Skype для бизнеса Server.
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814747"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="7106c-103">Схема базы данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7106c-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="7106c-104">В этом разделе документируется схема базы данных сохраняемого чата в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7106c-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="7106c-105">База данных сохраняемого чата указывает на базу данных, соответствующую серверным ролям сервера **персистентчатсторе** (соответствующей базе данных MGC) и **персистентчаткомплианцесторе** (соответствующей базе данных мгккомп).</span><span class="sxs-lookup"><span data-stu-id="7106c-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="7106c-106">Цель публикации этой схемы — предоставить вам возможность создавать запросы и подробно ознакомиться с подробными сведениями о использовании чата, активных комнатах, основных плакатов и т. д.</span><span class="sxs-lookup"><span data-stu-id="7106c-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7106c-107">Мы резервируем это право для развития этой схемы.</span><span class="sxs-lookup"><span data-stu-id="7106c-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="7106c-108">Корпорация Майкрософт не предоставляет никаких гарантий для обеспечения полной обратной совместимости с этой опубликованной схемой.</span><span class="sxs-lookup"><span data-stu-id="7106c-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="7106c-109">Следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="7106c-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="7106c-110">Функция SELECT\* ///не поддерживается, так как список столбцов может увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="7106c-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="7106c-111">Изменения схемы, созданные пользователем, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7106c-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="7106c-112">Операции записи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7106c-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="7106c-113">Протестируйте любые запросы, которые вы создаете в соответствии с конкретными размерами баз данных, чтобы обеспечить выполнение запросов на уровне в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="7106c-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="7106c-114">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7106c-114">In this section</span></span>

- [<span data-ttu-id="7106c-115">Список таблиц сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7106c-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="7106c-116">Список таблиц соответствия требованиям сервера для работы с сохраняемым сервером чата в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7106c-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="7106c-117">Данные таблицы сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7106c-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="7106c-118">Примеры запросов к базе данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="7106c-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

