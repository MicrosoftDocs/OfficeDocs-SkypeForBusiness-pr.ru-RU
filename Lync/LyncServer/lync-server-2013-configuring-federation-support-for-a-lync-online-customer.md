---
title: 'Lync Server 2013: Настройка поддержки федерации для клиента Lync Online'
description: 'Lync Server 2013: Настройка поддержки федерации для клиента Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b5e7995e686a9492b3a4be98a92b848716cacf9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548425"
---
# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="a40ee-103">Настройка поддержки федерации для клиента Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a40ee-103">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a40ee-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a40ee-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a40ee-105">Вы можете предоставить службы мгновенных сообщений пользователям свой организации любым из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a40ee-105">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="a40ee-106">Развертывание Lync Server 2013 в Организации (называемой *локальными службами*) и Настройка учетных записей пользователей Lync 2013 в Организации.</span><span class="sxs-lookup"><span data-stu-id="a40ee-106">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="a40ee-107">Настройка учетной записи клиента Microsoft Lync Online 2010 с поставщиком услуг хостинга и Настройка учетных записей пользователей с помощью поставщика услуг хостинга (известного как *веб-службы*).</span><span class="sxs-lookup"><span data-stu-id="a40ee-107">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="a40ee-108">При развертывании Lync 2013 в Организации можно использовать федерацию с доменами одного или нескольких клиентов Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="a40ee-108">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="a40ee-109">Чтобы включить федерацию между пользователями локального развертывания Lync 2013 и пользователями клиента Lync Online 2010, необходимо настроить поддержку домена и пользователей клиента Lync Online.</span><span class="sxs-lookup"><span data-stu-id="a40ee-109">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a40ee-110">В этой документации описываются только процедуры настройки организации для поддержки Федерации с клиентом Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="a40ee-110">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="a40ee-111">В этой документации не описываются процедуры настройки клиента Lync Online 2010 для поддержки Федерации.</span><span class="sxs-lookup"><span data-stu-id="a40ee-111">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="a40ee-112">Подробнее о службах Lync Online можно узнать в статье Lync Online по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A> .</span><span class="sxs-lookup"><span data-stu-id="a40ee-112">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a40ee-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="a40ee-113">In This Section</span></span>

  - [<span data-ttu-id="a40ee-114">Необходимые условия для Федерации с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a40ee-114">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="a40ee-115">Настройка поддержки федерации для домена Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a40ee-115">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="a40ee-116">Настройка доступа пользователей для Федерации с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a40ee-116">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="a40ee-117">Проверка связи с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a40ee-117">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

