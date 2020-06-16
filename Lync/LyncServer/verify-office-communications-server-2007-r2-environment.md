---
title: Проверка среды Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a7ba7e51e6dd1f6e42aeddfbbbd4ce7581d3fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="f5646-102">Проверка среды Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f5646-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5646-103">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f5646-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f5646-104">Перед развертыванием Lync Server 2013 в режиме сосуществования с Office Communications Server 2007 R2 необходимо убедиться, что службы Office Communications Server 2007 R2 настроены и запущены.</span><span class="sxs-lookup"><span data-stu-id="f5646-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="f5646-105">**Проверка того, что пул запущен с помощью средства администрирования Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="f5646-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="f5646-106">Откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f5646-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="f5646-107">Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="f5646-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="f5646-108">Убедитесь, что службы запущены на сервере Standard Edition или в корпоративном пуле.</span><span class="sxs-lookup"><span data-stu-id="f5646-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="f5646-109">![Консоль администрирования Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администрирования Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="f5646-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="f5646-110">**Обзор пользователей, настроенных для Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="f5646-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="f5646-111">Откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f5646-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="f5646-112">Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.</span><span class="sxs-lookup"><span data-stu-id="f5646-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="f5646-113">Щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f5646-113">Click **Users**.</span></span>

4.  <span data-ttu-id="f5646-114">Проверьте список пользователей Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f5646-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="f5646-115">![Список пользователей в средстве администрирования OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Список пользователей в средстве администрирования OCS")</span><span class="sxs-lookup"><span data-stu-id="f5646-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="f5646-116">**Проверка устаревшей конфигурации федеративного партнера XMPP**</span><span class="sxs-lookup"><span data-stu-id="f5646-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="f5646-117">Из устаревшего сервера XMPP перейдите к \\ апплету администрирование служб.</span><span class="sxs-lookup"><span data-stu-id="f5646-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="f5646-118">Убедитесь, что служба шлюза XMPP Office Communications Server запущена.</span><span class="sxs-lookup"><span data-stu-id="f5646-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="f5646-119">![Служба шлюза XMPP для Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза XMPP для Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="f5646-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

