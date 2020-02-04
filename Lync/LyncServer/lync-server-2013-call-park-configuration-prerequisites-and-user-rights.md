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
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="bb63e-102">Необходимые условия и права пользователя для настройки парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb63e-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb63e-103">_**Тема последнего изменения:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="bb63e-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="bb63e-104">Приостановка звонков — это функция управления звонками, которая устанавливается по умолчанию при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bb63e-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bb63e-105">В этой статье описаны действия, которые необходимо выполнить, прежде чем можно будет настроить приостановку звонков и права пользователей, необходимые для выполнения задач настройки.</span><span class="sxs-lookup"><span data-stu-id="bb63e-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb63e-106">Настроенные файлы на удержании с сохранением музыки для приложения парковки не заархивированы в рамках процесса восстановления для Lync Server 2013, а файлы будут потеряны, если файлы, отправленные в пул, повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="bb63e-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="bb63e-107">Всегда храните отдельную копию настраиваемых файлов музыки для вызовов в режиме удержания, загруженные для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="bb63e-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="bb63e-108">В этом разделе предполагается, что вы прочитали документацию по планированию, связанную с приостановкой звонка (см. [Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="bb63e-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="bb63e-109">Необходимые условия для настройки приостановки звонка</span><span class="sxs-lookup"><span data-stu-id="bb63e-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="bb63e-110">Для парковки звонков требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="bb63e-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="bb63e-111">приложения</span><span class="sxs-lookup"><span data-stu-id="bb63e-111">Application service</span></span>

  - <span data-ttu-id="bb63e-112">приостановки вызовов</span><span class="sxs-lookup"><span data-stu-id="bb63e-112">Call Park application</span></span>

<span data-ttu-id="bb63e-113">Эти компоненты устанавливаются автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bb63e-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="bb63e-114">Если вы хотите, чтобы во время приостановки звонка звуковая музыка продавалась, требуется также указать файл, на который нужно поместить файлы на хранение.</span><span class="sxs-lookup"><span data-stu-id="bb63e-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="bb63e-115">Файл на удержании по умолчанию устанавливается автоматически при развертывании корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bb63e-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bb63e-116">Вы можете заменить файл по умолчанию собственным файлом на удержании.</span><span class="sxs-lookup"><span data-stu-id="bb63e-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="bb63e-117">Для хранения звукового файла в методе парковки используется хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="bb63e-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="bb63e-118">Права пользователя на настройку приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="bb63e-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="bb63e-119">Для настройки парковки звонков можно использовать следующие средства администрирования:</span><span class="sxs-lookup"><span data-stu-id="bb63e-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="bb63e-120">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="bb63e-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="bb63e-121">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="bb63e-121">Lync Server Management Shell</span></span>

<span data-ttu-id="bb63e-122">Эти средства используются для настройки таблицы "Приостановка звонка" и для настройки других параметров, используемых при приостановке звонков.</span><span class="sxs-lookup"><span data-stu-id="bb63e-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="bb63e-123">Для настройки метода парковки требуется любая из указанных ниже административных ролей в зависимости от задачи.</span><span class="sxs-lookup"><span data-stu-id="bb63e-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="bb63e-124">**Ксвоицеадминистратор:** Эта роль администратора может создавать, настраивать и управлять всеми параметрами и политиками, связанными с голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="bb63e-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="bb63e-125">**Ксусерадминистратор:** Эта роль администратора может включить приостановку звонков в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bb63e-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="bb63e-126">Эта роль администратора также имеет доступ к просмотру только для чтения для всех конфигураций голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bb63e-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="bb63e-127">**Кссерверадминистратор:** Эта роль администратора может управлять работой серверов и служб, а также отслеживать их и устранять неполадки.</span><span class="sxs-lookup"><span data-stu-id="bb63e-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="bb63e-128">**Ксадминистратор:** Эта роль администратора может выполнять все задачи Ксвоицеадминистратор, Кссерверадминистратор и Ксусерадминистратор.</span><span class="sxs-lookup"><span data-stu-id="bb63e-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb63e-129">Подробные сведения о правах администратора можно найти <A href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bb63e-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb63e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bb63e-130">See Also</span></span>


[<span data-ttu-id="bb63e-131">Развертывание корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb63e-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="bb63e-132">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb63e-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

