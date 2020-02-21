---
title: 'Lync Server 2013: необходимые условия и роли для настройки оповещений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 037625d0efea2ae53cd4923a0a7cccce4a890098
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="2eae9-102">Необходимые условия и роли для настройки объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eae9-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eae9-103">_**Последнее изменение темы:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="2eae9-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="2eae9-104">Извещение — это функция управления вызовами корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2eae9-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="2eae9-105">В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить объявление и назначения ролей, необходимые для выполнения задач по настройке.</span><span class="sxs-lookup"><span data-stu-id="2eae9-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="2eae9-106">В этом разделе предполагается, что вы прочитали документацию по планированию, относящуюся к уведомлению (см. [Планирование функций управления вызовами в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="2eae9-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="2eae9-107">Предварительные требования к настройке объявлений</span><span class="sxs-lookup"><span data-stu-id="2eae9-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="2eae9-108">Для приложения извещения необходимы следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="2eae9-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="2eae9-109">служба приложения;</span><span class="sxs-lookup"><span data-stu-id="2eae9-109">Application service</span></span>

  - <span data-ttu-id="2eae9-110">приложение группы ответа;</span><span class="sxs-lookup"><span data-stu-id="2eae9-110">Response Group application</span></span>

  - <span data-ttu-id="2eae9-111">хранилище файлов для звуковых файлов.</span><span class="sxs-lookup"><span data-stu-id="2eae9-111">File Store, to hold audio files</span></span>

<span data-ttu-id="2eae9-112">Все эти компоненты устанавливаются по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2eae9-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="2eae9-113">Роли настройки объявлений</span><span class="sxs-lookup"><span data-stu-id="2eae9-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="2eae9-114">Для настройки объявлений можно использовать следующие средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="2eae9-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="2eae9-115">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="2eae9-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="2eae9-116">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="2eae9-116">Lync Server Management Shell</span></span>

<span data-ttu-id="2eae9-117">Для настройки приложения извещения требуется одна из следующих административных ролей:</span><span class="sxs-lookup"><span data-stu-id="2eae9-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="2eae9-118">**CsVoiceAdministrator**   эта роль администратора позволяет создавать, настраивать и управлять всеми параметрами и политиками голосовой связи, включая параметры оповещений.</span><span class="sxs-lookup"><span data-stu-id="2eae9-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="2eae9-119">**CsServerAdministrator**   эта роль администратора позволяет управлять, отслеживать и устранять неполадки в серверах и службах, а также настраивать все параметры оповещений.</span><span class="sxs-lookup"><span data-stu-id="2eae9-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="2eae9-120">**CsAdministrator**   . Эта роль администратора позволяет выполнять все административные задачи и изменять все параметры.</span><span class="sxs-lookup"><span data-stu-id="2eae9-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="2eae9-121">**CsViewOnlyAdministrator**   эта роль администратора может просматривать развертывание для мониторинга работоспособности развертывания.</span><span class="sxs-lookup"><span data-stu-id="2eae9-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2eae9-122">Дополнительные сведения об административных правах пользователей приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="2eae9-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2eae9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2eae9-123">See Also</span></span>


[<span data-ttu-id="2eae9-124">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eae9-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="2eae9-125">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eae9-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

