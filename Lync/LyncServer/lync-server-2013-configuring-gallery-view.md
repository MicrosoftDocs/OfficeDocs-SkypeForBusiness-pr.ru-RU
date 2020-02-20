---
title: 'Lync Server 2013: Настройка представления галереи'
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
ms.openlocfilehash: 02c13f2b1fa312394edfaba01ecd05179f86a0c9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a><span data-ttu-id="63918-102">Настройка представления галереи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63918-102">Configuring Gallery View in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63918-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="63918-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="63918-104">В Lync Server 2013 вы настраиваете Просмотр коллекции видео-конференций в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="63918-104">In Lync Server 2013, you configure Gallery View video conferencing in conferencing policy.</span></span> <span data-ttu-id="63918-105">Представление галереи включено по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="63918-105">Gallery View is turned on by default.</span></span> <span data-ttu-id="63918-106">Если вы хотите запретить представление галереи или разрешить его только для некоторых пользователей, вам необходимо отключить этот компонент в политике конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="63918-106">If you do not want to allow Gallery View, or want to allow it for only some users, you need to turn off the feature in conferencing policy.</span></span>

<span data-ttu-id="63918-107">Если видео участника конференции недоступно, можно улучшить работу с представлением коллекции пользователей при развертывании фотографий высокого разрешения, новой функции в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63918-107">When a conference participant's video is not available, the users' Gallery View experience can be enhanced if you deploy high-resolution photos, a new feature in Lync Server 2013.</span></span> <span data-ttu-id="63918-108">Фотографии с высоким разрешением предоставляют альтернативу уменьшению фотографий контактных лиц с ограниченным разрешением, хранящимся в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63918-108">High-resolution photos provide an alternative to the smaller, limited resolution contact photos stored in Active Directory Domain Services.</span></span> <span data-ttu-id="63918-109">Фотографии высокого разрешения хранятся в почтовом ящике Exchange 2013 пользователя и, следовательно, требуют интеграции Lync Server 2013 с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="63918-109">High-resolution photos are stored in a user's Exchange 2013 mailbox, and, therefore, require you to integrate Lync Server 2013 with Exchange 2013.</span></span> <span data-ttu-id="63918-110">Дополнительные сведения можно найти в статье, посвященной сведениям о сайте [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987)NextHop, "интеграция Exchange 2013 и Lync Server 2013".</span><span class="sxs-lookup"><span data-stu-id="63918-110">For details, see the NextHop blog article, "Integrating Exchange 2013 and Lync Server 2013," at [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63918-111">Содержимое и URL-адрес любого блога могут быть изменены без предварительного уведомления.</span><span class="sxs-lookup"><span data-stu-id="63918-111">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<span data-ttu-id="63918-112">Просмотреть или изменить параметры представления галереи можно с помощью панели управления Lync Server 2013 или с помощью одного из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="63918-112">You can view or modify the Gallery View parameters by using Lync Server 2013 Control Panel or by using one of the following cmdlets:</span></span>

  - <span data-ttu-id="63918-113">**Get-CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="63918-113">**Get-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="63918-114">**Set — CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="63918-114">**Set-CsConferencingPolicy**</span></span>

  - <span data-ttu-id="63918-115">**New — CsConferencingPolicy**</span><span class="sxs-lookup"><span data-stu-id="63918-115">**New-CsConferencingPolicy**</span></span>

<span data-ttu-id="63918-116">Настройте представление галереи, используя следующие параметры политики конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="63918-116">Configure Gallery View with the following conferencing policy settings:</span></span>

  - <span data-ttu-id="63918-117">**Алловмултивиев**   этот параметр определяет, разрешено ли пользователю упорядочивать видеоконференций в коллекции.</span><span class="sxs-lookup"><span data-stu-id="63918-117">**AllowMultiview**   This parameter controls whether a user is allowed to organize Gallery View video conferences.</span></span> <span data-ttu-id="63918-118">Этот параметр применяется к запланированным и незапланированным собраниям, созданным пользователем.</span><span class="sxs-lookup"><span data-stu-id="63918-118">This parameter applies to scheduled and ad-hoc meetings created by the user.</span></span>
    
    <span data-ttu-id="63918-119">Примеры:</span><span class="sxs-lookup"><span data-stu-id="63918-119">Examples:</span></span>
    
      - <span data-ttu-id="63918-120">Для этого параметра задано значение true для пользователя A, который размещен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63918-120">This parameter is set to True for User A, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="63918-121">Собрания, организованные пользователем A, позволяют пользователям присоединяться и принимать несколько видеопотоков.</span><span class="sxs-lookup"><span data-stu-id="63918-121">Meetings organized by User A enable users to join and receive multiple video streams.</span></span>
    
      - <span data-ttu-id="63918-122">Для этого параметра задано значение false для пользователя б, который размещен в пуле Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63918-122">This parameter is set to False for User B, who is homed on a Lync Server 2013 pool.</span></span> <span data-ttu-id="63918-123">Собрания, организованные по пользователю б, имеют один видеопоток, похожий на видеоконференцию, предоставляемую Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="63918-123">Meetings organized by User B have a single video stream that is similar to the video conference experience provided by Lync Server 2010.</span></span>
    
    <span data-ttu-id="63918-p106">Этот параметр определяет, кто может организовывать собрания, допускающие использование нескольких видеопотоков. В соответствии с индивидуальными разрешениями участникам собраний, допускающих использование нескольких видеопотоков, может быть как разрешено, так и запрещено принимать несколько видеопотоков (см. описание параметра EnableMultiviewJoin).</span><span class="sxs-lookup"><span data-stu-id="63918-p106">This parameter determines who can organize meetings that allow multiple video streams. Participants in meetings that allow multiple video streams may or may not be allowed to receive multiple video streams, based on their individual permissions (see the description for the EnableMultiviewJoin parameter).</span></span>

  - <span data-ttu-id="63918-126">**Для параметра enablemultiviewjoin**   этот параметр определяет, будет ли участник собрания получать представление о работе с видео в собрании, разрешив его.</span><span class="sxs-lookup"><span data-stu-id="63918-126">**EnableMultiviewJoin**   This parameter controls whether a participant in a meeting receives the Gallery View video experience in meetings that allow it.</span></span> <span data-ttu-id="63918-127">Этот параметр управляет взаимодействием с пользователем на любом собрании, котором этот пользователь принимает участие.</span><span class="sxs-lookup"><span data-stu-id="63918-127">This parameter controls the user's experience in any meeting in which he or she participates.</span></span>
    
    <span data-ttu-id="63918-128">Примеры:</span><span class="sxs-lookup"><span data-stu-id="63918-128">Examples:</span></span>
    
      - <span data-ttu-id="63918-129">Для этого параметра задано значение true для пользователя C. Пользователь C может получить несколько видеопотоков при участии в собрании или запуске пользователем A. Пользователь C получает один видеопоток, подобный интерфейсу видеоконференций, предоставляемому Lync Server 2010 при участие в собрании, организованном или запущенных пользователем б.</span><span class="sxs-lookup"><span data-stu-id="63918-129">This parameter is set to True for User C. User C can receive multiple video streams when participating in a meeting organized or started by User A. User C receives a single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in a meeting organized or started by User B.</span></span>
    
      - <span data-ttu-id="63918-130">Для этого параметра задано значение false для пользователя D. пользователь D получает один видеопоток, похожий на видеоконференцию, предоставляемую Lync Server 2010 при участии во всех собраниях, организованных пользователем A или пользователем б.</span><span class="sxs-lookup"><span data-stu-id="63918-130">This parameter is set to False for User D. User D receives single video stream that is similar to the video conference experience provided by Lync Server 2010 when participating in any meeting organized by User A or User B.</span></span>

<span data-ttu-id="63918-131">Следующая процедура является примером использования командной консоли Lync Server для включения видеоконференций в режиме галереи.</span><span class="sxs-lookup"><span data-stu-id="63918-131">The following procedure is an example of using Lync Server Management Shell to enable Gallery View video conferencing.</span></span>

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a><span data-ttu-id="63918-132">Изменение политики конференц-связи для видео-конференций с использованием представления галереи</span><span class="sxs-lookup"><span data-stu-id="63918-132">To modify conferencing policy for Gallery View video conferencing</span></span>

1.  <span data-ttu-id="63918-133">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="63918-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="63918-134">Выполните в командной строке следующий командлет для изменения политики конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="63918-134">At the command line, run the following cmdlet to edit conferencing policy:</span></span>
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>

