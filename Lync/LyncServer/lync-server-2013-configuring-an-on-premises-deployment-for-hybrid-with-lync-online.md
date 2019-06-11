---
title: Настройка локального развертывания для гибридной работы с Lync Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises deployment for hybrid with Lync Online
ms:assetid: c26addb0-2936-4eea-9071-3ab95825154b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205237(v=OCS.15)
ms:contentKeyID: 48185321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63620dc86a0249556d94491ec690989fa1dc835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-deployment-for-hybrid-with-lync-online"></a><span data-ttu-id="922db-102">Настройка локального развертывания для гибридной работы с Lync Online</span><span class="sxs-lookup"><span data-stu-id="922db-102">Configuring an on-premises deployment for hybrid with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="922db-103">_**Тема последнего изменения:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="922db-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="922db-104">Гибридное развертывание — это развертывание, в котором некоторые пользователи находятся в локальной среде, а некоторые пользователи находятся в сети, но все пользователи имеют общий доступ к тому же домену, например user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="922db-104">A hybrid deployment is a deployment in which some users are homed on-premises and some users are homed online, but all users share the same domain, such as user@contoso.com.</span></span> <span data-ttu-id="922db-105">В этом разделе рассказывается, как развернуть приложения, необходимые для гибридного развертывания, а затем настроить развертывание для ее включения.</span><span class="sxs-lookup"><span data-stu-id="922db-105">This section guides you through deploying the applications required for a hybrid deployment, and then configuring your deployment to enable it.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="922db-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="922db-106">In This Section</span></span>

  - [<span data-ttu-id="922db-107">Общие сведения о гибридной среде Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922db-107">Overview of the Lync Server 2013 hybrid environment</span></span>](lync-server-2013-overview-of-the-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="922db-108">Действия по подготовке и развертыванию гибридной среды Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922db-108">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>](lync-server-2013-steps-to-prepare-and-deploy-lync-server-hybrid-environment.md)

  - [<span data-ttu-id="922db-109">Настройка Федерации Lync Server 2013 с помощью Lync Online</span><span class="sxs-lookup"><span data-stu-id="922db-109">Configure federation of Lync Server 2013 with Lync Online</span></span>](lync-server-2013-configure-federation-with-lync-online.md)

  - [<span data-ttu-id="922db-110">Настройка Федерации для поставщика голосовой конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922db-110">Configure federation for an audio conferencing provider in Lync Server 2013</span></span>](lync-server-2013-configure-federation-for-an-audio-conferencing-provider.md)

  - [<span data-ttu-id="922db-111">Перемещение пользователей в Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922db-111">Move users to Lync Online in Lync Server 2013</span></span>](lync-server-2013-move-users-to-lync-online.md)

  - [<span data-ttu-id="922db-112">Администрирование пользователей в гибридном развертывании Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="922db-112">Administering users in a hybrid Lync Server 2013 deployment</span></span>](lync-server-2013-administering-users-in-a-hybrid-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

