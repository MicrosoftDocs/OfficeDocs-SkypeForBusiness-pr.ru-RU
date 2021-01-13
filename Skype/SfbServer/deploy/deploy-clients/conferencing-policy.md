---
title: Политика conferencing для учетных записей системы комнат Skype
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: В этом разделе вы узнаете, как назначать политики для учетных записей системы комнат Skype.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812729"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Политика conferencing для учетных записей системы комнат Skype
 
В этом разделе вы узнаете, как назначать политики для учетных записей системы комнат Skype.
  
## <a name="conferencing-policy-features"></a>Функции политики conferencing

Политика conferencing, назначенная учетной записи системы комнат Skype, должна иметь определенные характеристики. В большинстве раз клиент системы комнат Skype присоединяется к запланированному собранию, поэтому политика конференц-связи организатора собрания влияет на конференцию. Однако в Skype для бизнеса Server определенные возможности зависят от конфигурации участника. Например, если политика участника разрешает максимальное разрешение видео 1080p, участники будут использовать эту возможность видео с более высоким разрешением в конференции, даже если политика организатора не разрешает ее. В следующей таблице описано несколько таких параметров, которые следует учитывать при настройке политик для учетных записей системы комнат Skype в организации. 
  
|Возможность  <br/> |Значение  <br/> |Комментарий  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Должно быть true для звука системы комнат Skype  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Должно быть истинным, чтобы звук системы комнат Skype работал в сеансах доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Позволяет системе комнат Skype отрисовки видеопотоков с несколькими представлениями  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Зависит от того, включена ли учетная запись Корпоративная голосовая связь (EV) (см. раздел "Включение учетных записей системы комнат Skype для Skype для бизнеса")  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Зависит от того, включена ли учетная запись Корпоративная голосовая связь (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A in Meet Now (ad hoc) meetings, but Skype Room System can respond to polls on the screen at the front of room  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A in Meet Now (ad hoc) meetings, but Skype Room System can respond to polls on the screen at the front of room  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Н/Д для системы комнат Skype. Если зафиксировать true, удаленная сторона может записать  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Н/Д для системы комнат Skype. Если зафиксировать true, удаленная сторона может записать  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Недоступно  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Недоступно  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Позволяет клиенту системы комнат Skype принимать участие в одноранговых видеосвязях  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |Недоступно  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Система комнат Skype для бизнеса Server игнорирует hd1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Влияет на сеансы доски meet Now (ad hoc) в системе комнат Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |См. примечание в конце таблицы\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Это максимальная допустимая скорость исходящие видеосвязи. Система комнат Skype может отправлять один поток 1080 вместе с pano (если используется RoundTable) с такой скоростью. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |См. примечание в конце таблицы\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |Недоступно  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Рекомендуется установить этот уровень как можно более высоким. Эффективная пропускная способность зависит от условий сети во время конференций.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Для системы комнат Skype должно быть засвеяно true, чтобы обеспечить многосервийные видеопотоки  <br/> |
   
* Сведения о планировании пропускной способности см. в требованиях [к пропускной способности сети для трафика мультимедиа.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Если клиент системы комнат Skype попытается присоединиться к запланированному собранию, организованному пользователем, который находится в пуле Lync Server 2010, политика конференций организатора собрания может помешать клиенту системы комнат Skype выполнять совместную работу. 
  
## <a name="meeting-authentication"></a>Проверка подлинности на собрании

Система комнат Skype запросит у пользователей проверку подлинности при использовании ссылки на присоединиться к собранию с ограниченным доступом; например, собрание, для которого настроены параметры "lobby" собрания в Outlook. Этот параметр всегда настроен для настроенных собраний, и пользователям всегда будет предложено. Однако для неограниченных собраний пользователи могут присоединяться к собранию без проверки подлинности. 
  
Следующая команда позволяет администраторам требовать проверку подлинности для всех собраний, включая неограниченные собрания: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

По умолчанию requireRoomSystemsAuthorization имеет значение FALSE. 
  

