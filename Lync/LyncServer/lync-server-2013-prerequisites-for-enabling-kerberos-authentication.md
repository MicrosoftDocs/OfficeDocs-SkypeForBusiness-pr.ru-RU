---
title: 'Lync Server 2013: необходимые условия для активации проверки подлинности Kerberos'
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
ms.openlocfilehash: e0be98112431b9e57486bb33e0eab84eada94e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506786"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="d9e8f-102">Необходимые условия для активации проверки подлинности Kerberos в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9e8f-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e8f-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d9e8f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d9e8f-104">Перед включением проверки подлинности Kerberos убедитесь, что выполнены все необходимые требования к конфигурации и инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="d9e8f-105">Схема Active Directory расширена для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="d9e8f-106">Подготовка леса Active Directory завершена для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="d9e8f-107">Подготовка домена Active Directory завершена для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="d9e8f-108">Централизованное хранилище управления успешно установлено и доступно.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="d9e8f-109">Топология была создана и опубликована с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="d9e8f-110">Серверы и роли, которым требуются веб-службы, были определены и развернуты, в том числе серверы переднего плана, серверы Standard Edition и директора.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="d9e8f-111">Службы IIS настроены и развернуты с помощью рекомендуемых служб ролей для поддержки веб-служб в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="d9e8f-112">После выполнения необходимых условий необходимо создать одну или несколько учетных записей для веб-служб, которые будут использоваться для проверки подлинности Kerberos в развертывании.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="d9e8f-113">Вам требуется создать хотя бы одну учетную запись для проверки подлинности Kerberos для каждого из развертываний.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="d9e8f-114">Однако вы можете создать учетную запись для каждого сайта, чтобы реализовать на этом сайте локальную проверку подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="d9e8f-115">Для отдельного сайта можно указать только одну учетную запись для проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d9e8f-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

