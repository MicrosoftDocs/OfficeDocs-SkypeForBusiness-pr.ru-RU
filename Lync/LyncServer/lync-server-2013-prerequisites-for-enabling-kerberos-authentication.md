---
title: 'Lync Server 2013: необходимые условия для включения проверки подлинности Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="31c85-102">Необходимые условия для включения проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31c85-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31c85-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="31c85-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="31c85-104">Перед включением проверки подлинности Kerberos убедитесь, что выполнены все необходимые требования к конфигурации и инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="31c85-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="31c85-105">Схема Active Directory расширена для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31c85-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="31c85-106">Подготовка леса Active Directory для Lync Server 2013 завершена.</span><span class="sxs-lookup"><span data-stu-id="31c85-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="31c85-107">Подготовка домена Active Directory для Lync Server 2013 завершена.</span><span class="sxs-lookup"><span data-stu-id="31c85-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="31c85-108">Хранилище Central Management успешно установлено и доступно.</span><span class="sxs-lookup"><span data-stu-id="31c85-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="31c85-109">Топология создана и опубликована с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="31c85-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="31c85-110">Серверы и роли, для которых требуются веб-службы, были определены и развернуты, в том числе серверы переднего плана, серверы Standard Edition и режиссеры.</span><span class="sxs-lookup"><span data-stu-id="31c85-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="31c85-111">Службы IIS настраиваются и развертываются с помощью рекомендованных служб ролей для поддержки веб-служб в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31c85-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="31c85-112">После выполнения необходимых условий вы должны будете создать одну или несколько учетных записей для веб-служб, которые будут использоваться для проверки подлинности Kerberos для развертывания.</span><span class="sxs-lookup"><span data-stu-id="31c85-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="31c85-113">Как минимум, вам нужно создать для каждого развертывания один из учетных записей проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="31c85-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="31c85-114">Однако вы можете создать учетную запись для каждого сайта, чтобы предоставить локальную проверку подлинности Kerberos на сайте.</span><span class="sxs-lookup"><span data-stu-id="31c85-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="31c85-115">Вы можете указать только одну учетную запись для проверки подлинности Kerberos для сайта.</span><span class="sxs-lookup"><span data-stu-id="31c85-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

