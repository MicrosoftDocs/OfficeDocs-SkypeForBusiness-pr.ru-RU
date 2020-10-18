---
title: 'Lync Server 2013: развертывание доступа внешних пользователей'
description: 'Lync Server 2013: развертывание доступа внешних пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af41a169fe3a72e440e95cfa370a16117fb828a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573445"
---
# <a name="deploying-external-user-access-in-lync-server-2013"></a><span data-ttu-id="b5403-103">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-103">Deploying external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5403-104">_**Последнее изменение темы:** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="b5403-104">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="b5403-105">Развертывание пограничных компонентов для Microsoft Lync Server 2013 позволяет внешним пользователям, не вошедшим в внутреннюю сеть Организации, включая прошедшие проверку и анонимные удаленные пользователи, Федеративные партнеры (включая партнеров XMPP), мобильные клиенты и пользователей общедоступных служб обмена мгновенными сообщениями для общения с другими пользователями в Организации с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5403-105">Deploying edge components for Microsoft Lync Server 2013 makes it possible for external users who are not logged into your organization’s internal network, including authenticated and anonymous remote users, federated partners (including XMPP partners), mobile clients and users of public instant messaging (IM) services, to communicate with other users in your organization using Lync Server.</span></span> <span data-ttu-id="b5403-106">Процессы развертывания и настройки для Lync Server 2013 значительно отличаются от Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b5403-106">The deployment and configuration processes for Lync Server 2013 are not significantly different from Lync Server 2010.</span></span> <span data-ttu-id="b5403-107">Средства для установки и администрирования практически не отличаются от установки Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b5403-107">The tools for installation and administration are much the same as in Lync Server 2010.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b5403-108">&nbsp;Установка и Настройка пограничного сервера Microsoft Lync server 2013 может быть сложным процессом, который требует потенциального значительного объема планирования и координации с внутренними командами, включая систему безопасности, сети, брандмауэр, службу доменных имен (DNS), подсистему балансировки нагрузки и инфраструктуру открытых ключей (PKI).</span><span class="sxs-lookup"><span data-stu-id="b5403-108">Microsoft Lync Server 2013&nbsp;Edge Server installation and configuration can be a complex process requiring a potentially significant amount of planning and coordination with your internal teams, including – but not limited to – security, networking, firewall, domain name system (DNS), load balancer, and public key infrastructure (PKI) considerations.</span></span> <span data-ttu-id="b5403-109">Прежде чем приступать к развертыванию компонентов внешнего доступа, необходимо ознакомиться с документацией и процедурами планирования и использовать их.</span><span class="sxs-lookup"><span data-stu-id="b5403-109">It is strongly recommended that you review and use the planning process and documentation provided before deploying your external access components.</span></span> <span data-ttu-id="b5403-110">Это позволит оптимизировать ограничение числа и частоты нежелательных изменений и проблем при осуществлении процесса развертывания.</span><span class="sxs-lookup"><span data-stu-id="b5403-110">This will assist in limiting the number and frequency of undesired changes and problems as you proceed through the deployment process.</span></span> <span data-ttu-id="b5403-111">Сведения о планировании доступа внешних пользователей представлены в статье <A href="lync-server-2013-planning-for-external-user-access.md">Планирование доступа внешних пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b5403-111">For information on planning you external user access, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b5403-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="b5403-112">In This Section</span></span>

  - [<span data-ttu-id="b5403-113">Контрольный список развертывания для доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-113">Deployment checklist for external user access in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [<span data-ttu-id="b5403-114">Требования к системе для компонентов доступа внешних пользователей для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-114">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="b5403-115">Подготовка к установке серверов в сети периметра для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-115">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [<span data-ttu-id="b5403-116">Создание топологии пограничных серверов и директоров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-116">Building an edge and Director topology in Lync Server 2013</span></span>](lync-server-2013-building-an-edge-and-director-topology.md)

  - <span data-ttu-id="b5403-117">[Настройка директора в Lync Server 2013](lync-server-2013-setting-up-the-director.md) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="b5403-117">[Setting up the Director in Lync Server 2013](lync-server-2013-setting-up-the-director.md) (optional)</span></span>

  - [<span data-ttu-id="b5403-118">Настройка пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-118">Setting up Edge Servers in Lync Server 2013</span></span>](lync-server-2013-setting-up-edge-servers.md)

  - [<span data-ttu-id="b5403-119">Настройка обратных прокси-серверов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-119">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [<span data-ttu-id="b5403-120">Настройка поддержки доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-120">Configuring support for external user access in Lync Server 2013</span></span>](lync-server-2013-configuring-support-for-external-user-access.md)

  - [<span data-ttu-id="b5403-121">Руководство по подготовке к Lync-Skype подключениям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-121">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [<span data-ttu-id="b5403-122">Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-122">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="b5403-123">Развертывание мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-123">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="b5403-124">Проверка развертывания пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5403-124">Verifying your edge deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

