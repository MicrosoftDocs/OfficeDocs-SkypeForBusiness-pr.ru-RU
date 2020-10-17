---
title: Проверка федерации и удаленного доступа для внешних пользователей
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5821cd8710b8493a29684d1b7ee695f5bf5c747
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508386"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="0ab61-102">Проверка федерации и удаленного доступа для внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="0ab61-102">Verify federation and remote access for external users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab61-103">_**Последнее изменение темы:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="0ab61-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="0ab61-104">После переноса маршрута Федерации на пограничный сервер Lync Server 2013 необходимо выполнить некоторые функциональные тесты, чтобы убедиться, что Федерация работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="0ab61-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="0ab61-105">В тесты для внешних пользователей должны включаться все типы пользователей, поддерживаемые в организации, включая любой из типов (или все типы) из указанных ниже.</span><span class="sxs-lookup"><span data-stu-id="0ab61-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="0ab61-106">Тест подключения внешних пользователей и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="0ab61-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="0ab61-107">Пользователи, по крайней мере, один федеративный домен, внутренний пользователь Lync Server 2013 и пользователь в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ab61-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="0ab61-108">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="0ab61-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="0ab61-109">Пользователи каждого общедоступного поставщика услуг обмена мгновенными сообщениями, поддерживаемого организацией (и для которого была выполнена подготовка), взаимодействуют с пользователем в Lync Server 2013 и пользователем в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ab61-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="0ab61-110">Проверьте, что анонимные пользователи могут присоединиться к конференциям.</span><span class="sxs-lookup"><span data-stu-id="0ab61-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="0ab61-111">Пользователь, размещенный на Lync Server 2010, использующий удаленный доступ пользователей (вход в Lync Server 2010 извне интрасети, но без VPN) с пользователем в Lync Server 2013 и пользователем Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ab61-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="0ab61-112">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="0ab61-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="0ab61-113">Пользователь, размещенный на Lync Server 2013, использующий удаленный доступ пользователей (вход в Lync Server 2013 извне интрасети, но без VPN) с пользователем в Lync Server 2013 и пользователем Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ab61-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="0ab61-114">Проверьте мгновенные сообщения, сведения о присутствии, аудио-видео и совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="0ab61-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

