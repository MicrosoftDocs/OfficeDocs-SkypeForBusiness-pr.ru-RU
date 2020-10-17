---
title: 'Lync Server 2013: планирование интеграции единой системы обмена сообщениями Exchange'
description: 'Lync Server 2013: планирование интеграции единой системы обмена сообщениями Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Exchange Unified Messaging integration
ms:assetid: e7c63a71-2d99-4aa9-b649-36c1a431bdf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399031(v=OCS.15)
ms:contentKeyID: 48185880
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31296444d21a86a7837da3e29fc2152f3ca96ccc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571885"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="d1eac-103">Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1eac-103">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1eac-104">_**Последнее изменение темы:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="d1eac-104">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="d1eac-105">Lync Server 2013 поддерживает интеграцию с единой системой обмена сообщениями Exchange для объединения голосовых сообщений и сообщений электронной почты в единую инфраструктуру обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d1eac-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="d1eac-106">В Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) и Microsoft Exchange Server 2010 Единая система обмена сообщениями Exchange является одной из нескольких ролей Exchange Server, которые можно установить и настроить.</span><span class="sxs-lookup"><span data-stu-id="d1eac-106">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="d1eac-107">В Microsoft Exchange Server 2013 служба единой системы обмена сообщениями Exchange работает как служба на сервере почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1eac-107">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="d1eac-108">Для развертываний Lync Server 2013 Enterprise Voice единая система обмена сообщениями объединяет голосовые сообщения и сообщения электронной почты в единое хранилище, доступное по телефону (голосовой доступ к Outlook) или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="d1eac-108">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="d1eac-109">Единая система обмена сообщениями и Lync Server 2013 работают совместно для обеспечения автоответчика, голосового доступа к Outlook и служб автоматического секретаря для пользователей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d1eac-109">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="d1eac-110">Дополнительные сведения об изменениях архитектуры в Microsoft Exchange Server 2013 приведены в разделе "изменения архитектуры голосовой связи" в документации по Microsoft Exchange Server 2013 по адресу [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="d1eac-110">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="d1eac-111">Для поддержки этих функций в локальной среде Exchange единой системы обмена сообщениями необходимо выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d1eac-111">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="d1eac-112">Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) или последним пакетом обновления</span><span class="sxs-lookup"><span data-stu-id="d1eac-112">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="d1eac-113">Microsoft Exchange Server 2010 или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="d1eac-113">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="d1eac-114">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1eac-114">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d1eac-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="d1eac-115">In This Section</span></span>

  - [<span data-ttu-id="d1eac-116">Функции интегрированной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1eac-116">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="d1eac-117">Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1eac-117">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="d1eac-118">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1eac-118">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="d1eac-119">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1eac-119">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

