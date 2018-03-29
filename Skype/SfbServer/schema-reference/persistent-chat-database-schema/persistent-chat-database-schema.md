---
title: Схема базы данных сохраняемого чата
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
ms.openlocfilehash: 1c78ea53438484fb0ad573a815c10ad76f08edca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="f7036-103">Схема базы данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f7036-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="f7036-104">Здесь приведена схема базы данных сохраняемого сеанса беседы в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="f7036-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="f7036-105">База данных Persistent Chat ссылается на базу данных, соответствующий Скайп для ролей Business Server Тыловой сервер **PersistentChatStore** (в соответствии в базу данных mgc) и **PersistentChatComplianceStore** (соответствующий для базы данных mgccomp).</span><span class="sxs-lookup"><span data-stu-id="f7036-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="f7036-106">Цель публикации этой схемы — позволяют создавать запросы и получить некоторые полезные сведения о создания полезных отчетов об использовании чата, активных комнат, верхней плакатов и т. д.</span><span class="sxs-lookup"><span data-stu-id="f7036-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7036-107">Мы оставляем за собой право изменения этой схемы.</span><span class="sxs-lookup"><span data-stu-id="f7036-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="f7036-108">Корпорация Майкрософт не никаких гарантий на обслуживание полную обратную совместимость с этой опубликованную схему.</span><span class="sxs-lookup"><span data-stu-id="f7036-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="f7036-109">Воспользуйтесь следующими рекомендациями:</span><span class="sxs-lookup"><span data-stu-id="f7036-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="f7036-110">Нет ВЫБЕРИТЕ\* / / поддерживается, поскольку список столбцов может расти.</span><span class="sxs-lookup"><span data-stu-id="f7036-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="f7036-111">Изменения схемы не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f7036-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="f7036-112">Операции записи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f7036-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="f7036-113">Тестирование любых запросов, созданных с помощью размера баз данных, чтобы убедиться в том, что запросы можно выполнить на уровне в соответствии со своими потребностями.</span><span class="sxs-lookup"><span data-stu-id="f7036-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="f7036-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="f7036-114">In this section</span></span>

- [<span data-ttu-id="f7036-115">Список таблиц сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f7036-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="f7036-116">Список таблиц соответствия для сервера сохраняемого чата в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f7036-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="f7036-117">Данные таблицы persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="f7036-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="f7036-118">Примеры запросов к базе данных сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="f7036-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

