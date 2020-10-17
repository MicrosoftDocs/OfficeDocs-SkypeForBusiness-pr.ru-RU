---
title: 'Lync Server 2013: требования к приложению Магазина Windows для Lync'
description: 'Lync Server 2013: требования к приложению для Магазина Windows в Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17e8705a55625bcf0ad099ead1000a82c994d867
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566505"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="a9204-103">Требования к приложению для Магазина Windows Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9204-103">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9204-104">_**Последнее изменение темы:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="a9204-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="a9204-105">Организации, использующие локальное развертывание Lync Server, должны удовлетворять следующим требованиям для поддержки приложения Lync Windows в магазине.</span><span class="sxs-lookup"><span data-stu-id="a9204-105">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9204-106">Для Lync Server 2010 запустите накопительный пакет обновления для Lync Server 2010: Февраль 2012 (доступен по адресу <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) или более поздней версии на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="a9204-106">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="a9204-107">Чтобы разрешить пользователям присоединяться к собраниям, запустите накопительное обновление для Lync Server 2010: Октябрь 2012 (доступно по адресу <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) на серверах.</span><span class="sxs-lookup"><span data-stu-id="a9204-107">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="a9204-108">Включите службу автообнаружения, Lync Web App и службы веб-билетов на сервере.</span><span class="sxs-lookup"><span data-stu-id="a9204-108">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="a9204-109">Включите проверку подлинности на сертификате на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="a9204-109">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="a9204-110">(Процесс регистрации пользователя на сервере переднего плана или интерфейсном пуле часто называется регистратором). Дополнительные сведения: [CREATE регистратор параметры конфигурации в Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a9204-110">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="a9204-111">Опубликуйте записи ресурса псевдонима DNS (CNAME) для службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a9204-111">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="a9204-112">Больше не требуется гарантировать, что точка распространения списка отзыва сертификатов (CDP) для сертификатов, выданных серверу Lync Server, указывает на ресурс HTTP, а не на ресурс LDAP.</span><span class="sxs-lookup"><span data-stu-id="a9204-112">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="a9204-113">Тем не менее, убедитесь, что на клиентских компьютерах установлены последние обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="a9204-113">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="a9204-114">Настройте прокси-серверы HTTP на предприятии, чтобы разрешить HTTP-трафик, связанный с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9204-114">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="a9204-115">При необходимости добавьте исключения для служб автообнаружения, Lync Web App и веб-билетов.</span><span class="sxs-lookup"><span data-stu-id="a9204-115">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="a9204-116">На клиентских компьютерах установите Windows 8,1 и последнюю версию Lync Windows App Store, чтобы устранить проблему при входе, которая обычно возникает при использовании нескольких доменов (например, когда URI SIP является **userA@domainZ.com** , а пограничный сервер — **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="a9204-116">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="a9204-117">Если ваша организация подписывается на Lync Online или Microsoft 365 и вы используете собственное доменное имя, необходимо выполнить дополнительные действия по настройке сети для автоматического обнаружения серверов Lync.</span><span class="sxs-lookup"><span data-stu-id="a9204-117">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="a9204-118">Требования к конфигурации сети одинаковы для приложений Lync Windows и Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="a9204-118">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a9204-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a9204-119">See Also</span></span>


[<span data-ttu-id="a9204-120">Развертывание приложения Lync Windows для магазина в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9204-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
