---
title: 'Lync Server 2013: (необязательно) Проверка развертывания группы ответа'
description: 'Lync Server 2013: (необязательно) Проверка развертывания группы ответа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cfe15026bc1fcfbe10b593987d2717fc0dc8104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565715"
---
# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="b6aa2-103">Необязательно Проверка развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6aa2-103">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6aa2-104">_**Последнее изменение темы:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="b6aa2-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="b6aa2-105">После настройки группы ответа необходимо проверить конфигурацию, чтобы убедиться, что группы ответа работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-105">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="b6aa2-106">Необходимо проверить работу, как минимум, следующих сценариев, используя следующие типы пользователей:</span><span class="sxs-lookup"><span data-stu-id="b6aa2-106">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="b6aa2-107">**пользователи**;</span><span class="sxs-lookup"><span data-stu-id="b6aa2-107">**Users**</span></span>

  - <span data-ttu-id="b6aa2-108">Пользователь, размещенный в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6aa2-108">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="b6aa2-109">Внешний пользователь, использующий телефонную сеть общего пользования (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="b6aa2-109">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="b6aa2-110">Агент, размещенный на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6aa2-110">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="b6aa2-111">**Scenarios**</span><span class="sxs-lookup"><span data-stu-id="b6aa2-111">**Scenarios**</span></span>

  - <span data-ttu-id="b6aa2-112">Пользователь Lync Server 2013 вызывает группу ответа.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-112">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="b6aa2-113">Внешний пользователь вызывает группу ответа.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-113">The external user calls the response group.</span></span>

  - <span data-ttu-id="b6aa2-114">Пользователь вызывает группу ответа в то время, как агент обрабатывает другой вызов и переходит в очередь.</span><span class="sxs-lookup"><span data-stu-id="b6aa2-114">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

