---
title: 'Lync Server 2013: Настройка представления коллекции'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06054e1728245c87e8bf35419d3890f4e379543a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="62217-102">Настройка представления коллекции в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62217-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62217-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="62217-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="62217-104">В Lync Server 2013 вы настраиваете представление "коллекция видеоконференций" в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="62217-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="62217-105">По умолчанию включено представление коллекции.</span><span class="sxs-lookup"><span data-stu-id="62217-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="62217-106">Если вы не хотите разрешать Просмотр коллекции или разрешить ее для некоторых пользователей, вам нужно отключить эту функцию в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="62217-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="62217-107">Если видео участника конференции недоступно, вы можете улучшить режим просмотра коллекции пользователей при развертывании фотографий высокого разрешения, новой функции в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62217-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="62217-108">Фотографии высокого разрешения предоставляют альтернативу уменьшению фотографии контактных лиц с ограниченными разрешениями, которые хранятся в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="62217-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="62217-109">Фотографии высокого разрешения хранятся в почтовом ящике Exchange 2013 и, следовательно, требуют интеграции Lync Server 2013 с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="62217-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="62217-110">Дополнительные сведения можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)статье блога для NextHop: "интеграция Exchange 2013 и Lync Server 2013".</span><span class="sxs-lookup"><span data-stu-id="62217-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62217-111">Содержимое всех блогов и их URL-адреса могут быть изменены без уведомления.</span><span class="sxs-lookup"><span data-stu-id="62217-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="62217-112">Вы можете просмотреть или изменить параметры представления коллекции с помощью панели управления Lync Server 2013 или одного из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="62217-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="62217-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="62217-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="62217-114">**Set-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="62217-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="62217-115">**New-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="62217-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="62217-116">Настройка представления галереи со следующими параметрами политики конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="62217-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="62217-117">**Алловмултивиев**   . Этот параметр определяет, разрешено ли пользователю упорядочивать видеоконференции в галерее.</span><span class="sxs-lookup"><span data-stu-id="62217-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="62217-118">Этот параметр применяется к запланированным и нерегламентированным собраниям, созданным пользователем.</span><span class="sxs-lookup"><span data-stu-id="62217-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="62217-119">Иллюстрируют</span><span class="sxs-lookup"><span data-stu-id="62217-119">Examples:</span></span>
    
      - <span data-ttu-id="62217-120">Для этого параметра установлено значение true для пользователя A, который расположен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62217-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="62217-121">Собрания, упорядоченные по пользователю, позволяют пользователям присоединяться к нескольким видеопотокам и принимать их.</span><span class="sxs-lookup"><span data-stu-id="62217-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="62217-122">Для этого параметра задано значение false для пользователя B, который расположен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="62217-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="62217-123">Для собраний, организованных пользователем B, есть один видеопоток, аналогичный видеоконференцией Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="62217-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="62217-124">Этот параметр определяет, кто может упорядочивать собрания, разрешающие несколько видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="62217-124">This parameter determines who can organize meetings that allow multiple video streams.</span></span> <span data-ttu-id="62217-125">Участники собраний, которые разрешают нескольким видеопотокам получать несколько видеопотоков, в зависимости от их индивидуальных разрешений (ознакомьтесь с описанием параметра Енаблемултивиевжоин).</span><span class="sxs-lookup"><span data-stu-id="62217-125">Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="62217-126">**Енаблемултивиевжоин**   . Этот параметр определяет, будет ли участник собрания получать в галерее представление о работе с видео в собраниях, которые допускают его.</span><span class="sxs-lookup"><span data-stu-id="62217-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="62217-127">Этот параметр определяет взаимодействие пользователя с собранием, в котором он участвует.</span><span class="sxs-lookup"><span data-stu-id="62217-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="62217-128">Иллюстрируют</span><span class="sxs-lookup"><span data-stu-id="62217-128">Examples:</span></span>
    
      - <span data-ttu-id="62217-129">Для этого параметра установлено значение true для пользователя C. Пользователь C может получать несколько видеопотоков при участии в собрании или запуске пользователем A. User C получает один видеопоток, аналогичный видеоконференцией Lync Server 2010 при участие в собрании или запущено пользователем B.</span><span class="sxs-lookup"><span data-stu-id="62217-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="62217-130">Для этого параметра задано значение false для пользователя г. пользователь г получает один видеопоток, похожий на видеоконференцию, предоставленную Lync Server 2010 при участии в собраниях, организованных пользователем а или пользователем B.</span><span class="sxs-lookup"><span data-stu-id="62217-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="62217-131">Ниже описана процедура использования командной консоли Lync Server для включения видеоконференций в галерее.</span><span class="sxs-lookup"><span data-stu-id="62217-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="62217-132">Изменение политики конференц-связи в коллекции "Просмотр видеоконференций"</span><span class="sxs-lookup"><span data-stu-id="62217-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="62217-133">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="62217-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="62217-134">Чтобы изменить политику конференц-связи, в командной строке выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="62217-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

