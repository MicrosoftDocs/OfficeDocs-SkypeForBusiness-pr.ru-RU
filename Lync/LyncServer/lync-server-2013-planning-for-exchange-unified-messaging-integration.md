---
title: 'Lync Server 2013: планирование интеграции единой системы обмена сообщениями Exchange'
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
ms.openlocfilehash: 298e0f2667707c0ff73819b6fdd38ab105474d91
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522246"
---
# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="9b0bb-102">Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0bb-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b0bb-103">_**Последнее изменение темы:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="9b0bb-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="9b0bb-104">Lync Server 2013 поддерживает интеграцию с единой системой обмена сообщениями Exchange для объединения голосовых сообщений и сообщений электронной почты в единую инфраструктуру обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9b0bb-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="9b0bb-105">В Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) и Microsoft Exchange Server 2010 Единая система обмена сообщениями Exchange является одной из нескольких ролей Exchange Server, которые можно установить и настроить.</span><span class="sxs-lookup"><span data-stu-id="9b0bb-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="9b0bb-106">В Microsoft Exchange Server 2013 служба единой системы обмена сообщениями Exchange работает как служба на сервере почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="9b0bb-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="9b0bb-107">Для развертываний Lync Server 2013 Enterprise Voice единая система обмена сообщениями объединяет голосовые сообщения и сообщения электронной почты в единое хранилище, доступное по телефону (голосовой доступ к Outlook) или компьютеру.</span><span class="sxs-lookup"><span data-stu-id="9b0bb-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="9b0bb-108">Единая система обмена сообщениями и Lync Server 2013 работают совместно для обеспечения автоответчика, голосового доступа к Outlook и служб автоматического секретаря для пользователей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9b0bb-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="9b0bb-109">Дополнительные сведения об изменениях архитектуры в Microsoft Exchange Server 2013 приведены в разделе "изменения архитектуры голосовой связи" в документации по Microsoft Exchange Server 2013 по адресу [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730) .</span><span class="sxs-lookup"><span data-stu-id="9b0bb-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [https://go.microsoft.com/fwlink/p/?LinkId=266730](https://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="9b0bb-110">Для поддержки этих функций в локальной среде Exchange единой системы обмена сообщениями необходимо выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="9b0bb-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="9b0bb-111">Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) или последним пакетом обновления</span><span class="sxs-lookup"><span data-stu-id="9b0bb-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="9b0bb-112">Microsoft Exchange Server 2010 или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="9b0bb-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="9b0bb-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0bb-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9b0bb-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="9b0bb-114">In This Section</span></span>

  - [<span data-ttu-id="9b0bb-115">Функции интегрированной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0bb-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="9b0bb-116">Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0bb-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="9b0bb-117">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0bb-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="9b0bb-118">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b0bb-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

