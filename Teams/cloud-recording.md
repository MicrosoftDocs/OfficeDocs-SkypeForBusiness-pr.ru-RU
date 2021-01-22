---
title: Запись облачного собрания в Teams
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.reviewer: nakulm
search.appverid: MET150
f1.keywords:
- NOCSH
description: Практические рекомендации по развертыванию функций облачного голосового управления в Teams для записи собраний и групповых звонков Teams для записи аудио- и видеосвязи, а также обмена экранами.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 40fad38d8c77d8194d2bf24a451fb9438f10c586
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918975"
---
# <a name="teams-cloud-meeting-recording"></a>Запись облачного собрания в Teams

В Microsoft Teams пользователи могут записывать свои собрания Teams и групповые звонки. Можно записывать звук, видео и действия демонстрации экрана. Существует возможность записи с автоматической расшифровкой аудиозаписей, чтобы пользователи могли воспроизводить записи собрания с субтитрами и искать важные элементы обсуждения в расшифровке. Запись происходит в облаке и сохраняется в [Microsoft Stream](https://docs.microsoft.com/stream/), поэтому пользователи могут безопасно делиться ею со своей организацией.

Связанные: [документация конечного пользователя записи собрания Teams](https://aka.ms/recordmeeting)

>[!Note]
> Переход с использования Microsoft Stream на [OneDrive для бизнеса и SharePoint для записей собраний](tmr-meeting-recording-change.md) будет поэтапным процессом. При запуске вы сможете согласиться на использование этого интерфейса. В ноябре вам потребуется отказаться от использования, если вы хотите продолжить применение Stream. В начале 2021 г. мы потребуем, чтобы все пользователи перешли на OneDrive для бизнеса и SharePoint для записей собраний.

> [!NOTE]
> Сведения об использовании ролей в собраниях Teams и изменении ролей пользователей см. в сведениях о [ролях в собрании Teams.](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)

## <a name="prerequisites-for-teams-cloud-meeting-recording"></a>Предварительные условия для записи облачных собраний Teams

Для записи собраний пользователя Teams необходимо включить Для клиента Microsoft Stream. Кроме того, для организатора собрания и лица, инициирующего запись, необходимы следующие предварительные условия:

- У пользователя есть Office 365 E1, E3, E5, A1, A3, A5, Microsoft 365 бизнес премиум, бизнес стандартный или Бизнес базовый<sup>1</sup>
- Пользователь согласился с правилами компании, если они установлены администратором
- У пользователя достаточно места в Microsoft Stream для сохранения записей
- Для записи собраний и групповых звонков пользователь установил для параметра CsTeamsMeetingPolicy -AllowCloudRecording true (Разрешить запись собраний и групповых звонков).
- Для записи звонков 1:1 пользователь установил для параметра CsTeamsCallingPolicy -AllowCloudRecordingForCalls параметр true
- Пользователь не является анонимным, гостевым или федеративным пользователем на собрании
- Чтобы включить транскрибцию для собрания пользователя, в назначенной ему политике собраний Teams должен быть установлен параметр -AllowTranscription true.

<sup>1</sup> 20 августа 2020 г. доступ к файлу записи собрания истекает через 21 день у пользователей с A1. Дополнительные сведения см. в [записи собрания Microsoft Teams в Stream.](https://docs.microsoft.com/stream/portal-upload-teams-meeting-recording)

> [!IMPORTANT] 
> Пользователям не нужно иметь лицензию Microsoft Stream, если вы хотите, чтобы они могли только создавать и скачивать записи. Это означает, что записи хранятся не в Microsoft Stream, а в службах мультимедиа Async (AMS) с ограничением в 21 день до удаления. В этом случае администратор не может ни управлять записями, ни удалять их.

> [!IMPORTANT]
> Кроме того, на записи, которые находятся в AMS, влияет само сообщение чата. Таким образом, удаление исходного сообщения чата записи AMS помешает пользователям получить доступ к записи. Существует два сценария, которые могут повлиять на эту ситуацию. 1) Пользователь вручную удаляет сообщение чата. В этом случае, когда исходное сообщение исчезнет, пользователи больше не смогут получить доступ к записи и больше не смогут скачивать его. Однако сами записи могут храниться во внутренних системах Майкрософт в течение определенного времени (не превышающий исходный 21-дневный период). 2) Запись сообщения чата удаляется с помощью политики хранения чата. Записи AMS связаны непосредственно с политикой хранения чата. Таким образом, хотя записи в AMS по умолчанию сохраняются в течение 21 дня перед удалением, если сообщение чата удаляется до 21-дневного периода, из-за политик хранения сообщений чата запись также будет удалена. После этого восстановить запись будет не удалось.

## <a name="set-up-teams-cloud-meeting-recording-for-users-in-your-organization"></a>Настройка записи облачных собраний Teams для пользователей в вашей организации

В этом разделе объясняется, как вы можете настроить и запланировать запись собраний Teams.

### <a name="turn-on-microsoft-stream-for-users-in-the-organization"></a>Включив Microsoft Stream для пользователей в организации

Microsoft Stream доступен в составе соответствующих подписок Microsoft 365 и Office 365 или как автономные службы.  См. [Обзор лицензирования Stream](https://docs.microsoft.com/stream/license-overview) для более подробной информации.  Microsoft Stream теперь входит в состав Microsoft 365 бизнес, Microsoft 365 бизнес стандартный и Microsoft 365 бизнес базовый.

Узнайте больше о том, как назначать лицензии пользователям [в Microsoft 365 или Office 365,](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) чтобы пользователи могли получать доступ к Microsoft Stream. Убедитесь, что Microsoft Stream не заблокирован для пользователей, как определено в окнах блокировки регистрации [для Microsoft Stream.](https://docs.microsoft.com/stream/disable-user-organization)

### <a name="make-sure-users-have-upload-video-permissions-in-microsoft-stream"></a>Убедитесь, что у пользователей есть разрешения на отправку видео в Microsoft Stream

По умолчанию все в компании могут создавать контент в Stream, если Stream активирован и лицензия назначена пользователю. Администратор Microsoft Stream может [ограничить сотрудников для создания контента](https://docs.microsoft.com/stream/restrict-uploaders) в Stream. Пользователи, которые находятся в этом ограниченном списке, не смогут записывать встречи.

### <a name="notify-employees-to-consent-to-company-guidelines-in-microsoft-stream"></a>Уведомить сотрудников о согласии с руководящими принципами компании в Microsoft Stream

Если администратор Microsoft Stream [настроил политику руководства компании](https://docs.microsoft.com/stream/company-policy-and-consent) и требует, чтобы сотрудники приняли эту политику перед сохранением содержимого, пользователи должны сделать это перед записью в Microsoft Teams. Перед развертыванием функции записи в организации убедитесь, что пользователи согласились с этой политикой.

### <a name="turn-on-or-turn-off-cloud-recording"></a>Включить или отключить облачную запись

Вы можете использовать центр администрирования Microsoft Teams или PowerShell, чтобы установить политику собраний команд, чтобы контролировать возможность записи собраний пользователей.

В центре администрирования Microsoft Teams включите или выключите параметр **Разрешить запись в облаке** в политике собрания. Чтобы узнать больше, см. [Управление политиками собраний в Teams](meeting-policies-in-teams.md#allow-cloud-recording).

Используя PowerShell, вы настраиваете параметр AllowCloudRecording в TeamsMeetingPolicy. Чтобы узнать больше, см. [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)и [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Обратите внимание, что как организатор собрания, так и инициатор записи должны иметь разрешения на запись для записи собрания. Если пользователям не назначена настраиваемая политика, пользователи получают глобальную политику, в которой по умолчанию включена запись AllowCloudRecording.

> [!NOTE]
> Дополнительные сведения об использовании ролей Teams для настройки разрешений на запись собраний см. в сведениях о ролях [в собрании Teams.](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)

Чтобы пользователь мог вернуться к глобальной политике, используйте следующий командлет, чтобы удалить конкретное назначение политики для пользователя:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Чтобы изменить значение AllowCloudRecording в Глобальной политике, используйте следующий командлет:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $false
```
</br>
</br>


|                                                                 Сценарий                                                                 |                                                                                                                                                                         Действия                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                    Я хочу, чтобы все пользователи в моей компании могли записывать свои встречи                                    |                                                                     <ol><li>Подтвердите, что глобальный CsTeamsMeetingPolicy имеет AllowCloudRecording = True<li>У всех пользователей есть глобальная политика CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = True </ol>                                                                     |
| Я хочу, чтобы большинство моих пользователей могли записывать свои собрания, но выборочно отключать определенных пользователей, которым не разрешено записывать |        <ol><li>Подтвердите, что GlobalCsTeamsMeetingPolicy имеет AllowCloudRecording = True<li>У большинства пользователей есть глобальная политика CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = True<li>Всем другим пользователям была предоставлена одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = False</ol>         |
|                                                   Я хочу, чтобы запись была отключена на 100%                                                   |                                                                <ol><li>Подтвердите, что глобальные CsTeamsMeetingPolicy имеют AllowCloudRecording = False<li>Всем пользователям была предоставлена глобальная политика CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = False                                                                 |
|      Я хочу отключить запись для большинства пользователей, но выборочно разрешить определенным пользователям записывать       | <ol><li>Подтвердите, что глобальные CsTeamsMeetingPolicy имеют AllowCloudRecording = False<li>Большинству пользователей была предоставлена глобальная политика CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = False<li>Всем другим пользователям была предоставлена одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = True <ol> |
|                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                  |
#### <a name="where-your-meeting-recordings-are-stored"></a>Где хранятся записи вашей встречи

Записи собраний хранятся в облачном хранилище Microsoft Stream. В настоящее время функция записи собрания отключена для клиентов, чьи данные Teams хранятся в стране, если Microsoft Stream недоступен в регионе расположения данных в стране, где хранятся данные. Возможность записи собрания может быть включена для клиентов, данные которых должны храниться в стране, даже если Microsoft Stream не доступен в этом регионе. Для этого можно разрешить хранение записей в ближайшем географическом регионе Microsoft Stream. 

Если данные ваших Teams хранятся внутри страны, и вы предпочитаете хранить записи собраний внутри страны, мы рекомендуем отключить эту функцию, а затем включить ее после развертывания Microsoft Stream в вашем регионе проживания данных в стране. Чтобы отключить эту функцию для всех пользователей  в организации, отключите параметр "Разрешить облачную запись" в политике собраний Глобальной группы, которая находится в Центре администрирования Microsoft Teams. Однако если вы хотите, чтобы записи хранились в ближайшем географическом регионе Microsoft Stream, перед  изменением необходимо включить как разрешение облачной записи, так и разрешение хранения за пределами этого региона. 

Чтобы включить запись в регионе в глобальной политике, используйте следующий cmdlet:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowCloudRecording $true -AllowRecordingStorageOutsideRegion $true

Here's a summary of what happens when you turn on meeting recording when this change takes effect:

|If you turn on meeting recordings...|Meeting recordings are stored... |
|---|---|
|Before Microsoft Stream is available in your in-country data residency region |In the nearest Microsoft Stream region|
|After Microsoft Stream is available in your in-country data residency region |In your in-country data residency region|

For new and existing tenants that haven't yet turned on meeting recording, new recordings are stored in-country after Microsoft Stream is available in the in-country data residency region. However, any tenant that enables meeting recording before Microsoft Stream is available in the in-country data residency region will continue to use the Microsoft Stream storage for existing and new recordings, even after Microsoft Stream is available in the in-country data residency region.

To find the region where your Microsoft Stream data is stored, in Microsoft Stream, click **?** in the upper-right corner, click **About Microsoft Stream**, and then click **Your data is stored in**.  To learn more about the regions where Microsoft Stream stores data, see [Microsoft Stream FAQ](https://docs.microsoft.com/stream/faq#which-regions-does-microsoft-stream-host-my-data-in).

To learn more about where data is stored across services in Microsoft 365 or Office 365, see [Where is your data located?](https://products.office.com/where-is-your-data-located?rtc=1)

### Turn on or turn off recording transcription

This setting controls whether captions and transcription features are available during playback of meeting recordings. If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording. The person who started the recording needs this setting turned on so that the recording also includes transcription.

> [!NOTE]
> That transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting. They are stored together with the meeting recordings in Microsoft Stream cloud storage.

You can use the Microsoft Teams admin center or PowerShell to set a Teams meeting policy to control whether the recording initiator gets a choice to transcribe the meeting recording.

In the Microsoft Teams admin center, turn on or turn off the **Allow transcription** setting in the meeting policy. To learn more, see [Manage meeting policies in Teams](meeting-policies-in-teams.md#allow-transcription).

Using PowerShell, you configure the AllowTranscription setting in TeamsMeetingPolicy. To learn more, see [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) and [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

Unless you have assigned a custom policy to the users, users get the Global policy, which has AllowTranscription disabled by default.

For a user to fall back to Global policy, use the following cmdlet to remove a specific policy assignment for a user:

```powershell
Grant-CsTeamsMeetingPolicy -Identity {user} -PolicyName $null -Verbose
```

Чтобы изменить значение AllowCloudRecording в Глобальной политике, используйте следующий командлет:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowTranscription $false
```
</br>
</br>

|Сценарий|Действия |
|---|---|
|Я хочу, чтобы все пользователи в моей компании могли транскрибировать при инициации записи собрания |<ol><li>Подтвердите, что глобальный CsTeamsMeetingPolicy имеет AllowTranscription = True <li>Все пользователи имеют глобальную политику csTeamsMeetingPolicy ИЛИ одну из политик CsTeamsMeetingPolicy со значением AllowTranscription = True. </ol>|
|Я хочу, чтобы большинство моих пользователей могли транскрибировать записи собраний, но выборочно отключать определенных пользователей, которым не разрешено транскрибировать |<ol><li>Подтвердите, что глобальный CsTeamsMeetingPolicy имеет AllowTranscription = True <li>У большинства пользователей есть глобальные политики CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowTranscription = True <li>Всем другим пользователям была предоставлена одна из политик CsTeamsMeetingPolicy с AllowTranscription = False </ol>|
|Я хочу, чтобы транскрипция записи была отключена на 100% |<ol><li>Подтвердите, что глобальные CsTeamsMeetingPolicy имеют AllowTranscription = False <li>Всем пользователям была предоставлена глобальная политика CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowTranscription = False </ol>|
|Я хочу, чтобы транскрипция была отключена для большинства пользователей, но выборочно включить конкретных пользователей, которым разрешено транскрибировать |<ol><li>Подтвердите, что глобальные CsTeamsMeetingPolicy имеют AllowCloudRecording = False <li>Большинству пользователей была предоставлена глобальная политика CsTeamsMeetingPolicy ИЛИ одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = False <li>Всем другим пользователям была предоставлена одна из политик CsTeamsMeetingPolicy с AllowCloudRecording = True </ol>|
|||

### <a name="planning-for-storage"></a>Планирование хранения

Размер 1-часовой записи составляет 400 МБ. Убедитесь, что вы понимаете емкость, необходимую для записанных файлов, и имеете достаточно места для хранения в Microsoft Stream.  Ознакомьтесь [с обзором лицензирования Microsoft Stream,](https://docs.microsoft.com/stream/license-overview) чтобы понять базовое хранилище, включенное в подписку, и узнать, как приобрести дополнительное место в хранилище.

## <a name="manage-meeting-recordings"></a>Управление записями собраний

Записи собрания считаются собственностью арендатора. Если владелец записи покидает компанию, администратор может открыть URL-адрес видеозаписи в Microsoft Stream в режиме администратора. Администратор может удалить запись, обновить любые метаданные записи или изменить разрешения для записи видео. Узнайте больше о [возможностях администратора в Stream](https://docs.microsoft.com/stream/manage-content-permissions).

> [!NOTE]
> См. [Управление пользовательскими данными в Microsoft Stream](https://docs.microsoft.com/stream/managing-user-data) и [Разрешения и конфиденциальность в Microsoft Stream](https://docs.microsoft.com/stream/portal-permissions) для получения дополнительной информации об управлении записями и доступом пользователей.

## <a name="compliance-and-ediscovery-for-meeting-recordings"></a>Соответствие требованиям и электронное обнаружение для записей собраний

Записи собраний хранятся в Microsoft Stream, который соответствует Microsoft 365 и Office 365 Tier-C. Для поддержки запросов e-Discovery для администраторов соответствия, которые заинтересованы в записях собраний или вызовов для Microsoft Streams, сообщение о завершении записи доступно в функции поиска контента соответствия для Microsoft Teams. Администраторы соответствия могут искать ключевое слово «запись» в строке темы элемента в предварительном просмотре поиска содержимого соответствия и обнаруживать записи встреч и вызовов в организации. Обязательное условие для просмотра всех записей - их необходимо настроить в Microsoft Stream с правами администратора. Узнайте больше о [назначении прав администратора в Stream](https://docs.microsoft.com/stream/assign-administrator-user-role).

## <a name="related-topics"></a>Статьи по теме

- [Обзор PowerShell в Teams](teams-powershell-overview.md)
