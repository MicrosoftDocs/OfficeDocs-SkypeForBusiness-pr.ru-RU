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
ms.openlocfilehash: 9325cdce67113c46ec02879417748a2e3dd0397d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="dd1b3-102">Планирование интеграции единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b3-102">Planning for Exchange Unified Messaging integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd1b3-103">_**Тема последнего изменения:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="dd1b3-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="dd1b3-104">Lync Server 2013 поддерживает интеграцию с единой системой обмена сообщениями Exchange (UM) для комбинирования голосовой почты и обмена сообщениями в одной инфраструктуре обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="dd1b3-104">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="dd1b3-105">В Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) и Microsoft Exchange Server 2010 сервер единой системы обмена сообщениями Exchange (UM) — это одна из нескольких ролей Exchange Server, которые можно установить и настроить.</span><span class="sxs-lookup"><span data-stu-id="dd1b3-105">In Microsoft Exchange Server 2007 Service Pack 1 (SP1) and Microsoft Exchange Server 2010, Exchange Unified Messaging (UM) is one of several Exchange server roles that you can install and configure.</span></span>

<span data-ttu-id="dd1b3-106">В Microsoft Exchange Server 2013 служба единой системы обмена сообщениями работает в качестве службы сервера почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="dd1b3-106">In Microsoft Exchange Server 2013, Exchange UM runs as a service on an Exchange Mailbox server.</span></span> <span data-ttu-id="dd1b3-107">Для корпоративных развертываний на Lync Server 2013, единая система обмена сообщениями объединяет голосовую почту и сообщения электронной почты в едином магазине, доступном с телефона (голосовой доступ к Outlook) или на компьютере.</span><span class="sxs-lookup"><span data-stu-id="dd1b3-107">For Lync Server 2013 Enterprise Voice deployments, Unified Messaging combines voice messaging and email messaging into a single store that is available from a telephone (Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="dd1b3-108">Единая система обмена сообщениями и Lync Server 2013 работают вместе для обеспечения ответа на звонки, голосового доступа к Outlook и служб автоматического ассистента для пользователей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="dd1b3-108">Unified Messaging and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto-attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="dd1b3-109">Дополнительные сведения об изменениях архитектуры в Microsoft Exchange Server 2013 можно найти в разделе "изменения архитектуры голосовой связи" в документации по Microsoft Exchange Server 2013 [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730)по адресу.</span><span class="sxs-lookup"><span data-stu-id="dd1b3-109">For more information about the architecture changes in Microsoft Exchange Server 2013, see “Voice Architecture Changes” in the Microsoft Exchange Server 2013 documentation at [http://go.microsoft.com/fwlink/p/?LinkId=266730](http://go.microsoft.com/fwlink/p/?linkid=266730).</span></span>

<span data-ttu-id="dd1b3-110">Для того чтобы эти функции поддерживались в локальной среде Exchange UM, необходимо выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="dd1b3-110">For these features to be supported in an on-premises Exchange UM deployment, you must be running one of the following:</span></span>

  - <span data-ttu-id="dd1b3-111">Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="dd1b3-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack</span></span>

  - <span data-ttu-id="dd1b3-112">Microsoft Exchange Server 2010 или последний пакет обновления</span><span class="sxs-lookup"><span data-stu-id="dd1b3-112">Microsoft Exchange Server 2010 or latest service pack</span></span>

  - <span data-ttu-id="dd1b3-113">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b3-113">Microsoft Exchange Server 2013</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd1b3-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="dd1b3-114">In This Section</span></span>

  - [<span data-ttu-id="dd1b3-115">Функции интегрированной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b3-115">Features of integrated Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-features-of-integrated-unified-messaging.md)

  - [<span data-ttu-id="dd1b3-116">Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b3-116">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="dd1b3-117">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b3-117">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

  - [<span data-ttu-id="dd1b3-118">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b3-118">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

