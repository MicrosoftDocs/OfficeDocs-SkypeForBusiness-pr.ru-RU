---
title: Просмотр политик conferencing в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: Сводка. Узнайте, как просматривать политики конференций в Skype для бизнеса Server.
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119408"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="47d0e-103">Просмотр политик conferencing в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="47d0e-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="47d0e-104">**Сводка:** Узнайте, как просматривать политики конференциинга в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="47d0e-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="47d0e-105">Политики конференциинга можно просматривать с помощью панели управления Skype для бизнес-серверов или с помощью панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="47d0e-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="47d0e-106">Просмотр политик конференциинга с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="47d0e-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="47d0e-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="47d0e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="47d0e-108">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="47d0e-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="47d0e-109">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.</span><span class="sxs-lookup"><span data-stu-id="47d0e-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="47d0e-110">На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="47d0e-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="47d0e-111">В **фильтре редактирования файла** выберите поле **"Сведения** о шоу".</span><span class="sxs-lookup"><span data-stu-id="47d0e-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="47d0e-112">**Изменение политики conferencing — \<policy\>** открывает отображение параметров выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="47d0e-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="47d0e-113">Дополнительные сведения о настройке параметров см. в материале [Create conferencing policies in Skype for Business Server.](create-policies.md)</span><span class="sxs-lookup"><span data-stu-id="47d0e-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="47d0e-114">Просмотр политик conferencing с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="47d0e-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="47d0e-115">Чтобы просмотреть политики conferencing, используйте **cmdlet Get-CsConferencingPolicy:**</span><span class="sxs-lookup"><span data-stu-id="47d0e-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="47d0e-116">В этом кодлете возвращаются такие сведения, как следующие:</span><span class="sxs-lookup"><span data-stu-id="47d0e-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
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
</pre>

<span data-ttu-id="47d0e-117">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в обзоре [Get-CsConferencingPolicy.](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="47d0e-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
