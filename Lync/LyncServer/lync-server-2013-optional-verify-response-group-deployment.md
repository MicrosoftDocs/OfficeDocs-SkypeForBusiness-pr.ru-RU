---
title: 'Lync Server 2013: (необязательно) Проверка развертывания группы ответа'
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
ms.openlocfilehash: 065a48aedf1b093358193d0c8afbd12b44653025
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="5ca34-102">Необязательно Проверка развертывания группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ca34-102">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ca34-103">_**Тема последнего изменения:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="5ca34-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="5ca34-104">После настройки группы ответа необходимо проверить конфигурацию, чтобы убедиться, что группы ответа работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="5ca34-104">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="5ca34-105">Необходимо проверить работу, как минимум, следующих сценариев, используя следующие типы пользователей:</span><span class="sxs-lookup"><span data-stu-id="5ca34-105">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="5ca34-106">**Пользователи**</span><span class="sxs-lookup"><span data-stu-id="5ca34-106">**Users**</span></span>

  - <span data-ttu-id="5ca34-107">Пользователь, который размещен на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ca34-107">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="5ca34-108">Внешний пользователь, использующий телефонную сеть общего пользования (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="5ca34-108">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="5ca34-109">Агент, размещенный на Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ca34-109">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="5ca34-110">**Сценарии**</span><span class="sxs-lookup"><span data-stu-id="5ca34-110">**Scenarios**</span></span>

  - <span data-ttu-id="5ca34-111">Пользователь Lync Server 2013 вызывает группу ответа.</span><span class="sxs-lookup"><span data-stu-id="5ca34-111">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="5ca34-112">Внешний пользователь вызывает группу ответа.</span><span class="sxs-lookup"><span data-stu-id="5ca34-112">The external user calls the response group.</span></span>

  - <span data-ttu-id="5ca34-113">Пользователь вызывает группу ответа в то время, как агент обрабатывает другой вызов и переходит в очередь.</span><span class="sxs-lookup"><span data-stu-id="5ca34-113">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

