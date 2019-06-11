---
title: 'Lync Server 2013: схема базы данных сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f35b1551b1ef7f228c70cbb76e748eae5e7cf59
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="fb8d9-102">Схема базы данных сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb8d9-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb8d9-103">_**Тема последнего изменения:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="fb8d9-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="fb8d9-104">В этом документе описана схема базы данных сохраняемого чата в программном обеспечении Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="fb8d9-105">База данных сохраняемого чата указывает на базу данных, соответствующую серверным ролям Lync Server 2013, **персистентчатсторе** (соответствующей базе данных MGC) и **персистентчаткомплианцесторе** (соответствующей мгккомп база данных).</span><span class="sxs-lookup"><span data-stu-id="fb8d9-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="fb8d9-106">Цель публикации этой схемы — предоставить вам возможность создавать запросы и подробно ознакомиться с подробными сведениями о использовании чата, активных комнатах, основных плакатов и т. д.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fb8d9-107">Мы резервируем это право для развития этой схемы.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="fb8d9-108">Корпорация Майкрософт не предоставляет никаких гарантий для обеспечения полной обратной совместимости с этой опубликованной схемой.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="fb8d9-109">Следуйте этим рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-109">Follow these best practices:</span></span>

  - <span data-ttu-id="fb8d9-110">Функция SELECT\* ///не поддерживается, так как список столбцов может увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="fb8d9-111">Изменения схемы, созданные пользователем, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="fb8d9-112">Операции записи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-112">No write operations are supported.</span></span>

  - <span data-ttu-id="fb8d9-113">Протестируйте любые запросы, которые вы создаете в соответствии с конкретными размерами баз данных, чтобы обеспечить выполнение запросов на уровне в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="fb8d9-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb8d9-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="fb8d9-114">In This Section</span></span>

  - [<span data-ttu-id="fb8d9-115">Список таблиц сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb8d9-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="fb8d9-116">Список таблиц соблюдения требований для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb8d9-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="fb8d9-117">Данные таблицы сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb8d9-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="fb8d9-118">Примеры запросов к базе данных сохраняемого чата для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb8d9-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

