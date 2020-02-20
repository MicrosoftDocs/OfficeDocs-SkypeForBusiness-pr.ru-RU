---
title: 'Lync Server 2013: развертывание мобильной работы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying mobility
ms:assetid: f41e6b25-d2cd-43fd-a17b-22cfda8bcd4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690055(v=OCS.15)
ms:contentKeyID: 48185805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b7449da84f2e810fe6ec4d2fd199d2daba56160
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="904e3-102">Развертывание мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-102">Deploying mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="904e3-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="904e3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="904e3-104">При развертывании функции мобильности Lync Server 2013 мобильные пользователи могут использовать поддерживаемые мобильные устройства для функций Lync, таких как обмен мгновенными сообщениями, присутствие и контакты.</span><span class="sxs-lookup"><span data-stu-id="904e3-104">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="904e3-105">Дополнительные сведения о требованиях к развертыванию функции Mobility Service можно найти [в статье Планирование мобильных устройств в Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="904e3-105">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="904e3-106">В этом разделе приведено описание процедуры развертывания и проверки работы функций мобильности и автоматического обнаружения.</span><span class="sxs-lookup"><span data-stu-id="904e3-106">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="904e3-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="904e3-107">In This Section</span></span>

  - [<span data-ttu-id="904e3-108">Создание DNS-записей для службы автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-108">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="904e3-109">Изменение сертификатов для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-109">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="904e3-110">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-110">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="904e3-111">Настройка службы автообнаружения в Lync Server 2013 для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="904e3-111">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="904e3-112">Проверка развертывания мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-112">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="904e3-113">Настройка для push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-113">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="904e3-114">Настройка политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904e3-114">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

