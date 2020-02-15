---
title: Подготовка Active Directory для Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prepare Active Directory for Lync Server 2013
ms:assetid: d0978eb6-d842-40e9-b475-73197cc34e08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205265(v=OCS.15)
ms:contentKeyID: 48185413
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725bb861cdabff370d8a15b15d3dc8d511cbe901
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prepare-active-directory-for-lync-server-2013"></a><span data-ttu-id="86e54-102">Подготовка Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86e54-102">Prepare Active Directory for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86e54-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="86e54-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="86e54-104">Перед развертыванием Lync Server 2013 в режиме сосуществования с Office Communications Server 2007 R2 необходимо выполнить некоторые дополнительные задачи Active Directory, чтобы настроить схему, лес и домен для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86e54-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you must perform some additional Active Directory tasks to configure the schema, forest, and domain for Lync Server 2013.</span></span> <span data-ttu-id="86e54-105">Расширения схемы добавляют классы и атрибуты Active Directory, необходимые серверу Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86e54-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span> <span data-ttu-id="86e54-106">Для получения дополнительных сведений ознакомьтесь с разделом [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="86e54-106">For additional information, see the topic [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

<span data-ttu-id="86e54-107">**Подготовка Active Directory для Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="86e54-107">**Prepare Active Directory for Lync Server 2013**</span></span>

1.  <span data-ttu-id="86e54-108">На сервере переднего плана Lync Server 2013 запустите программу установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86e54-108">On the Lync Server 2013 Front End Server, run Lync Server 2013 Setup.</span></span>

2.  <span data-ttu-id="86e54-109">Выберите **Prepare Active Directory** (Подготовка Active Directory)</span><span class="sxs-lookup"><span data-stu-id="86e54-109">Select **Prepare Active Directory**</span></span>
    
    <span data-ttu-id="86e54-110">![Мастер развертывания Lync Server 2013, страница приветствия](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Мастер развертывания Lync Server 2013, страница приветствия")</span><span class="sxs-lookup"><span data-stu-id="86e54-110">![Lync Server 2013 Deployment Wizard, Welcome page](images/JJ205265.5f88ae18-9c3c-42ea-a91a-836ecf5d515f(OCS.15).jpg "Lync Server 2013 Deployment Wizard, Welcome page")</span></span>

3.  <span data-ttu-id="86e54-111">Выполните действия 1–5.</span><span class="sxs-lookup"><span data-stu-id="86e54-111">Complete steps 1 through 5.</span></span>
    
    <span data-ttu-id="86e54-112">![Мастер развертывания, Преаратион Active Directory](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Мастер развертывания, Преаратион Active Directory")</span><span class="sxs-lookup"><span data-stu-id="86e54-112">![Deployment Wizard, Active Directory Prearation](images/JJ205265.eddd9e94-fa70-453f-8810-b99a2bf0844a(OCS.15).jpg "Deployment Wizard, Active Directory Prearation")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

