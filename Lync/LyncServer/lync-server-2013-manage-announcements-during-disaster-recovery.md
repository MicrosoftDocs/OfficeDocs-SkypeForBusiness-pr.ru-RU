---
title: 'Lync Server 2013: Управление объявлениями во время аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6058974b8473bc2c6db91abaaeb1550647ba592d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="072ea-102">Управление объявлениями во время аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="072ea-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="072ea-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="072ea-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="072ea-104">Lync Server 2013 поддерживает извещения о вызовах неназначенных номеров во время простоев.</span><span class="sxs-lookup"><span data-stu-id="072ea-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="072ea-105">Восстановление функциональности оповещений во время отказа не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="072ea-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="072ea-106">Если вы выбираете восстановление оповещений во время отказа, то необходимо пересоздать конфигурацию оповещений в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="072ea-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="072ea-107">В этом разделе описываются действия, которые необходимо выполнить для восстановления оповещений при аварийном восстановлении.</span><span class="sxs-lookup"><span data-stu-id="072ea-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="072ea-108">Этот раздел относится к диапазонам неназначенных номеров, использующим приложение "извещения".</span><span class="sxs-lookup"><span data-stu-id="072ea-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="072ea-109">Этот раздел не относится к диапазонам неназначенных номеров, использующим автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="072ea-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="072ea-110">До отказа</span><span class="sxs-lookup"><span data-stu-id="072ea-110">Before an Outage</span></span>

<span data-ttu-id="072ea-111">Независимо от того, хотите ли вы использовать объявления во время простоя, следует создать отдельные резервные копии всех настраиваемых звуковых файлов, настроенных для приложения оповещений.</span><span class="sxs-lookup"><span data-stu-id="072ea-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="072ea-112">Не выполняется резервное копирование настраиваемых оповещений в рамках процесса аварийного восстановления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="072ea-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="072ea-113">Если не взять отдельные резервные копии файлов, и файлы, отправленные на сервер или в пул, будут повреждены, испорчены или очищены, то они будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="072ea-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="072ea-114">Если у вас нет резервных копий настраиваемых звуковых файлов, а исходные аудиофайлы больше недоступны, вы можете найти звуковые файлы, настроенные для приложения оповещений, в хранилище файлов для сервера или пула, где вы изначально импортированы файлы.</span><span class="sxs-lookup"><span data-stu-id="072ea-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="072ea-115">Вы можете скопировать все звуковые файлы, настроенные для приложения оповещений из хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="072ea-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="072ea-116">**Копирование звуковых файлов из хранилища файлов**</span><span class="sxs-lookup"><span data-stu-id="072ea-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="072ea-117">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="072ea-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="072ea-118">Пример:</span><span class="sxs-lookup"><span data-stu-id="072ea-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="072ea-119">Здесь X-ApplicationServer-X ссылается на идентификатор службы сервера приложений пула (например, 1-ApplicationServer-1")</span><span class="sxs-lookup"><span data-stu-id="072ea-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="072ea-120">Во время отказа</span><span class="sxs-lookup"><span data-stu-id="072ea-120">During an Outage</span></span>

<span data-ttu-id="072ea-121">Чтобы использовать приложение извещения во время сбоя, необходимо повторно создать конфигурацию объявлений в резервном пуле, выполнив действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="072ea-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="072ea-122">Рекомендуется выполнять эти задачи после перехода резервный пул при отказе, поскольку после выполнения действия 2 резервный пул становится владельцем диапазонов не назначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="072ea-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="072ea-123">Для диапазонов номеров, использующих телефонный номер автосекретаря единой системы обмена сообщениями Exchange, выполнение этих действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="072ea-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="072ea-124">**Повторное создание конфигурации оповещений в резервном пуле**</span><span class="sxs-lookup"><span data-stu-id="072ea-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="072ea-125">Пересоздайте в резервном пуле оповещения, развернутые в основном пуле, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="072ea-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="072ea-126">Импортируйте все звуковые файлы, используемые в основном пуле, в резервный пул с помощью командлета **Import-CsAnnouncementFile**, указав резервный пул в параметре Parent.</span><span class="sxs-lookup"><span data-stu-id="072ea-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="072ea-127">Пересоздайте каждое оповещение с помощью командлета **New-CsAnnouncement**, указав резервный пул в параметре Parent.</span><span class="sxs-lookup"><span data-stu-id="072ea-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="072ea-128">Сведения о том, как использовать эти параметры для создания оповещений в резервном пуле, можно узнать <A href="lync-server-2013-create-an-announcement.md">в статье Create a извещения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="072ea-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="072ea-129">После пересоздания всех оповещений в резервном пуле перенаправьте все диапазоны не назначенных номеров, использующие оповещения в основном пуле, к пересозданным оповещениям в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="072ea-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="072ea-130">Для каждого диапазона не назначенных номеров, использующего оповещение из основного пула, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="072ea-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="072ea-131">После отказа</span><span class="sxs-lookup"><span data-stu-id="072ea-131">After the Outage</span></span>

<span data-ttu-id="072ea-132">Когда основной пул станет доступным, необходимо перенаправить диапазоны не назначенных номеров, измененные при отказе, обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="072ea-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="072ea-133">Для диапазонов номеров, использующих телефонный номер автосекретаря единой системы обмена сообщениями Exchange, выполнение этих действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="072ea-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="072ea-134">**Восстановление объявлений в основном пуле**</span><span class="sxs-lookup"><span data-stu-id="072ea-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="072ea-p105">Если пришлось перестроить основной пул во время восстановления, то необходимо пересоздать оповещения в основном пуле, импортировав звуковые файлы и создав оповещения, как это делалось для резервного пула, только не нужно указывать основной пул в параметре Parent. Подробные сведения см. в разделе "Во время отказа" выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="072ea-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="072ea-137">Для каждого диапазона не назначенных номеров, измененного во время отказа, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="072ea-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="072ea-138">Дополнительно можно удалить оповещения, пересозданные в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="072ea-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="072ea-139">Получение списка извещений для приложения извещения о резервном копировании пула.</span><span class="sxs-lookup"><span data-stu-id="072ea-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="072ea-140">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="072ea-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="072ea-141">Пример:</span><span class="sxs-lookup"><span data-stu-id="072ea-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="072ea-p107">В полученном списке найдите оповещения, которые требуется удалить, и скопируйте их GUID. Для каждого оповещения, которое требуется удалить, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="072ea-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="072ea-144">Пример:</span><span class="sxs-lookup"><span data-stu-id="072ea-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

