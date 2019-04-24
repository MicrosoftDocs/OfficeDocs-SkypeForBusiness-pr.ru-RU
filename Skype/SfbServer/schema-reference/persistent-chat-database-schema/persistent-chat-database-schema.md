---
title: Схема базы данных сохраняемого чата
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Здесь приведена схема базы данных сохраняемого сеанса беседы в Скайп для Business Server.
ms.openlocfilehash: 37b22077157def7ea25a5cf70b23a0272a58956e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212693"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="25383-103">Схема базы данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="25383-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="25383-104">Здесь приведена схема базы данных сохраняемого сеанса беседы в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="25383-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="25383-105">База данных Persistent Chat ссылается на базу данных, соответствующий Скайп для ролей Business Server Тыловой сервер **PersistentChatStore** (в соответствии в базу данных mgc) и **PersistentChatComplianceStore** (соответствующий для базы данных mgccomp).</span><span class="sxs-lookup"><span data-stu-id="25383-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="25383-106">Цель публикации этой схемы — позволяют создавать запросы и получить некоторые полезные сведения о создания полезных отчетов об использовании чата, активных комнат, верхней плакатов и т. д.</span><span class="sxs-lookup"><span data-stu-id="25383-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="25383-107">Мы оставляем за собой право изменения этой схемы.</span><span class="sxs-lookup"><span data-stu-id="25383-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="25383-108">Корпорация Майкрософт не никаких гарантий на обслуживание полную обратную совместимость с этой опубликованную схему.</span><span class="sxs-lookup"><span data-stu-id="25383-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="25383-109">Воспользуйтесь следующими рекомендациями:</span><span class="sxs-lookup"><span data-stu-id="25383-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="25383-110">Нет ВЫБЕРИТЕ\* / / поддерживается, поскольку список столбцов может расти.</span><span class="sxs-lookup"><span data-stu-id="25383-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="25383-111">Изменения схемы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25383-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="25383-112">Операции записи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="25383-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="25383-113">Тестирование любых запросов, созданных с помощью размера баз данных, чтобы убедиться в том, что запросы можно выполнить на уровне в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="25383-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="25383-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="25383-114">In this section</span></span>

- [<span data-ttu-id="25383-115">Список таблиц сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="25383-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="25383-116">Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="25383-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="25383-117">Данные таблицы сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="25383-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="25383-118">Примеры запросов к базе данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="25383-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

