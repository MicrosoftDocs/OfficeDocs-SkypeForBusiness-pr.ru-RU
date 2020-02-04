---
title: 'Lync Server 2013: необходимые условия для включения проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb722f69dcd975d7f346b6e4db8f8ff140f4ac3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="3d0a0-102">Необходимые условия для включения проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d0a0-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d0a0-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3d0a0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3d0a0-104">Перед включением проверки подлинности Kerberos убедитесь, что выполнены все необходимые требования к конфигурации и инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="3d0a0-105">Схема Active Directory расширена для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="3d0a0-106">Подготовка леса Active Directory для Lync Server 2013 завершена.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="3d0a0-107">Подготовка домена Active Directory для Lync Server 2013 завершена.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="3d0a0-108">Хранилище Central Management успешно установлено и доступно.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="3d0a0-109">Топология создана и опубликована с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="3d0a0-110">Серверы и роли, для которых требуются веб-службы, были определены и развернуты, в том числе серверы переднего плана, серверы Standard Edition и режиссеры.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="3d0a0-111">Службы IIS настраиваются и развертываются с помощью рекомендованных служб ролей для поддержки веб-служб в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="3d0a0-112">После выполнения необходимых условий вы должны будете создать одну или несколько учетных записей для веб-служб, которые будут использоваться для проверки подлинности Kerberos для развертывания.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="3d0a0-113">Как минимум, вам нужно создать для каждого развертывания один из учетных записей проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="3d0a0-114">Однако вы можете создать учетную запись для каждого сайта, чтобы предоставить локальную проверку подлинности Kerberos на сайте.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="3d0a0-115">Вы можете указать только одну учетную запись для проверки подлинности Kerberos для сайта.</span><span class="sxs-lookup"><span data-stu-id="3d0a0-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

