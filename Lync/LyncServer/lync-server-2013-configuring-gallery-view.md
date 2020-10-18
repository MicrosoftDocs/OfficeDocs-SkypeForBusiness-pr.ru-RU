---
title: 'Lync Server 2013: Настройка представления галереи'
description: 'Lync Server 2013: Настройка представления галереи.'
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
ms.openlocfilehash: 2aec2f1e3c7bff9a3736f40584a29880978b9daa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575925"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="58e7c-103">Настройка представления галереи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58e7c-103">Configuring Gallery View in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58e7c-104">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="58e7c-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="58e7c-105">В Lync Server 2013 вы настраиваете Просмотр коллекции видео-конференций в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="58e7c-105">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="58e7c-106">Представление галереи включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58e7c-106">Gallery View is turned on by default.</span></span> <span data-ttu-id="58e7c-107">Если вы хотите запретить представление галереи или разрешить его только для некоторых пользователей, вам необходимо отключить этот компонент в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="58e7c-107">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="58e7c-108">Если видео участника конференции недоступно, можно улучшить работу с представлением коллекции пользователей при развертывании фотографий высокого разрешения, новой функции в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58e7c-108">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="58e7c-109">Фотографии с высоким разрешением предоставляют альтернативу уменьшению фотографий контактных лиц с ограниченным разрешением, хранящимся в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58e7c-109">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="58e7c-110">Фотографии высокого разрешения хранятся в почтовом ящике Exchange 2013 пользователя и, следовательно, требуют интеграции Lync Server 2013 с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="58e7c-110">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="58e7c-111">Дополнительные сведения можно найти в статье, посвященной сведениям о сайте NextHop, "Интеграция Exchange 2013 и Lync Server 2013" [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) .</span><span class="sxs-lookup"><span data-stu-id="58e7c-111">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58e7c-112">Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="58e7c-112">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="58e7c-113">Просмотреть или изменить параметры представления галереи можно с помощью панели управления Lync Server 2013 или с помощью одного из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="58e7c-113">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="58e7c-114">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="58e7c-114">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="58e7c-115">**Set — CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="58e7c-115">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="58e7c-116">**New — CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="58e7c-116">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="58e7c-117">Настройте представление галереи, используя следующие параметры политики конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="58e7c-117">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="58e7c-118">**Алловмултивиев**     Этот параметр определяет, разрешено ли пользователю упорядочивать видеоконференций в коллекции.</span><span class="sxs-lookup"><span data-stu-id="58e7c-118">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="58e7c-119">Этот параметр применяется к запланированным и незапланированным собраниям, созданным пользователем.</span><span class="sxs-lookup"><span data-stu-id="58e7c-119">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="58e7c-120">Примеры:</span><span class="sxs-lookup"><span data-stu-id="58e7c-120">Examples:</span></span>
    
      - <span data-ttu-id="58e7c-121">Для этого параметра задано значение true для пользователя A, который размещен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58e7c-121">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="58e7c-122">Собрания, организованные пользователем A, позволяют пользователям присоединяться и принимать несколько видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="58e7c-122">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="58e7c-123">Для этого параметра задано значение false для пользователя б, который размещен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58e7c-123">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="58e7c-124">Собрания, организованные по пользователю б, имеют один видеопоток, похожий на видеоконференцию, предоставляемую Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="58e7c-124">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="58e7c-p106">Этот параметр определяет, кто может организовывать собрания, допускающие использование нескольких видеопотоков. В соответствии с индивидуальными разрешениями участникам собраний, допускающих использование нескольких видеопотоков, может быть как разрешено, так и запрещено принимать несколько видеопотоков (см. описание параметра EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="58e7c-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="58e7c-127">**Для параметра enablemultiviewjoin**     Этот параметр определяет, будет ли участник собрания получать в собрании представление видеовзаимодействия в собрании.</span><span class="sxs-lookup"><span data-stu-id="58e7c-127">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="58e7c-128">Этот параметр управляет взаимодействием с пользователем на любом собрании, котором этот пользователь принимает участие.</span><span class="sxs-lookup"><span data-stu-id="58e7c-128">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="58e7c-129">Примеры:</span><span class="sxs-lookup"><span data-stu-id="58e7c-129">Examples:</span></span>
    
      - <span data-ttu-id="58e7c-130">Для этого параметра задано значение true для пользователя C. Пользователь C может получить несколько видеопотоков при участии в собрании или запуске пользователем A. Пользователь C получает один видеопоток, подобный интерфейсу видеоконференций, предоставленному Lync Server 2010 при участии в собрании или запуске пользователем B.</span><span class="sxs-lookup"><span data-stu-id="58e7c-130">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="58e7c-131">Для этого параметра задано значение false для пользователя D. пользователь D получает один видеопоток, похожий на видеоконференцию, предоставляемую Lync Server 2010 при участии во всех собраниях, организованных пользователем A или пользователем б.</span><span class="sxs-lookup"><span data-stu-id="58e7c-131">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="58e7c-132">Следующая процедура является примером использования командной консоли Lync Server для включения видеоконференций в режиме галереи.</span><span class="sxs-lookup"><span data-stu-id="58e7c-132">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="58e7c-133">Изменение политики конференц-связи для видео-конференций с использованием представления галереи</span><span class="sxs-lookup"><span data-stu-id="58e7c-133">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="58e7c-134">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="58e7c-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="58e7c-135">Выполните в командной строке следующий командлет для изменения политики конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="58e7c-135">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

