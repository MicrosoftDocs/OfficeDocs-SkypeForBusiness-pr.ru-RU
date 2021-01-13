---
title: Просмотр политик в Skype для бизнеса Server
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
description: Сводка. Узнайте, как просматривать политики в Skype для бизнеса Server.
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817509"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Просмотр политик в Skype для бизнеса Server
 
**Сводка:** Learn how to view conferencing policies in Skype for Business Server.
  
You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>View conferencing policies by using Skype for Business Server Control Panel

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем щелкните **"Conferencing Policy" (Политика).**
    
4. На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.
    
5. В **фильтре "Изменить файл"** выберите **"Показать сведения".**
    
    **Edit Conferencing \<policy\> Policy -** открывает отображение параметров выбранной политики.
    
    Дополнительные сведения о настройке параметров см. в дополнительных сведениях о создании политик конфигурации [в Skype для бизнеса Server.](create-policies.md)
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>View conferencing policies by using Skype for Business Server Management Shell

Чтобы просмотреть политики, используйте **get-CsConferencingPolicy:**
  
```PowerShell
Get-CsConferencingPolicy
```

Этот cmdlet возвращает следующие сведения:
  
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

Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [get-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)
  

