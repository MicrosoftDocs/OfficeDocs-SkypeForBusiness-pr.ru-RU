---
title: 'Lync Server 2013: (необязательно) Проверка развертывания группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b031ab8fdaac5249146faedafcc23517040b3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="ab1ac-102">Необязательно Проверка развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab1ac-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab1ac-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ab1ac-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ab1ac-104">После настройки группы ответа необходимо проверить конфигурацию, чтобы убедиться, что группы ответа работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="ab1ac-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="ab1ac-105">Необходимо проверить работу, как минимум, следующих сценариев, используя следующие типы пользователей:</span><span class="sxs-lookup"><span data-stu-id="ab1ac-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="ab1ac-106">**Пользователи**</span><span class="sxs-lookup"><span data-stu-id="ab1ac-106">**Users**</span></span>

  - <span data-ttu-id="ab1ac-107">Пользователь, который размещен на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab1ac-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="ab1ac-108">Внешний пользователь, использующий телефонную сеть общего пользования (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="ab1ac-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="ab1ac-109">Агент, размещенный на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab1ac-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="ab1ac-110">**Сценарии**</span><span class="sxs-lookup"><span data-stu-id="ab1ac-110">**Scenarios**</span></span>

  - <span data-ttu-id="ab1ac-111">Пользователь Lync Server 2013 вызывает группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ab1ac-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="ab1ac-112">Внешний пользователь вызывает группу ответа.</span><span class="sxs-lookup"><span data-stu-id="ab1ac-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="ab1ac-113">Пользователь вызывает группу ответа в то время, как агент обрабатывает другой вызов и переходит в очередь.</span><span class="sxs-lookup"><span data-stu-id="ab1ac-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

