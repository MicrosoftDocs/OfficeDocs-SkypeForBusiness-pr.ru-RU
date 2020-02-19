---
title: 'Lync Server 2013: развертывание'
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
ms.openlocfilehash: 1ac492e29cfb349d6cce4d3ff211d879414c2e6f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-of-lync-server-2013"></a><span data-ttu-id="44e12-102">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-102">Deployment of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e12-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="44e12-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="44e12-104">Развертывание программного обеспечения Lync Server 2013 Communications включает подготовку доменных служб Active Directory, развертывание серверов переднего плана и других основных компонентов Lync Server 2013, а затем развертывание дополнительных ролей сервера и компонентов, которые в Организации может потребоваться, например, доступ к внешним пользователям и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="44e12-104">Deployment of Lync Server 2013 communications software includes preparing Active Directory Domain Services, deploying the Front End Servers and other core Lync Server 2013 internal components, and then deploying any additional server roles and features that your organization may require, such as external user access and Enterprise Voice.</span></span>

<span data-ttu-id="44e12-105">В этой документации описываются три сценария развертывания Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="44e12-105">This documentation describes three scenarios for deploying Lync Server 2013:</span></span>

  - <span data-ttu-id="44e12-106">Новое развертывание Lync Server 2013, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="44e12-106">New Deployment of Lync Server 2013, Enterprise Edition</span></span>

  - <span data-ttu-id="44e12-107">Новое развертывание Lync Server 2013, Standard Edition</span><span class="sxs-lookup"><span data-stu-id="44e12-107">New Deployment of Lync Server 2013, Standard Edition</span></span>

  - <span data-ttu-id="44e12-108">Новое развертывание Lync Server 2013 Standard Edition или Enterprise Edition в существующем развертывании Lync Server 2010 Standard Edition или Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="44e12-108">New Deployment of Lync Server 2013 Standard Edition or Enterprise Edition into an existing Lync Server 2010 Standard Edition or Enterprise Edition deployment</span></span>

<span data-ttu-id="44e12-109">Сведения о развертывании Lync Server 2013 в существующей среде Microsoft Office Communications Server 2007 или Microsoft Office Communications Server 2007 R2 можно найти в документации по [миграции](migration.md) .</span><span class="sxs-lookup"><span data-stu-id="44e12-109">For information about deploying Lync Server 2013 in an existing Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2 environment, see the [Migration](migration.md) documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44e12-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="44e12-110">In This Section</span></span>

  - [<span data-ttu-id="44e12-111">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-111">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

  - [<span data-ttu-id="44e12-112">Развертывание доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-112">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

  - [<span data-ttu-id="44e12-113">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-113">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)

  - [<span data-ttu-id="44e12-114">Развертывание мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-114">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)

  - [<span data-ttu-id="44e12-115">Развертывание архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-115">Deploying Archiving in Lync Server 2013</span></span>](lync-server-2013-deploying-archiving.md)

  - [<span data-ttu-id="44e12-116">Настройка конференц-связи с телефонным подключением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-116">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

  - [<span data-ttu-id="44e12-117">Планирование и развертывание видео в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-117">Planning and deploying video in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-video.md)

  - [<span data-ttu-id="44e12-118">Развертывание сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-118">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)

  - [<span data-ttu-id="44e12-119">Развертывание сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-119">Deploying Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deploying-persistent-chat-server.md)

  - [<span data-ttu-id="44e12-120">Развертывание клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-120">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)

  - [<span data-ttu-id="44e12-121">Планирование и развертывание единого хранилища контактов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-121">Planning and deploying unified contact store in Lync Server 2013</span></span>](lync-server-2013-planning-and-deploying-unified-contact-store.md)

  - [<span data-ttu-id="44e12-122">Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-122">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

  - [<span data-ttu-id="44e12-123">Обновление ознакомительной версии Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-123">Updating from the evaluation version of Lync Server 2013</span></span>](lync-server-2013-updating-from-the-evaluation-version.md)

  - [<span data-ttu-id="44e12-124">Развертывание удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-124">Deploying remote call control in Lync Server 2013</span></span>](lync-server-2013-deploying-remote-call-control.md)

  - [<span data-ttu-id="44e12-125">Развертывание мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-125">Deploying mobility in Lync Server 2013</span></span>](lync-server-2013-deploying-mobility.md)

  - [<span data-ttu-id="44e12-126">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-126">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)

  - [<span data-ttu-id="44e12-127">Конфигурация работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e12-127">Health configuration in Lync Server 2013</span></span>](lync-server-2013-health-configuration-in-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

