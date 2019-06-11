---
title: 'Lync Server 2013: развертывание'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c7c7d6be1ee0e73ee87d71676dddfdcf7954d03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="31532-102">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31532-103">_**Тема последнего изменения:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="31532-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="31532-104">Развертывание коммуникационного программного обеспечения Lync Server 2013 включает в себя подготовку доменных служб Active Directory, развертывание серверов переднего плана и других основных компонентов основного приложения Lync Server 2013, а затем развертывание дополнительных ролей сервера и функций, которые возможно, вам потребуется ваша организация, например доступ внешних пользователей и голосовой голос.</span><span class="sxs-lookup"><span data-stu-id="31532-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="31532-105">В этой статье описаны три сценария развертывания Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="31532-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="31532-106">Новое развертывание Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="31532-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="31532-107">Новое развертывание Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="31532-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="31532-108">Новое развертывание Lync Server 2013 Standard Edition или Enterprise Edition в существующем развертывании Lync Server 2010 Standard Edition или Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="31532-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="31532-109">Сведения о том, как развертывать Lync Server 2013 в существующей среде Microsoft Office Communications Server 2007 или Microsoft Office Communications Server 2007 R2, можно найти в документации по [миграции](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="31532-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="31532-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="31532-110">In This Section</span></span>

  - [<span data-ttu-id="31532-111">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="31532-112">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="31532-113">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="31532-114">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="31532-115">Развертывание архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="31532-116">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="31532-117">Планирование и развертывание видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="31532-118">Развертывание сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="31532-119">Развертывание сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="31532-120">Развертывание клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="31532-121">Планирование и развертывание единого банка контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="31532-122">Управление проверкой подлинности между сервером (OAuth) и приложениями-партнерами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="31532-123">Обновление с ознакомительной версии Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="31532-124">Развертывание удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="31532-125">Развертывание поддержки мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="31532-126">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="31532-127">Конфигурация работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31532-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

