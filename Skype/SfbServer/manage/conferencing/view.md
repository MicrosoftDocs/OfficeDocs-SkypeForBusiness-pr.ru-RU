---
title: Просмотр политик конференц-связи в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Сводка: Узнайте, как для просмотра политик конференц-связи в Скайп для Business Server 2015.'
ms.openlocfilehash: 5a0e99506d5c9fb7bc8799abcb15e4bb4224a3bc
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568670"
---
# <a name="view-conferencing-policies-in-skype-for-business-server-2015"></a>Просмотр политик конференц-связи в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как для просмотра политик конференц-связи в Скайп для Business Server 2015.
  
Политики конференц-связи можно просмотреть с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Просмотр политик конференц-связи с помощью Скайп для панели управления Business Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
4. На странице **Политика конференц-связи** дважды щелкните политику, которую вы хотите просмотреть.
    
5. В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.
    
    **Изменения политики конференц - \<политики\> ** открывает Отображение параметров для выбранной политики.
    
    Для получения дополнительных сведений о настройке параметров см. [Создание политики конференц-связи в Скайп для Business Server 2015](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Просмотр политик конференц-связи с помощью Скайп для консоли Business Server

Чтобы просмотреть политики конференц-связи, используйте командлет **Get-CsConferencingPolicy**.
  
```
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

Дополнительные сведения, включая описание полный синтаксис и список параметров [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)см.
  

