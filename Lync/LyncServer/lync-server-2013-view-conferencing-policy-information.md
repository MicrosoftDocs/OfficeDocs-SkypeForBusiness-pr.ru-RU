---
title: 'Lync Server 2013: Просмотр сведений о политике конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c2cccd61d710acd9d2155412ec427c65eafc2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="7abe1-102">Просмотр сведений о политике конференц-связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7abe1-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7abe1-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7abe1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7abe1-104">В панели управления Lync Server 2013 вы можете управлять реализацией конференций в развертывании с помощью политик конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="7abe1-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="7abe1-105">Сюда относятся следующие политики конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="7abe1-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="7abe1-106">Глобальная политика, созданная по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7abe1-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="7abe1-107">Необязательная политика уровня сайта и пользовательского уровня, которую можно создать и использовать для определения способа реализации конференции для конкретных сайтов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="7abe1-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="7abe1-108">Просмотр параметров политики конференций</span><span class="sxs-lookup"><span data-stu-id="7abe1-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="7abe1-109">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7abe1-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7abe1-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7abe1-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7abe1-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7abe1-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7abe1-112">На панели навигации слева выберите **Конференц** -связь, а затем — **Политика Конференц**-связи.</span><span class="sxs-lookup"><span data-stu-id="7abe1-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="7abe1-113">На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="7abe1-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="7abe1-114">В окне " **Изменение фильтра файлов**" выберите **Показать подробности...**</span><span class="sxs-lookup"><span data-stu-id="7abe1-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="7abe1-115">флажок.</span><span class="sxs-lookup"><span data-stu-id="7abe1-115">check box.</span></span>
    
    <span data-ttu-id="7abe1-116">Диалоговое окно " \*\*изменение политики конференц-связи" \<— открывается параметр политики\> \*\* , в котором отображаются параметры выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="7abe1-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="7abe1-117">Подробнее о настройке параметров можно узнать в разделе [Создание или изменение политики конференц-связи в Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7abe1-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7abe1-118">Просмотр политик конференц-связи с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7abe1-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7abe1-119">Политики Конференции можно просмотреть с помощью Windows PowerShell и командлета Get-КсконференЦингполици.</span><span class="sxs-lookup"><span data-stu-id="7abe1-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="7abe1-120">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7abe1-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7abe1-121">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7abe1-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="7abe1-122">Просмотр политик конференц-связи</span><span class="sxs-lookup"><span data-stu-id="7abe1-122">To view conferencing policies</span></span>

  - <span data-ttu-id="7abe1-123">Чтобы просмотреть сведения обо всех политиках конференц-связи, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7abe1-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="7abe1-124">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="7abe1-124">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="7abe1-125">Дополнительные сведения можно найти в разделе справки по командлету [Get-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="7abe1-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

