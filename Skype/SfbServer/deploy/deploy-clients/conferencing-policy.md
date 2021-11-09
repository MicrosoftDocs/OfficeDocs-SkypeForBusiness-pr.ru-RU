---
title: Политика conferencing для Skype учетных записей системы номеров
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Ознакомьтесь с этой темой, чтобы узнать, как назначить политики conferencing для Skype учетных записей системы номеров.
ms.openlocfilehash: 97980cb50613fca105af40686a920a8ff9c9b546
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838371"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Политика conferencing для Skype учетных записей системы номеров
 
Ознакомьтесь с этой темой, чтобы узнать, как назначить политики conferencing для Skype учетных записей системы номеров.
  
## <a name="conferencing-policy-features"></a>Функции политики conferencing

Политика conferencing, назначенная учетной записи Skype room System, должна иметь определенные характеристики. В большинстве Skype клиент системы номеров присоединяется к запланированному собранию, поэтому политика конференц-связи организатора собрания влияет на конференцию. Однако в Skype для бизнеса Server определенные возможности зависят от конфигурации участника. Например, если политика участника позволяет максимальное разрешение видео в 1080p, участники будут испытывать эту возможность видео с более высоким разрешением на конференции, даже если политика организатора этого не позволяет. В следующей таблице описано несколько таких параметров, о которых следует знать при настройке политик конференций для Skype учетных записей системы номеров в организации. 
  
|Функция  <br/> |Значение  <br/> |Comment  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Должно быть верно для Skype системы номеров  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Должно быть верно для Skype системы номеров для работы в сеансах доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Позволяет Skype комнате для отрисовки нескольких видеопотоков с несколькими представлениями  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|Отключение PowerPointAnnotations  <br/> |FALSE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Зависит от того, включена ли учетная запись Корпоративная голосовая связь (EV) (см. раздел Включение Skype учетных записей системы номеров для Skype для бизнеса)  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Зависит от того, включена ли Корпоративная голосовая связь учетная запись (EV).  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A в собраниях Meet Now (ad hoc), но Skype система номеров может реагировать на опросы на экране в передней части комнаты  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A в собраниях Meet Now (ad hoc), но Skype система номеров может реагировать на опросы на экране в передней части комнаты  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|EnableAppDesktopSharing  <br/> |Версия для настольного компьютера  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A для Skype системы номеров. Если TRUE, удаленная сторона может записывать  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A для Skype системы номеров. Если TRUE, удаленная сторона может записывать  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Н/Д  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Н/Д  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Позволяет клиенту Skype room System участвовать в одноранговых сеансах видео  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |Н/Д  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Игнорируется Skype для бизнеса Server, Skype комната система использует HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Влияет на сеансы доски Meet Now (ad hoc) в Skype Room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |См. примечание в конце таблицы\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Это максимальная допустимая скорость исходящие биты видео. Skype Система room system может отправить один поток 1080 вместе с pano (если используется roundTable) по этой скорости бита. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |См. примечание в конце таблицы\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |Н/Д  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Рекомендуется установить этот уровень как можно более высоким. Эффективная пропускная способность зависит от сетевых условий во время конференций.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Должно быть TRUE для Skype системы номеров, чтобы обеспечить много просмотр видеопотоков  <br/> |
   
* Сведения о планировании пропускной способности см. в ссылке Требования к [пропускной способности](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)сети для трафика мультимедиа.
  
> [!NOTE]
> Если клиент Skype Room System попытается присоединиться к запланированному собранию, организованному пользователем, который находится в пуле Lync Server 2010, политика конференций организатора собрания может помешать клиенту Skype Room System выполнять совместную работу. 
  
## <a name="meeting-authentication"></a>Проверка подлинности собраний

Skype Система номеров побуждает пользователей к проверке подлинности при использовании ссылки на соединение собраний для пользования ограниченной встречей; например, собрание, для которого параметры лобби собраний были настроены в Outlook. Этот параметр всегда для настраиваемых собраний, и пользователям всегда будет предложено. Однако для неограниченных собраний пользователи могут присоединяться к собранию без проверки подлинности. 
  
Следующая команда позволяет администраторам требовать проверки подлинности для всех собраний, включая неограниченные собрания: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

По умолчанию requireRoomSystemsAuthorization является FALSE. 
  

