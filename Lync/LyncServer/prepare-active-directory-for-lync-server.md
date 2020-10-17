---
title: Подготовка Active Directory для Lync Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server
ms:assetid: 54cd597d-0c2d-479c-8c52-1babc53f71dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688059(v=OCS.15)
ms:contentKeyID: 49733653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604d44eba22caf38bc55c788d67efb120a7abc3b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509306"
---
# <a name="prepare-active-directory-for-lync-server"></a><span data-ttu-id="fe4fb-102">Подготовка Active Directory для Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe4fb-102">Prepare Active Directory for Lync Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe4fb-103">_**Последнее изменение темы:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="fe4fb-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="fe4fb-104">Перед развертыванием Lync Server 2013 в режиме сосуществования с Lync Server 2010 необходимо выполнить некоторые дополнительные задачи Active Directory, чтобы настроить схему, лес и домен для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe4fb-104">Prior to deploying Lync Server 2013 in a coexistence state with Lync Server 2010, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="fe4fb-105">Расширения схемы добавляют классы и атрибуты Active Directory, необходимые для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe4fb-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server 2013.</span></span> <span data-ttu-id="fe4fb-106">Для получения дополнительных сведений ознакомьтесь с разделом [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="fe4fb-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="fe4fb-107">**Подготовка Active Directory для Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="fe4fb-107">**To prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="fe4fb-108">На сервере переднего плана Lync Server 2013 запустите программу установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe4fb-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="fe4fb-109">Выберите пункт **Подготовить Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="fe4fb-109">Select **Prepare Active Directory**.</span></span>
    
    <span data-ttu-id="fe4fb-110">![Мастер развертывания Lync Server 2013, страница приветствия](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Мастер развертывания Lync Server 2013, страница приветствия")</span><span class="sxs-lookup"><span data-stu-id="fe4fb-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="fe4fb-111">Выполните действия 1–5.</span><span class="sxs-lookup"><span data-stu-id="fe4fb-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="fe4fb-112">![Мастер развертывания, Преаратион Active Directory](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Мастер развертывания, Преаратион Active Directory")</span><span class="sxs-lookup"><span data-stu-id="fe4fb-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

