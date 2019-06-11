---
title: 'Lync Server 2013: Настройка поддержки федерации для клиента Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e3b1e7a325a078d4769116697f957815f02487
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="8ded6-102">Настройка поддержки федерации для клиента Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ded6-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ded6-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8ded6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8ded6-104">Вы можете предоставить доступ к службам связи для пользователей в вашей организации одним из указанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="8ded6-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="8ded6-105">Развертывание Lync Server 2013 в вашей организации (называемой *локальными службами*) и Настройка учетных записей пользователей Lync 2013 в Организации.</span><span class="sxs-lookup"><span data-stu-id="8ded6-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="8ded6-106">Настройка учетной записи клиента Microsoft Lync Online 2010 с поставщиком услуг размещения и Настройка учетных записей пользователей с помощью поставщика услуг размещения (называемых *веб-службами*).</span><span class="sxs-lookup"><span data-stu-id="8ded6-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="8ded6-107">Если вы развертываете Lync 2013 в своей организации, вы можете использовать федерацию с доменами одного или нескольких пользователей Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="8ded6-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="8ded6-108">Чтобы включить федерацию между пользователями локального развертывания Lync 2013 и пользователей в клиенте Lync Online 2010, необходимо настроить поддержку домена и пользователей клиента Lync Online.</span><span class="sxs-lookup"><span data-stu-id="8ded6-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ded6-109">В этой статье описаны действия, которые необходимо выполнить, чтобы настроить для Организации поддержку Федерации с помощью клиента Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="8ded6-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="8ded6-110">В этой документации не описаны процедуры для настройки клиента Lync Online 2010 для поддержки Федерации.</span><span class="sxs-lookup"><span data-stu-id="8ded6-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="8ded6-111">Подробные сведения о службах Lync Online можно найти в Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>Online по адресу.</span><span class="sxs-lookup"><span data-stu-id="8ded6-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ded6-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="8ded6-112">In This Section</span></span>

  - [<span data-ttu-id="8ded6-113">Необходимые условия для Федерации с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ded6-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="8ded6-114">Настройка поддержки федерации для домена Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ded6-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="8ded6-115">Настройка доступа пользователей для Федерации с помощью клиента Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ded6-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="8ded6-116">Проверка связи с клиентом Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ded6-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

