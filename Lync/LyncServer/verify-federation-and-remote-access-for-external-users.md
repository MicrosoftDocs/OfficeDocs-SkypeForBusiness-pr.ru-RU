---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ad994eb7769dff067195520c2c6fde955910f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="16358-102">Проверка федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="16358-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16358-103">_**Тема последнего изменения:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="16358-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="16358-104">После перевода маршрута Федерации на граничный сервер Lync Server 2013 необходимо выполнить несколько функциональных тестов, чтобы убедиться, что она работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="16358-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="16358-105">Для проверки внешнего доступа пользователей следует включить все типы внешних пользователей, которые поддерживаются вашей организацией, в том числе любые из указанных ниже элементов.</span><span class="sxs-lookup"><span data-stu-id="16358-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="16358-106">Проверка подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="16358-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="16358-107">Пользователи, у которых есть хотя бы один федеративный домен, внутренний пользователь на Lync Server 2013 и пользователь на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="16358-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="16358-108">Протестируйте обмен мгновенными сообщениями, присутствие, звук и видео (A/V) и общий доступ к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="16358-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="16358-109">Пользователи всех общедоступных служб обмена мгновенными сообщениями, которые поддерживаются вашей организацией (и для которых была выполнена подготовка) взаимодействия с пользователем в Lync Server 2013 и пользователем на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="16358-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="16358-110">Убедитесь в том, что анонимные пользователи смогут присоединиться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="16358-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="16358-111">Пользователь, размещенный на Lync Server 2010 с удаленным доступом пользователей (вход в Lync Server 2010 из-за пределов интрасети, но не VPN) с пользователем на Lync Server 2013 и пользователем на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="16358-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="16358-112">Проверка обмена мгновенными сообщениями, сведений о присутствии, а/V и совместном использовании рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="16358-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="16358-113">Пользователь, размещенный на Lync Server 2013 с удаленным доступом пользователей (вход в Lync Server 2013 из-за пределов интрасети, но не VPN) с пользователем на Lync Server 2013 и пользователем на Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="16358-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="16358-114">Проверка обмена мгновенными сообщениями, сведений о присутствии, а/V и совместном использовании рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="16358-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

