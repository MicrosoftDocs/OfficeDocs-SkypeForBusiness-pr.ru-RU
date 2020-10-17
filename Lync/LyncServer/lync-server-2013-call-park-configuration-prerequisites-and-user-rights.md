---
title: 'Lync Server 2013: необходимые условия и права пользователя для настройки парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f39bd78d4c04ffef6763e3d1f48e40ca55089
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508266"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="0b5c0-102">Необходимые условия и права пользователя для настройки парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b5c0-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b5c0-103">_**Последнее изменение темы:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="0b5c0-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="0b5c0-104">Парковки вызовов — это функция управления звонками, которая устанавливается по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0b5c0-105">В этом разделе описываются действия, которые необходимо выполнить, прежде чем можно будет настроить парковки вызовов и права пользователя, необходимые для выполнения задач по настройке.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b5c0-106">Не выполняется резервное копирование настроенных файлов музыки на удержание для приложения парковки вызовов в рамках процесса аварийного восстановления Lync Server 2013, а файлы будут потеряны, если загруженные в пул файлы повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="0b5c0-107">Всегда храните отдельную копию настраиваемых файлов музыки для вызовов в режиме удержания, загруженные для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="0b5c0-108">В этом разделе предполагается, что вы прочитали документацию по планированию, относящуюся к парковки вызовов (см. [Планирование функций управления вызовами в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="0b5c0-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="0b5c0-109">Необходимые условия для настройки парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="0b5c0-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="0b5c0-110">Для парковки вызовов требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0b5c0-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="0b5c0-111">служба приложения;</span><span class="sxs-lookup"><span data-stu-id="0b5c0-111">Application service</span></span>

  - <span data-ttu-id="0b5c0-112">Приложение "Парковка вызовов"</span><span class="sxs-lookup"><span data-stu-id="0b5c0-112">Call Park application</span></span>

<span data-ttu-id="0b5c0-113">Эти компоненты устанавливаются автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="0b5c0-114">Если вы хотите, чтобы вызывающий абонент слышал музыку во время приостановки вызовов, для этого также потребуется файл музыки при удержании.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="0b5c0-115">Стандартный файл для хранения музыки устанавливается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0b5c0-116">Вы можете заменить его на собственный файл.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="0b5c0-117">Служба парковки вызовов использует хранилище файлов для хранения звукового файла.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="0b5c0-118">Права пользователя настройки парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="0b5c0-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="0b5c0-119">Для настройки парковки вызовов можно использовать следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="0b5c0-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="0b5c0-120">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0b5c0-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="0b5c0-121">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="0b5c0-121">Lync Server Management Shell</span></span>

<span data-ttu-id="0b5c0-122">Эти средства используются для настройки таблицы орбит парковки вызовов и настройки других параметров, используемых для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="0b5c0-123">Для настройки парковки вызовов требуется любая из следующих административных ролей в зависимости от задачи:</span><span class="sxs-lookup"><span data-stu-id="0b5c0-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="0b5c0-124">**CsVoiceAdministrator:** Эта роль администратора позволяет создавать, настраивать и управлять всеми параметрами и политиками, связанными с голосовыми сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="0b5c0-125">**CsUserAdministrator:** Эта роль администратора позволяет включить приостановку вызовов в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="0b5c0-126">Она также имеет доступ только для чтения ко всем параметрам конфигурации голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="0b5c0-127">**CsServerAdministrator:** Эта роль администратора позволяет управлять серверами и службами, а также отслеживать их и устранять неполадки.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="0b5c0-128">**CsAdministrator:** Эта роль администратора позволяет выполнять все задачи CsVoiceAdministrator, CsServerAdministrator и CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b5c0-129">Подробные сведения об административных правах приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0b5c0-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b5c0-130">См. также</span><span class="sxs-lookup"><span data-stu-id="0b5c0-130">See Also</span></span>


[<span data-ttu-id="0b5c0-131">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b5c0-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="0b5c0-132">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b5c0-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

