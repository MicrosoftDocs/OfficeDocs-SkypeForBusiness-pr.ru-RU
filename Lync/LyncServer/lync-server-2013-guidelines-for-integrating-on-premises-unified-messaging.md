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
ms.openlocfilehash: 71d6fc97a0b8c96758344dea12a0720d5ad049ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="24c38-102">Рекомендации по интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c38-102">Guidelines for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24c38-103">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="24c38-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="24c38-104">Ниже приведены рекомендации по развертыванию Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="24c38-104">The following are guidelines and best practices to consider when you deploy Enterprise Voice:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24c38-105">Единая система обмена сообщениями Exchange поддерживает IPv6 только в том случае, если вы также используете UCMA 4.</span><span class="sxs-lookup"><span data-stu-id="24c38-105">Exchange Unified Messaging (UM) supports IPv6 only if you are also using UCMA 4.</span></span>



</div>

  - <span data-ttu-id="24c38-106">Разверните сервер Lync Server 2013 Standard Edition или интерфейсный пул.</span><span class="sxs-lookup"><span data-stu-id="24c38-106">Deploy a Lync Server 2013 Standard Edition server or a Front End pool.</span></span> <span data-ttu-id="24c38-107">Дополнительные сведения об установке содержатся в документации по развертыванию [Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="24c38-107">For details about installation, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="24c38-108">Работайте вместе с администраторами Exchange, чтобы подтвердить, какие задачи каждый из вас будет выполнять для обеспечения успешной интеграции.</span><span class="sxs-lookup"><span data-stu-id="24c38-108">Work with Exchange administrators to confirm which tasks each of you will perform to assure a smooth and successful integration.</span></span>

  - <span data-ttu-id="24c38-109">Разверните роли сервера почтовых ящиков Exchange в каждом лесу единой системы обмена сообщениями Exchange, в котором необходимо включить поддержку единой системы обмена сообщениями Exchange для пользователей.</span><span class="sxs-lookup"><span data-stu-id="24c38-109">Deploy the Exchange Mailbox server roles in each Exchange Unified Messaging (UM) forest where you want to enable users for Exchange UM.</span></span> <span data-ttu-id="24c38-110">Дополнительные сведения об установке ролей Exchange Server можно найти в документации по Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24c38-110">For details about installing Exchange server roles, see the Microsoft Exchange Server 2013 documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24c38-111">Если установлена единая система обмена сообщениями Exchange, она настроена на использование самозаверяющего сертификата.</span><span class="sxs-lookup"><span data-stu-id="24c38-111">When Exchange Unified Messaging (UM) is installed, it is configured to use a self-signed certificate.</span></span><BR><span data-ttu-id="24c38-112">Однако самозаверяющий сертификат не включает Lync Server 2013 и единую систему обмена сообщениями Exchange для доверия друг другу, поэтому необходимо запросить отдельный сертификат от центра сертификации, который доверяет обоим серверам.</span><span class="sxs-lookup"><span data-stu-id="24c38-112">The self-signed certificate, however, does not enable Lync Server 2013 and Exchange UM to trust each other, which is why it is necessary to request a separate certificate from a certification authority that both servers trust.</span></span>

    
    </div>

  - <span data-ttu-id="24c38-113">Если Lync Server 2013 и Exchange единой системы обмена сообщениями установлены в разных лесах, настройте каждый лес Exchange так, чтобы он доверял лесу Lync Server 2013 и лесу Lync Server 2013, чтобы доверять каждому лесу Exchange.</span><span class="sxs-lookup"><span data-stu-id="24c38-113">If Lync Server 2013 and Exchange UM are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange forest.</span></span> <span data-ttu-id="24c38-114">Кроме того, установите параметры Exchange единой системы обмена сообщениями пользователей в объектах пользователей в лесу Lync Server 2013, как правило, с помощью сценария или средства перекрестного леса, например, диспетчера жизненного цикла удостоверений (ILM).</span><span class="sxs-lookup"><span data-stu-id="24c38-114">Also, set the users’ Exchange UM settings on the user objects in the Lync Server 2013 forest, typically by using a script or a cross-forest tool, such as Identity Lifecycle Manager (ILM).</span></span>

  - <span data-ttu-id="24c38-115">При необходимости установите консоль управления Exchange для управления серверами единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="24c38-115">If necessary, install the Exchange Management Console to manage your Unified Messaging servers.</span></span>

  - <span data-ttu-id="24c38-116">Получите допустимые телефонные номера для голосового доступа к Outlook и автосекретарю.</span><span class="sxs-lookup"><span data-stu-id="24c38-116">Obtain valid phone numbers for Outlook Voice Access and auto attendant.</span></span>

  - <span data-ttu-id="24c38-117">Если вы используете версию единой системы обмена сообщениями Exchange, предшествующую Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1), координирует имена для абонентских групп с универсальным кодом ресурса SIP для Exchange и корпоративной абонентской абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="24c38-117">If you are using a version of Exchange UM earlier than Microsoft Exchange Server 2010 Service Pack 1 (SP1), coordinate names for Exchange UM SIP URI dial plans and Enterprise Voice dial plans.</span></span>

<div>

## <a name="deploying-redundant-exchange-um-servers"></a><span data-ttu-id="24c38-118">Развертывание избыточных серверов единой системы обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="24c38-118">Deploying Redundant Exchange UM Servers</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24c38-119">Рекомендуется развертывать как минимум два сервера, на которых выполняются службы единой системы обмена сообщениями Exchange для каждой абонентской группы SIP единой системы обмена сообщениями Exchange, настроенной для Организации.</span><span class="sxs-lookup"><span data-stu-id="24c38-119">We recommend that you deploy a minimum of two servers on which Exchange UM services is running for each Exchange UM SIP URI dial plan that you configure for your organization.</span></span> <span data-ttu-id="24c38-120">Помимо дополнительной емкости развертывание избыточных серверов обеспечивает высокую доступность.</span><span class="sxs-lookup"><span data-stu-id="24c38-120">In addition to providing expanded capacity, deploying redundant servers provides high availability.</span></span> <span data-ttu-id="24c38-121">В случае отказа сервера Lync Server 2013 можно настроить на отработку отказа на другой сервер.</span><span class="sxs-lookup"><span data-stu-id="24c38-121">In the event of an server failure, Lync Server 2013 can be configured to fail over to another server.</span></span>



</div>

<span data-ttu-id="24c38-122">В следующем примере конфигурации единой системы обмена сообщениями Exchange обеспечивают устойчивость.</span><span class="sxs-lookup"><span data-stu-id="24c38-122">The following example configurations provide Exchange UM resiliency.</span></span>

<span data-ttu-id="24c38-123">**Пример 1. Устойчивость единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="24c38-123">**Example 1: Exchange UM Resiliency**</span></span>

<span data-ttu-id="24c38-124">![Пример 1 единой системы обмена сообщениями Exchange](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Пример 1 единой системы обмена сообщениями Exchange")</span><span class="sxs-lookup"><span data-stu-id="24c38-124">![Exchange UM Example 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM Example 1")</span></span>

<span data-ttu-id="24c38-p105">В примере 1 серверы единой системы обмена сообщениями Exchange 1 и 2 включены в центре обработки данных в Таквила, серверы единой системы обмена сообщениями Exchange 3 и 4 включены в центре данных в Дублине. В случае сбоя в Таквила записи DNS A для серверов 1 и 2 следует настроить так, чтобы они указывали на серверы 3 и 4 соответственно. В случае сбоя сервера единой системы обмена сообщениями Exchange в Дублине записи DNS A для серверов 3 и 4 необходимо настроить так, чтобы они указывал на серверы 1 и 2 соответственно.</span><span class="sxs-lookup"><span data-stu-id="24c38-p105">In Example 1, Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. In the event of an Exchange UM outage in Tukwila, the Domain Name System (DNS) A records for servers 1 and 2 should be configured to point to servers 3 and 4, respectively. In the event of an Exchange UM outage in Dublin, the DNS A records for servers 3 and 4 should be configured to point to servers 1 and 2, respectively.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24c38-128">Для примера 1 вы также должны назначить один из следующих сертификатов на каждом сервере единой системы обмена сообщениями Exchange:</span><span class="sxs-lookup"><span data-stu-id="24c38-128">For Example 1, you should also assign one of following certificate on each Exchange UM server:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="24c38-129">Используйте сертификат с подстановочными знаками в альтернативном имени субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="24c38-129">Use a certificate with a wildcard in the Subject Alternative Name (SAN).</span></span></P>
> <LI>
> <P><span data-ttu-id="24c38-130">Добавьте полное доменное имя каждого из четырех серверов единой системы обмена сообщениями Exchange в SAN.</span><span class="sxs-lookup"><span data-stu-id="24c38-130">Put the fully qualified domain name (FQDN) of each of the four Exchange UM servers in the SAN.</span></span></P></LI></UL>



</div>

<span data-ttu-id="24c38-131">**Пример 2. Устойчивость единой системы обмена сообщениями Exchange**</span><span class="sxs-lookup"><span data-stu-id="24c38-131">**Example 2: Exchange UM Resiliency**</span></span>

<span data-ttu-id="24c38-132">![Пример 2 единой системы обмена сообщениями Exchange](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Пример 2 единой системы обмена сообщениями Exchange")</span><span class="sxs-lookup"><span data-stu-id="24c38-132">![Exchange UM Example 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM Example 2")</span></span>

<span data-ttu-id="24c38-p106">В примере 2 при обычных условиях работы серверов единой системы обмена сообщениями Exchange 1 и 2 включены в центре обработки данных в Таквила, серверы единой системы обмена сообщениями Exchange 3 и 4 включены в центре обработки данных Дублина. Все четыре сервера включены в абонентскую группу SIP URI Таквила. Но серверы 3 и 4 отключены. В случае сбоя единой системы обмена сообщениями Exchange в Таквила, например, серверы единой системы обмена сообщениями Exchange 1 и 2 должны быть отключены, а серверы единой системы обмена сообщениями Exchange 4 и 3 должны быть включены, чтобы трафик единой системы обмена сообщениями Exchange из Таквила направлялся на серверы в Дублине.</span><span class="sxs-lookup"><span data-stu-id="24c38-p106">In Example 2, under ordinary operating conditions Exchange UM servers 1 and 2 are enabled in the Tukwila data center, and Exchange UM servers 3 and 4 are enabled in the Dublin data center. All four servers are included in the Tukwila users' SIP URI dial plan; however, servers 3 and 4 are disabled. In the event of an Exchange UM outage in Tukwila, for example, Exchange UM servers 1 and 2 should be disabled and Exchange UM servers 3 and 4 should be enabled so the Tukwila Exchange UM traffic will be routed to the servers in Dublin.</span></span>

<span data-ttu-id="24c38-136">Сведения о том, как включить или отключить единую систему обмена сообщениями в Exchange 2013, можно найти в [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)разделе "интеграция Exchange 2013 единой системы обмена сообщениями с Lync Server".</span><span class="sxs-lookup"><span data-stu-id="24c38-136">For details about how to enable or disable Unified Messaging on Exchange 2013, see “Integrate Exchange 2013 UM with Lync Server” at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

<span data-ttu-id="24c38-137">Сведения о том, как включить или отключить единую систему обмена сообщениями в Microsoft Exchange Server 2010, можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="24c38-137">For details about how to enable or disable Unified Messaging on Microsoft Exchange Server 2010, see:</span></span>

  - <span data-ttu-id="24c38-138">"Включить единую систему обмена сообщениями в [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418)Exchange 2010" по адресу.</span><span class="sxs-lookup"><span data-stu-id="24c38-138">"Enable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418).</span></span>

  - <span data-ttu-id="24c38-139">"Отключить единую систему обмена сообщениями в [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416)Exchange 2010" по адресу.</span><span class="sxs-lookup"><span data-stu-id="24c38-139">"Disable Unified Messaging on Exchange 2010" at [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24c38-140">См. также</span><span class="sxs-lookup"><span data-stu-id="24c38-140">See Also</span></span>


[<span data-ttu-id="24c38-141">Процесс развертывания для интеграции локальной единой системы обмена сообщениями и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c38-141">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

