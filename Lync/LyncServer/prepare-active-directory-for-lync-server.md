---
title: Подготовка Active Directory для Lync Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bface3b7e2515ed7ec8a8f3d78f21e867a6d6c00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="43b69-102">Подготовка Active Directory для Lync Server</span><span class="sxs-lookup"><span data-stu-id="43b69-102">Prepare Active Directory for Lync Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43b69-103">_**Тема последнего изменения:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="43b69-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="43b69-104">Перед развертыванием Lync Server 2013 в состоянии сосуществования в Lync Server 2010 необходимо выполнить некоторые дополнительные задачи Active Directory, чтобы настроить схему, лес и домен для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43b69-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="43b69-105">Расширения схемы добавляют классы и атрибуты Active Directory, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43b69-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="43b69-106">Дополнительные сведения можно найти в разделе [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="43b69-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="43b69-107">**Подготовка службы каталогов Active Directory для Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="43b69-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="43b69-108">На сервере переднего плана Lync Server 2013 запустите программу установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43b69-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="43b69-109">Выберите команду **подготовить Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="43b69-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="43b69-110">![Мастер развертывания Lync Server 2013, страница приветствия](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Мастер развертывания Lync Server 2013, страница приветствия")</span><span class="sxs-lookup"><span data-stu-id="43b69-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="43b69-111">Выполните действия 1 – 5.</span><span class="sxs-lookup"><span data-stu-id="43b69-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="43b69-112">![Мастер развертывания, Преаратион Active Directory](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Мастер развертывания, Преаратион Active Directory")</span><span class="sxs-lookup"><span data-stu-id="43b69-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

