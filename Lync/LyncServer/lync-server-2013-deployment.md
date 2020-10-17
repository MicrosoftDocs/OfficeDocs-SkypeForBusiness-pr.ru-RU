---
title: 'Lync Server 2013: развертывание'
description: 'Lync Server 2013: развертывание.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment
ms:assetid: 83bd43ee-c1fe-4b38-bfa7-3eb382817bf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398664(v=OCS.15)
ms:contentKeyID: 48184687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750dabf9659327b19e80006d1bca05090f22fd43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555365"
---
# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="8c2c8-103">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-103">Deployment of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c2c8-104">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8c2c8-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8c2c8-105">Развертывание программного обеспечения для связи Lync Server 2013 включает подготовку доменных служб Active Directory, развертывание серверов переднего плана и других основных компонентов Lync Server 2013, а затем развертывание дополнительных ролей сервера и функций, которые могут потребоваться в Организации, например доступа внешних пользователей и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8c2c8-105">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="8c2c8-106">В этой документации описываются три сценария развертывания Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="8c2c8-106">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="8c2c8-107">Новое развертывание Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8c2c8-107">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="8c2c8-108">Новое развертывание Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8c2c8-108">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="8c2c8-109">Новое развертывание Lync Server 2013 Standard Edition или Enterprise Edition в существующем развертывании Lync Server 2010 Standard Edition или Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="8c2c8-109">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="8c2c8-110">Сведения о развертывании Lync Server 2013 в существующей среде Microsoft Office Communications Server 2007 или Microsoft Office Communications Server 2007 R2 можно найти в документации по [миграции](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="8c2c8-110">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8c2c8-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="8c2c8-111">In This Section</span></span>

  - [<span data-ttu-id="8c2c8-112">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-112">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="8c2c8-113">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-113">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="8c2c8-114">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-114">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="8c2c8-115">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-115">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="8c2c8-116">Развертывание архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-116">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="8c2c8-117">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-117">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="8c2c8-118">Планирование и развертывание видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-118">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="8c2c8-119">Развертывание сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-119">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="8c2c8-120">Развертывание сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-120">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="8c2c8-121">Развертывание клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-121">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="8c2c8-122">Планирование и развертывание единого хранилища контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-122">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="8c2c8-123">Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-123">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="8c2c8-124">Обновление ознакомительной версии Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-124">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="8c2c8-125">Развертывание удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-125">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="8c2c8-126">Развертывание мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-126">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="8c2c8-127">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-127">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="8c2c8-128">Конфигурация работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2c8-128">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

