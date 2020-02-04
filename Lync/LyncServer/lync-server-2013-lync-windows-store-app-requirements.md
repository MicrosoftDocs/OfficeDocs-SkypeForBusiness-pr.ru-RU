---
title: 'Lync Server 2013: требования к приложению в магазине Lync из Магазина Windows'
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
ms.openlocfilehash: 9cc1ab2b397111cef1040592f29a11d55e5f1f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="a63a4-102">Требования к приложению Lync из Магазина Windows для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a63a4-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a63a4-103">_**Тема последнего изменения:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="a63a4-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="a63a4-104">Организации с локальным развертыванием сервера Lync Server должны соответствовать следующим требованиям для поддержки приложения Lync из Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="a63a4-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a63a4-105">Для Lync Server 2010 Запустите накопительное обновление для Lync Server 2010: Февраль 2012 (доступно по адресу <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; кбид = 2670352</A>) или более поздней версии на всех серверах.</span><span class="sxs-lookup"><span data-stu-id="a63a4-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="a63a4-106">Чтобы разрешить пользователям присоединяться к собраниям, запустите накопительное обновление для Lync Server 2010: Октябрь 2012 (доступно по адресу <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; кбид = 2737915</A>) на серверах.</span><span class="sxs-lookup"><span data-stu-id="a63a4-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="a63a4-107">Включите функцию автообнаружения, Lync Web App и службы веб-билета на сервере.</span><span class="sxs-lookup"><span data-stu-id="a63a4-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="a63a4-108">Включите проверку подлинности на сертификате на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="a63a4-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="a63a4-109">(Процесс регистрации пользователей на сервере переднего плана или в пуле переднего плана часто называется регистратором). Подробности можно найти [в разделе Создание параметров конфигурации регистратора в Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="a63a4-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="a63a4-110">Опубликуйте записи ресурсов псевдонимов DNS (CNAME) для службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="a63a4-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="a63a4-111">Больше не требуется, чтобы точка распространения списка отзыва сертификатов (CDP) для сертификатов, выданных в Lync Server, указывала на ресурс HTTP, а не на ресурс LDAP.</span><span class="sxs-lookup"><span data-stu-id="a63a4-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="a63a4-112">Тем не менее убедитесь, что на клиентских компьютерах установлены последние обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="a63a4-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="a63a4-113">Настройте прокси-серверы HTTP в корпоративной сети, чтобы разрешить трафик HTTP, связанный с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a63a4-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="a63a4-114">При необходимости добавьте исключения для служб автообнаружения, Lync Web App и веб-билета.</span><span class="sxs-lookup"><span data-stu-id="a63a4-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="a63a4-115">На клиентских компьютерах установите Windows 8,1 и последнюю версию приложения Lync из Магазина Windows, чтобы устранить проблему с входом, которая обычно происходит при использовании нескольких доменов (например, если URI SIP — **userA@domainZ.com** , но пограничный сервер — **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="a63a4-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="a63a4-116">Если ваша организация подписалась на Lync Online или Office 365 и вы используете свое собственное доменное имя, вы должны выполнить дополнительные действия, чтобы настроить сеть для автоопределения серверов Lync.</span><span class="sxs-lookup"><span data-stu-id="a63a4-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="a63a4-117">Требования к конфигурации сети одинаковы для приложения Lync из Магазина Windows и Lync на мобильных устройствах.</span><span class="sxs-lookup"><span data-stu-id="a63a4-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="a63a4-118">Следуйте инструкциям "Настройка сети" в вики-статье Office 365 "Настройка мобильных устройств Lync" [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span><span class="sxs-lookup"><span data-stu-id="a63a4-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a63a4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a63a4-119">See Also</span></span>


[<span data-ttu-id="a63a4-120">Развертывание приложения Lync из Магазина Windows в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a63a4-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

