---
title: Просмотр политик конференц-связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Сводка: сведения о том, как просматривать политики конференций в Skype для бизнеса Server.'
ms.openlocfilehash: 7ea7b5cb9ba54fcf26e5f37b79320466c19d1050
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992194"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>Просмотр политик конференц-связи в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как просматривать политики конференций в Skype для бизнеса Server.
  
Вы можете просматривать политики конференц-связи с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для Business Server Management.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Просмотр политик конференц-связи с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.
    
5. В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.
    
    Диалоговое окно " **изменение политики конференц-связи" \<— открывается параметр политики\> ** , в котором отображаются параметры выбранной политики.
    
    Подробнее о настройке параметров можно узнать в разделе [Создание политик конференц-связи в Skype для бизнеса Server](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Просмотр политик конференц-связи с помощью командной консоли Skype для бизнеса Server

Чтобы просмотреть политики конференц-связи, используйте командлет **Get-CsConferencingPolicy**.
  
```PowerShell
Get-CsConferencingPolicy
```

Командлет возвращает данные в следующем виде:
  
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

Дополнительные сведения, включая полные описания синтаксиса и список параметров, можно найти в [статьях Get-ксконференЦингполици](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
  

