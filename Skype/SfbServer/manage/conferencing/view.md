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
ms.localizationpriority: medium
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: Сводка. Узнайте, как просматривать политики конференций в Skype для бизнеса Server.
ms.openlocfilehash: f3e41eaa136674e7ab91af0b947daf6def872be5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578813"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Просмотр политик conferencing в Skype для бизнеса Server
 
**Сводка:** Узнайте, как просматривать политики conferencing в Skype для бизнеса Server.
  
Политики конференций можно просматривать с помощью панели Skype для бизнеса Server или с помощью Skype для бизнеса Server management Shell.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Просмотр политик conferencing с помощью Skype для бизнеса Server панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
4. На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.
    
5. В **фильтре редактирования файла** выберите поле **"Сведения** о шоу".
    
    **Изменение политики conferencing — \<policy\>** открывает отображение параметров выбранной политики.
    
    Дополнительные сведения о настройке параметров см. в материале [Create conferencing policies in Skype для бизнеса Server.](create-policies.md)
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Просмотр политик conferencing с помощью Skype для бизнеса Server управленческой оболочки

Чтобы просмотреть политики conferencing, используйте **cmdlet Get-CsConferencingPolicy:**
  
```PowerShell
Get-CsConferencingPolicy
```

В этом кодлете возвращаются такие сведения, как следующие:
  
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

Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в обзоре [Get-CsConferencingPolicy.](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)
