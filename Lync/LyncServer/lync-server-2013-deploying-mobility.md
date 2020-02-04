---
title: 'Lync Server 2013: развертывание поддержки мобильной работы'
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
ms.openlocfilehash: 9ea96278ad965538923b619e84ea059c0d6c7953
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mobility-in-lync-server-2013"></a><span data-ttu-id="b0157-102">Развертывание поддержки мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-102">Deploying mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0157-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b0157-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b0157-104">При развертывании функции мобильной связи Lync Server 2013 пользователи мобильных устройств могут использовать поддерживаемые мобильные устройства для работы с Lync, такие как обмен мгновенными сообщениями, присутствие и контакты.</span><span class="sxs-lookup"><span data-stu-id="b0157-104">When you deploy the Lync Server 2013 mobility feature, mobile users can use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span>

<span data-ttu-id="b0157-105">Дополнительные сведения о требованиях к развертыванию функции Mobility Service можно найти [в разделе Планирование мобильных устройств в Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="b0157-105">For details about requirements for deploying the mobility feature, see [Planning for mobility in Lync Server 2013](lync-server-2013-planning-for-mobility.md).</span></span>

<span data-ttu-id="b0157-106">Этот раздел поможет вам выполнить инструкции по развертыванию и проверке функций автоматического обнаружения и мобильных устройств.</span><span class="sxs-lookup"><span data-stu-id="b0157-106">This section guides you through the steps for deploying and verifying the mobility and automatic discovery features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b0157-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="b0157-107">In This Section</span></span>

  - [<span data-ttu-id="b0157-108">Создание DNS-записей для службы автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-108">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>](lync-server-2013-creating-dns-records-for-the-autodiscover-service.md)

  - [<span data-ttu-id="b0157-109">Изменение сертификатов для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-109">Modifying certificates for mobility in Lync Server 2013</span></span>](lync-server-2013-modifying-certificates-for-mobility.md)

  - [<span data-ttu-id="b0157-110">Настройка обратного прокси-сервера для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-110">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)

  - [<span data-ttu-id="b0157-111">Настройка службы автообнаружения в Lync Server 2013 для мобильной работы с гибридными развертываниями</span><span class="sxs-lookup"><span data-stu-id="b0157-111">Configuring Autodiscover in Lync Server 2013 for mobility with hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-mobility-with-hybrid-deployments.md)

  - [<span data-ttu-id="b0157-112">Проверка развертывания среды для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-112">Verifying your mobility deployment in Lync Server 2013</span></span>](lync-server-2013-verifying-your-mobility-deployment.md)

  - [<span data-ttu-id="b0157-113">Настройка для использования push-уведомлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-113">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)

  - [<span data-ttu-id="b0157-114">Настройка политики мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0157-114">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

