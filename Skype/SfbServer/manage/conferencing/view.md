---
title: Просмотр политик конференц-связи в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Сводка: Узнайте, как для просмотра политик конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 161b9f172af935b105e01bda88c1c3dbef2e3a9f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992338"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="15e0a-103">Просмотр политик конференц-связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="15e0a-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="15e0a-104">**Сводка:** Узнайте, как для просмотра политик конференц-связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="15e0a-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="15e0a-105">Политики конференц-связи можно просмотреть с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="15e0a-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="15e0a-106">Просмотр политик конференц-связи с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="15e0a-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="15e0a-107">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="15e0a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="15e0a-108">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="15e0a-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="15e0a-109">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="15e0a-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="15e0a-110">На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="15e0a-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="15e0a-111">В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="15e0a-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="15e0a-112">**Изменения политики конференц - \<политики\> ** открывает Отображение параметров для выбранной политики.</span><span class="sxs-lookup"><span data-stu-id="15e0a-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="15e0a-113">Для получения дополнительных сведений о настройке параметров см. [Создание политики конференц-связи в Скайп для Business Server](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="15e0a-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="15e0a-114">Просмотр политик конференц-связи с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="15e0a-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="15e0a-115">Чтобы просмотреть политики конференц-связи, используйте командлет **Get-CsConferencingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="15e0a-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="15e0a-116">Командлет возвращает данные в следующем виде:</span><span class="sxs-lookup"><span data-stu-id="15e0a-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="15e0a-117">Дополнительные сведения, включая описание полный синтаксис и список параметров [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="15e0a-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

