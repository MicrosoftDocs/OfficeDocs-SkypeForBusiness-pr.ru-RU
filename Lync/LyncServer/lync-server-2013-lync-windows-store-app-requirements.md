---
title: 'Lync Server 2013: требования к приложению Магазина Windows для Lync'
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
ms.openlocfilehash: 84e4c7c9f4fb07d737b4f384faa5559a69c2392c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="a7197-102">Требования к приложению для Магазина Windows Lync для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7197-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7197-103">_**Последнее изменение темы:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="a7197-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="a7197-104">Организации, использующие локальное развертывание Lync Server, должны удовлетворять следующим требованиям для поддержки приложения Lync Windows в магазине.</span><span class="sxs-lookup"><span data-stu-id="a7197-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7197-105">Для Lync Server 2010 запустите накопительный пакет обновления для Lync Server 2010: Февраль 2012 (доступен по адресу <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) или более поздней версии на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="a7197-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="a7197-106">Чтобы разрешить пользователям присоединяться к собраниям, запустите накопительное обновление для Lync Server 2010: Октябрь 2012 (доступно по адресу <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) на серверах.</span><span class="sxs-lookup"><span data-stu-id="a7197-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="a7197-107">Включите службу автообнаружения, Lync Web App и службы веб-билетов на сервере.</span><span class="sxs-lookup"><span data-stu-id="a7197-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="a7197-108">Включите проверку подлинности на сертификате на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="a7197-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="a7197-109">(Процесс регистрации пользователя на сервере переднего плана или интерфейсном пуле часто называется регистратором). Дополнительные сведения: [CREATE регистратор параметры конфигурации в Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a7197-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="a7197-110">Опубликуйте записи ресурса псевдонима DNS (CNAME) для службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a7197-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="a7197-111">Больше не требуется гарантировать, что точка распространения списка отзыва сертификатов (CDP) для сертификатов, выданных серверу Lync Server, указывает на ресурс HTTP, а не на ресурс LDAP.</span><span class="sxs-lookup"><span data-stu-id="a7197-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="a7197-112">Тем не менее, убедитесь, что на клиентских компьютерах установлены последние обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="a7197-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="a7197-113">Настройте прокси-серверы HTTP на предприятии, чтобы разрешить HTTP-трафик, связанный с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a7197-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="a7197-114">При необходимости добавьте исключения для служб автообнаружения, Lync Web App и веб-билетов.</span><span class="sxs-lookup"><span data-stu-id="a7197-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="a7197-115">На клиентских компьютерах установите Windows 8,1 и последнюю версию Lync Windows App Store, чтобы устранить проблему при входе, которая обычно возникает при использовании нескольких доменов (например, когда URI SIP является **userA@domainZ.com** , а пограничный сервер — **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="a7197-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="a7197-116">Если ваша организация подписывается на Lync Online или Office 365 и вы используете свое собственное доменное имя, необходимо выполнить некоторые дополнительные действия по настройке сети для автоматического обнаружения серверов Lync.</span><span class="sxs-lookup"><span data-stu-id="a7197-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="a7197-117">Требования к конфигурации сети одинаковы для приложений Lync Windows и Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="a7197-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="a7197-118">Следуйте инструкциям "Настройка сети" в вики-статье Office 365 "Настройка мобильных устройств Lync" [https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822).</span><span class="sxs-lookup"><span data-stu-id="a7197-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [https://go.microsoft.com/fwlink/?LinkId=271822](https://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a7197-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a7197-119">See Also</span></span>


[<span data-ttu-id="a7197-120">Развертывание приложения Lync Windows для магазина в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7197-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

