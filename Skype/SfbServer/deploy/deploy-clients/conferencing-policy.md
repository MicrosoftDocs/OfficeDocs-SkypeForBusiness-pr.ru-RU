---
title: Политика конференц-связи для учетных записей системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: В этом разделе описывается назначение политик конференц-связи для учетных записей Системы комнат Skype.
ms.openlocfilehash: 5c34ad8a397cc18fe6d9b67be421bfd6ce1d4435
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234487"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Политика конференц-связи для учетных записей системы комнат Skype
 
В этом разделе описывается назначение политик конференц-связи для учетных записей Системы комнат Skype.
  
## <a name="conferencing-policy-features"></a>Функции политики конференц-связи

Политика конференц-связи, назначенная учетной записи системы для помещения в Skype, должна иметь определенные характеристики. В большинстве случаев клиент системы помещения в Skype присоединяется к запланированному собранию, и, следовательно, политика конференций организатора собрания повлияет на конференцию. Тем не менее, в Skype для бизнеса Server некоторые возможности зависят от конфигурации участника. Например, если политика участника допускает предельное разрешение на работу с помощью функции 1080p, участники будут использовать эту возможность более высоком разрешающей способности на Конференции, даже если она не разрешена политикой организатора. В таблице ниже описаны некоторые параметры, которые следует учитывать при настройке политик конференц-связи с системными учетными записями Skype в Организации. 
  
|Функция  <br/> |Значение  <br/> |Комментарий  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Должно быть верно для звукового сопровождения Skype для системы комнат  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Должно быть истинным, чтобы звуковая система комнаты Skype работала в течение собрания (ad hoc) в системе комнат Skype  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Позволяет системе комнат Skype обрабатывать несколько представлений и видеопотоков  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|DisablePowerPointAnnotations  <br/> |False  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Зависит от того, включена ли учетная запись корпоративной голосовой связью (EV) (вы видите раздел Включение учетных записей системы для помещения Skype в Skype для бизнеса).  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Зависит от того, поддерживает ли учетная запись функцию корпоративной голосовой связи (EV)  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |Н/д в одноранговых собраниях, но система комнат Skype может отвечать на запросы на опросы на экране на передней части комнаты  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |Н/д в одноранговых собраниях, но система комнат Skype может отвечать на запросы на опросы на экране на передней части комнаты  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Н/д для системы комнат Skype. If TRUE, a remote party could record  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Н/д для системы комнат Skype. If TRUE, a remote party could record  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Н/Д  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Н/Д  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Позволяет клиенту системы комнаты Skype принимать участие в видеосеансах одноранговых устройств  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |Н/Д  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Игнорируется в Skype для бизнеса Server, система комнат Skype использует HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Влияет на проведение собраний на сегодня (ad hoc) на досках в системе комнат Skype  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Просмотр примечаний в конце таблицы\*  <br/> |
|VideoBitRateKB  <br/> |5000  <br/> |Это максимальная допустимая исходящая скорость видеосигнала. Система комнат Skype может отправлять 1 1080-поток вместе с Pano (если RoundTable используется) на этой скорости. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Просмотр примечаний в конце таблицы\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |Н/Д  <br/> |
|TotalReceiveVideoBitRateKB  <br/> |20000  <br/> |Рекомендуется установить значение как можно выше. Эффективная пропускная способность зависит от состояния сети на момент Конференции.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Должно быть ИСТИНным для системы комнат Skype, чтобы обеспечить возможность просмотра видеопотоков с несколькими мониторами  <br/> |
   
* Сведения о планировании пропускной способности можно найти в разделе [требования к пропускной способности сети для трафика мультимедиа](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Если клиент системы комнат Skype попытается присоединиться к запланированному собранию, организованному пользователем, расположенному на сервере Lync Server 2010, политика конференции организатора собрания может не позволить клиенту системы помещения в Skype выполнить совместную работу. 
  
## <a name="meeting-authentication"></a>Проверка подлинности в собрании

Система комнаты Skype запрашивает проверку подлинности пользователей при использовании ссылки присоединиться к собранию, чтобы присоединиться к ограниченному собранию; Например, собрание, для которого настроены параметры "зал собрания" в Outlook. Этот параметр всегда включен для настраиваемых собраний, и пользователям всегда отправляется запрос. Однако к собраниях с неограниченным доступом пользователи могут присоединиться, не проходя проверку подлинности. 
  
Следующая команда позволяет администраторам запрашивать проверку подлинности для всех собраний, включая собрания с неограниченным доступом: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

По умолчанию параметр RequireRoomSystemsAuthorization имеет значение FALSE. 
  

