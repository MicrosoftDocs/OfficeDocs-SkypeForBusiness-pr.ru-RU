---
title: 'Lync Server 2013: схема базы данных сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a18cd17686133219ccc60d5e85fd149df190665a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="94739-102">Схема базы данных сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94739-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94739-103">_**Последнее изменение темы:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="94739-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="94739-104">В этом документе приведена схема базы данных сохраняемого чата в коммуникационном программном обеспечении Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94739-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="94739-105">База данных сохраняемого чата относится к базе данных, соответствующей серверам ролей сервера Lync Server 2013, **PersistentChatStore** (соответствующим базам данных MGC) и **PersistentChatComplianceStore** (соответствующим базам данных mgccomp).</span><span class="sxs-lookup"><span data-stu-id="94739-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="94739-106">Цель публикации этой схемы – обеспечить возможность построения запросов и получения рекомендация по успешному созданию отчетов об использовании чата, активных комнатах, лучших авторах и т. д.</span><span class="sxs-lookup"><span data-stu-id="94739-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="94739-p102">Мы сохраняем за собой право изменять эту схему. Корпорация Майкрософт не дает никаких гарантий в отношении полной обратной совместимости с данной опубликованной схемой.</span><span class="sxs-lookup"><span data-stu-id="94739-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="94739-109">Следуйте приведенным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="94739-109">Follow these best practices:</span></span>

  - <span data-ttu-id="94739-110">SELECT\* //не поддерживается, так как список столбцов может увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="94739-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="94739-111">Изменение схемы пользователем не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="94739-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="94739-112">Операции записи не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="94739-112">No write operations are supported.</span></span>

  - <span data-ttu-id="94739-113">Все создаваемые запросы следует тестировать с помощью баз данных соответствующего размера для проверки того, будут ли они выполняться с должной производительностью.</span><span class="sxs-lookup"><span data-stu-id="94739-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94739-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="94739-114">In This Section</span></span>

  - [<span data-ttu-id="94739-115">Список таблиц сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94739-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="94739-116">Список таблиц соответствия сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94739-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="94739-117">Сведения о таблице сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94739-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="94739-118">Примеры запросов к базе данных сохраняемого чата для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94739-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

