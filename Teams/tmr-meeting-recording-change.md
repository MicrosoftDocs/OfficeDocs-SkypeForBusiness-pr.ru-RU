---
title: Использование OneDrive для бизнеса и SharePoint Online для записей собраний
author: cichur
ms.author: v-cichur
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как перейти со Stream на хранилище записи собраний OneDrive для бизнеса и SharePoint в Microsoft Teams.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: bbde1b4d5425b0bbcf904528f0ddb232f27a2ba4b15fb0755639ef01b1f5f09f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312447"
---
# <a name="use-onedrive-for-business-and-sharepoint-online-or-stream-for-meeting-recordings"></a>Использование OneDrive для бизнеса, SharePoint Online или Stream для записей собраний

> [!Note]
> Переход с использования Microsoft Stream на OneDrive для бизнеса и SharePoint Online для записей собраний будет поэтапным процессом.

|<div style="width:290px">Дата&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Событие&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------------|:----------------------|
|5 октября 2020 г.<br> *(Завершено)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Включение политики собраний Teams, чтобы записи собраний сохранялись в OneDrive для бизнеса и SharePoint Online, а не в Microsoft Stream (классическая версия)|
|Развертывание с 7 января 2021 г.<br> *(Завершено)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Все новые записи собраний Teams будут сохраняться в OneDrive для бизнеса и SharePoint Online, если вы не отложили этот переход, изменяя политики собраний Teams в вашей организации и явно устанавливая для них значение **Stream**. Отображение отчетов о политике в виде Stream не является достаточным условием. Необходимо явно установить для политики значение **Stream**.|
|Развертывание с 11 января 2021 г.<br> *(Завершено)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Только GCC**<br> В то время как клиенты GCC могут отказаться от возможности, начиная с 5 октября, вы не можете ее принять. Эта возможность будет развертываться для всех пользователей GCC с 11 января 2021 г., если вы не отказались от нее.<br>  <br>Начиная с 11 января 2021 года, все новые записи собраний Teams для клиентов GCC будут сохраняться в OneDrive для бизнеса и SharePoint Online, если вы не отложили этот переход, изменяя политики собраний Teams в вашей организации и явно устанавливая для них значение **Stream**. <br><br>Если вы отказались от возможности, но готовы включить ее, вы можете сделать это, явно установив политику собраний Teams на значение **OneDrive для бизнеса**. |
|Развертывание от 1 марта 2021 г.<br> *(Завершено)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Только GCC-High и DoD**<br> Теперь клиенты впервые могут включить записи собраний в облаке в Microsoft Teams. По умолчанию эти записи будут храниться и воспроизводиться в OneDrive и SharePoint Online. |
|Развертывание от 7 июля 2021 г.<br> *(Завершено)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Все клиенты (планы "Корпоративный", "Для образовательных учреждений" и "GCC")**<br> Для собрания Teams, которое было записано в OneDrive и SharePoint Online, а также транскрибировалось в прямом эфире во время собрания, вы можете выполнять поиск файла записи собрания в Поиске (Майкрософт) на базе стенограммы. |
|Последовательное развертывание с 16 августа 2021 г. &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Все клиенты (планы "Корпоративный", "Для образовательных учреждений" и "GCC")**<br>Новые записи собраний сохраняются в Microsoft Stream (классическая версия); у всех клиентов записи собраний автоматически сохраняются в OneDrive для бизнеса и SharePoint Online, даже если они изменили свои политики собраний Teams на Stream.<br><br> Мы рекомендуем клиентам для улучшения контроля изменений в организации соглашаться с переходом по мере готовности в любой удобный момент, а не ждать пока он произойдет самостоятельно. |

В Microsoft Teams существует новый метод сохранения записей собраний. На первом этапе перехода с классической версии Microsoft Stream на [новый Stream](/stream/streamnew/new-stream) этот метод сохраняет записи в Microsoft OneDrive для бизнеса и SharePoint в Microsoft 365, а также предлагает множество преимуществ.

Stream (классическая версия) в качестве платформы не устареет в ближайшем будущем. Видео, которые в настоящий момент находятся в Stream (классическая версия), останутся там до тех пор, пока в будущем не будет доступно средство миграции для их перемещения в OneDrive и SharePoint Online. Для получения дополнительной информации о наших планах см. [Миграция классической версии Stream](/stream/streamnew/classic-migration).

> [!NOTE]
> Если запись собрания Teams не удается отправить в OneDrive или SharePoint Online, она будет временно сохранена в службах мультимедиа Azure (AMS). После сохранения в AMS не предпринимается повторная попытка автоматической отправки записи в OneDrive, SharePoint Online или Stream.

Записи собраний, сохраненные в AMS, доступны в течение 21 дня, а затем автоматически удаляются. При необходимости сохранить копию пользователи могут скачать видео из AMS.

Преимущества использования OneDrive для бизнеса и SharePoint Online для сохранения записей:

- Политики хранения для записи собраний Teams (TMR) (метки автоматического хранения S+C E5)
- Преимущества управления информацией в OneDrive для бизнеса и SharePoint Online
- Простота настройки разрешений и общего доступа
- Делитесь с гостями (внешними пользователями) записями, только явно предоставляя общий доступ
- Поток запроса доступа
- Предоставляйте общие ссылки в OneDrive для бизнеса и SharePoint Online
- Записи собраний доступны быстрее
- Поиск на базе стенограммы, записанной во время собрания
- Поддержка **локального** клиента
- Поддержка нескольких регионов — записи хранятся в регионе, определенном для этого пользователя
- Поддержка создания собственных ключей (BYOK)

См. полный список [возможностей, доступных в настоящее время и ожидаемых в будущем](/stream/streamnew/features-new-version-stream).

Дополнительные сведения см. в статье "Новые возможности записей собраний в Microsoft Teams".

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint-online"></a>Настройка параметра записи собраний в OneDrive для бизнеса и SharePoint Online

Параметр записи собраний — это параметр на уровне политики Teams. В приведенном ниже примере показано, как задать глобальную политику. Убедитесь, что вы задаете параметр записи собраний для политики или политик, которые вы назначили пользователям.

> [!Note]
> Распространение изменений политики собраний Teams займет некоторое время. Выполните проверку через несколько часов после настройки, а затем выйдите из системы и повторно войдите в классическое приложение Teams или просто перезагрузите компьютер.

1. Установка PowerShell в Teams PowerShell

   > [!NOTE]
   > Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell. Если вы используете последний общедоступный выпуск Teams PowerShell, вам не нужно устанавливать соединитель Skype для бизнеса Online. См. статью [Управление Skype для бизнеса Online с помощью PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide)

2. Запустите PowerShell от имени администратора.

3. Установите модуль [Teams PowerShell](./teams-powershell-install.md).

4. Импортируйте модуль MicrosoftTeams и выполните вход в качестве администратора Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

5. Используйте [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy), чтобы настроить политику собраний Teams для перехода с хранилища Stream на OneDrive для бизнеса и SharePoint Online.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Если некоторым пользователям назначена политика для организатора или пользователя, то необходимо задать этот параметр в этой политике, если вы хотите, чтобы они также хранили записи собраний в OneDrive для бизнеса и SharePoint Online. Дополнительные сведения см. в статье [Управление политиками собраний в Teams](meeting-policies-in-teams.md).

## <a name="learn-more"></a>Подробнее

Дополнительные сведения о записи собраний Teams в облаке см. в статье [Запись собраний Teams в облаке](cloud-recording.md). В этой статье вы можете узнать дополнительные сведения о таких параметрах записи как настройка, управление, распоряжение, разрешения и хранилище.
