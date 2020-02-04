---
title: 'Lync Server 2013: рекомендации по интеграции локальной единой системы обмена сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f3e57245f0a8edf5b545f9a67547e6be6f63399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="2053f-102">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2053f-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2053f-103">_**Тема последнего изменения:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="2053f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="2053f-104">Ниже приведены рекомендации по развертыванию корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="2053f-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2053f-105">Единая система обмена сообщениями Exchange поддерживает IPv6 только в том случае, если вы также используете УКМА 4.</span><span class="sxs-lookup"><span data-stu-id="2053f-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="2053f-106">Развертывание сервера Lync Server 2013 Standard Edition или пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2053f-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="2053f-107">Подробнее об установке можно найти в разделе [развертывание Lync Server 2013](lync-server-2013-deploying-lync-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2053f-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="2053f-108">Работайте вместе с администраторами Exchange, чтобы подтвердить, какие задачи каждый из вас будет выполнять для обеспечения успешной интеграции.</span><span class="sxs-lookup"><span data-stu-id="2053f-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="2053f-109">Разверните роли сервера почтовых ящиков Exchange в каждом лесе в лесу единой системы обмена сообщениями Exchange, в котором вы хотите включить пользователей для Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="2053f-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="2053f-110">Подробнее об установке ролей Exchange Server можно найти в документации по Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2053f-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2053f-111">Если установлена единая система обмена сообщениями Exchange, она настроена на использование самозаверяющего сертификата.</span><span class="sxs-lookup"><span data-stu-id="2053f-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="2053f-112">Однако самозаверенный сертификат не включает Lync Server 2013 и Exchange UM для обеспечения доверительных отношений друг с другом, поэтому необходимо запросить отдельный сертификат в центре сертификации, которому доверяют оба сервера.</span><span class="sxs-lookup"><span data-stu-id="2053f-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="2053f-113">Если в разных лесах установлены Lync Server 2013 и Exchange UM, настройте каждый лес Exchange таким образом, чтобы он доверял лесу Lync Server 2013 и лесу Lync Server 2013, чтобы доверять каждому лесу Exchange.</span><span class="sxs-lookup"><span data-stu-id="2053f-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="2053f-114">Кроме того, настройте параметры Exchange UM для объектов пользователей в лесу Lync Server 2013, как правило, с помощью сценария или инструмента между лесами, например, диспетчером жизненного цикла удостоверений (ILM).</span><span class="sxs-lookup"><span data-stu-id="2053f-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="2053f-115">При необходимости установите консоль управления Exchange для управления серверами единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="2053f-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="2053f-116">Получите допустимые телефонные номера для голосового доступа к Outlook и автосекретарю.</span><span class="sxs-lookup"><span data-stu-id="2053f-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="2053f-117">Если вы используете более раннюю версию Exchange, чем Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1), координирует имена для абонентов SIP в UM-среде с помощью URI и для корпоративных абонентных групп.</span><span class="sxs-lookup"><span data-stu-id="2053f-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="2053f-118">Развертывание избыточных серверов единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="2053f-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2053f-119">Рекомендуется развертывать минимум два сервера, на которых выполняются службы Exchange UM для каждой абонентской группы Exchange UM, которую вы настроили для Организации.</span><span class="sxs-lookup"><span data-stu-id="2053f-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="2053f-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span><span class="sxs-lookup"><span data-stu-id="2053f-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="2053f-121">В случае сбоя сервера Lync Server 2013 можно настроить на переход на другой сервер.</span><span class="sxs-lookup"><span data-stu-id="2053f-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="2053f-122">В следующем примере конфигурации единой системы обмена сообщениями Exchange обеспечивают устойчивость.</span><span class="sxs-lookup"><span data-stu-id="2053f-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="2053f-123">**Пример 1. Устойчивость единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="2053f-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="2053f-124">![Пример 1 единой системы обмена сообщениями Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Пример 1 единой системы обмена сообщениями Exchange")</span><span class="sxs-lookup"><span data-stu-id="2053f-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="2053f-p105">В примере 1 серверы единой системы обмена сообщениями Exchange 1 и 2 включены в центре обработки данных в Таквила, серверы единой системы обмена сообщениями Exchange 3 и 4 включены в центре данных в Дублине. В случае сбоя в Таквила записи DNS A для серверов 1 и 2 следует настроить так, чтобы они указывали на серверы 3 и 4 соответственно. В случае сбоя сервера единой системы обмена сообщениями Exchange в Дублине записи DNS A для серверов 3 и 4 необходимо настроить так, чтобы они указывал на серверы 1 и 2 соответственно.</span><span class="sxs-lookup"><span data-stu-id="2053f-p105">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2053f-128">Для примера 1 вы также должны назначить один из следующих сертификатов на каждом сервере единой системы обмена сообщениями Exchange:</span><span class="sxs-lookup"><span data-stu-id="2053f-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2053f-129">Используйте сертификат с подстановочными знаками в альтернативном имени субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="2053f-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="2053f-130">Добавьте полное доменное имя каждого из четырех серверов единой системы обмена сообщениями Exchange в SAN.</span><span class="sxs-lookup"><span data-stu-id="2053f-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2053f-131">**Пример 2. Устойчивость единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="2053f-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="2053f-132">![Пример 2 единой системы обмена сообщениями Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Пример 2 единой системы обмена сообщениями Exchange")</span><span class="sxs-lookup"><span data-stu-id="2053f-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="2053f-p106">В примере 2 при обычных условиях работы серверов единой системы обмена сообщениями Exchange 1 и 2 включены в центре обработки данных в Таквила, серверы единой системы обмена сообщениями Exchange 3 и 4 включены в центре обработки данных Дублина. Все четыре сервера включены в абонентскую группу SIP URI Таквила. Но серверы 3 и 4 отключены. В случае сбоя единой системы обмена сообщениями Exchange в Таквила, например, серверы единой системы обмена сообщениями Exchange 1 и 2 должны быть отключены, а серверы единой системы обмена сообщениями Exchange 4 и 3 должны быть включены, чтобы трафик единой системы обмена сообщениями Exchange из Таквила направлялся на серверы в Дублине.</span><span class="sxs-lookup"><span data-stu-id="2053f-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="2053f-136">Дополнительные сведения о том, как включить или отключить единую систему обмена сообщениями в Exchange 2013, можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)разделе "интеграция Exchange 2013 UM с Lync Server".</span><span class="sxs-lookup"><span data-stu-id="2053f-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="2053f-137">Сведения о том, как включить или отключить единую систему обмена сообщениями на сервере Microsoft Exchange Server 2010, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="2053f-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="2053f-138">"Включить единую систему обмена сообщениями на [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)Exchange 2010".</span><span class="sxs-lookup"><span data-stu-id="2053f-138">"Enable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="2053f-139">"Отключить единую систему обмена сообщениями в [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)Exchange 2010".</span><span class="sxs-lookup"><span data-stu-id="2053f-139">"Disable Unified Messaging on Exchange 2010" at [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2053f-140">См. также</span><span class="sxs-lookup"><span data-stu-id="2053f-140">See Also</span></span>


[<span data-ttu-id="2053f-141">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2053f-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

