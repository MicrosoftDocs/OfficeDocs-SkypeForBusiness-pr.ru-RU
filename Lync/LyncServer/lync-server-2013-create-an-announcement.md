---
title: 'Lync Server 2013: создание извещения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create an announcement
ms:assetid: a6fd5922-fe46-41ba-94e3-c76b1101a31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412783(v=OCS.15)
ms:contentKeyID: 48185005
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80210787a8261d122fa7508807ab995279c7d0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-an-announcement-in-lync-server-2013"></a><span data-ttu-id="abd6c-102">Создание объявления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abd6c-102">Create an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abd6c-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="abd6c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="abd6c-104">Чтобы создать новое оповещение, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="abd6c-104">To create a new announcement, you need to perform the following steps:</span></span>

1.  <span data-ttu-id="abd6c-105">Если планируется использовать звуковое приглашение, запишите звуковой файл с помощью любого приложения для звукозаписи.</span><span class="sxs-lookup"><span data-stu-id="abd6c-105">For audio prompts, record the audio file by using your favorite audio recording application.</span></span>

2.  <span data-ttu-id="abd6c-106">Чтобы импортировать содержимое звукового файла в хранилище файлов, выполните командлет **Import-CsAnnouncementFile**.</span><span class="sxs-lookup"><span data-stu-id="abd6c-106">For audio prompts, run the **Import-CsAnnouncementFile** cmdlet to import the contents of the audio file to File Store.</span></span>

3.  <span data-ttu-id="abd6c-107">Чтобы создать оповещение и присвоить ему имя, выполните командлет **New-CsAnnouncement**.</span><span class="sxs-lookup"><span data-stu-id="abd6c-107">Run the **New-CsAnnouncement** cmdlet to create and name the announcement.</span></span> <span data-ttu-id="abd6c-108">С его помощью можно создавать оповещения со звуковыми приглашениями, текстовыми приглашениями, преобразованными в речь, а также оповещения без приглашений.</span><span class="sxs-lookup"><span data-stu-id="abd6c-108">Perform this step to create announcements with an audio prompt, a text-to-speech (TTS) prompt, or no prompt.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="abd6c-109">Вы можете создать оповещение без приглашения, например, если требуется переводить звонки в определенное назначение без воспроизведения сообщения.</span><span class="sxs-lookup"><span data-stu-id="abd6c-109">You might want to create an announcement with no prompt (for example, if you want to transfer calls to a specific destination without playing a message).</span></span>

    
    </div>

4.  <span data-ttu-id="abd6c-110">Назначьте новое оповещение диапазону номеров в таблице неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="abd6c-110">Assign the new announcement to a number range in the unassigned number table.</span></span>

<span data-ttu-id="abd6c-111">В этом разделе описывается импорт и создание оповещений.</span><span class="sxs-lookup"><span data-stu-id="abd6c-111">This topic describes how to import and create announcements.</span></span> <span data-ttu-id="abd6c-112">Подробнее о назначении объявлений в таблице неназначенные номера можно найти в разделе [Настройка таблицы неназначенные номера в Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span><span class="sxs-lookup"><span data-stu-id="abd6c-112">For details about assigning announcements in the unassigned number table, see [Configure the unassigned number table in Lync Server 2013](lync-server-2013-configure-the-unassigned-number-table.md).</span></span>

<div>

## <a name="to-create-a-new-announcement"></a><span data-ttu-id="abd6c-113">Создание нового оповещения</span><span class="sxs-lookup"><span data-stu-id="abd6c-113">To create a new announcement</span></span>

1.  <span data-ttu-id="abd6c-114">Если планируется использовать звуковые приглашения, создайте звуковой файл.</span><span class="sxs-lookup"><span data-stu-id="abd6c-114">For audio prompts, create the audio file.</span></span>

2.  <span data-ttu-id="abd6c-115">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="abd6c-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

3.  <span data-ttu-id="abd6c-116">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="abd6c-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="abd6c-117">Для звуковых приглашений выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="abd6c-117">For audio prompts, run:</span></span>
    
        Import-CsAnnouncementFile -Parent <service of the Application Server running the Announcement application> -FileName <name for file in File Store> -Content Byte [<contents of file in byte array>]

5.  <span data-ttu-id="abd6c-118">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="abd6c-118">Run:</span></span>
    
        New-CsAnnouncement -Parent <service of Application Server running the Announcement application, in the form: service:ApplicationServer:<fqdn>> -Name <unique name to be used as destination in unassigned number table> [-AudioFilePrompt <FileName specified in Import-CsAnnouncementFile>] [-TextToSpeechPrompt <text string to be converted to speech>] [-Language <Language for playing the TTS prompt (required for PromptTts)>] [-TargetUri sip:SIPAddress for transferring caller after announcement]
    
    <span data-ttu-id="abd6c-p103">Для перевода звонков на голосовую почту введите SIP-адрес в формате sip:имя_пользователя@имя_домена;opaque=app:voicemail (пример: sip:bob@contoso.com;opaque=app:voicemail). Для перевода звонков на номер телефона введите SIP-адрес в формате sip:номер@имя_домена;user=phone (пример: sip:+ 14255550121@contoso.com;user=phone).</span><span class="sxs-lookup"><span data-stu-id="abd6c-p103">For transferring calls to voice mail, type SIPAddress in the format sip:username@domainname;opaque=app:voicemail (for example, sip:bob@contoso.com;opaque=app:voicemail). For transferring calls to a phone number, type SIPAddress in the format sip:number@domainname;user=phone (for example, sip:+ 14255550121@contoso.com;user=phone).</span></span>
    
    <span data-ttu-id="abd6c-121">Например, чтобы указать звуковое приглашение, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="abd6c-121">For example, to specify an audio prompt:</span></span>
    
        $a = Get-Content ".\PromptFile.wav" -ReadCount 0 -Encoding Byte
        Import-CsAnnouncementFile -Parent service:ApplicationServer:pool0@contoso.com -FileName "ChangedNumberMessage.wav" -Content $a
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Number Changed Announcement" -AudioFilePrompt "ChangedNumberMessage.wav"
    
    <span data-ttu-id="abd6c-122">Например, чтобы указать текстовое приглашение, преобразованное в речь, введите:</span><span class="sxs-lookup"><span data-stu-id="abd6c-122">For example, to specify a TTS prompt:</span></span>
    
        New-CsAnnouncement -Parent service:ApplicationServer:pool0.contoso.com -Name "Help Desk Announcement" -TextToSpeechPrompt "The Help Desk number has changed. Please dial 5550100." -Language "en-US"
    
    <span data-ttu-id="abd6c-123">Подробнее об этих командлетах и о том, как просмотреть список кодов языков, используемых в параметре **тексттоспичпромпт** , можно найти в статьях [New-ксаннаунцемент](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span><span class="sxs-lookup"><span data-stu-id="abd6c-123">For more detail about these cmdlets, and to see a list of the language codes to use in the **TextToSpeechPrompt** parameter, see [New-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="abd6c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="abd6c-124">See Also</span></span>


[<span data-ttu-id="abd6c-125">Import-CsAnnouncementFile</span><span class="sxs-lookup"><span data-stu-id="abd6c-125">Import-CsAnnouncementFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsAnnouncementFile)  
[<span data-ttu-id="abd6c-126">New-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="abd6c-126">New-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAnnouncement)  
[<span data-ttu-id="abd6c-127">Настройка таблицы неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abd6c-127">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

