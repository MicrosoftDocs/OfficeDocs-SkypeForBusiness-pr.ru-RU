---
title: Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о включении и отключении оповещений о подключении к собранию и выходе из него в Microsoft Teams. '
ms.openlocfilehash: d7e900a86a8292c56e9ce0d941506b8a894c8141
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459646"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams

При настройке функции аудиоконференций в Office 365 вы получите мост аудиоконференций. Мост конференц-связи может содержать один или несколько телефонных номеров, которые люди будут использовать для подключения к собранию Microsoft Teams по телефону. 
  
Мост конференц-связи отвечает на звонок для пользователя, подключающегося к собранию по телефону. Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности. Организатору собрания Microsoft Teams выдается ПИН-код, позволяющий начать собрание, если это не удается сделать с помощью приложения Microsoft Teams. Однако вы можете настроить систему так, чтобы ПИН-код для начала собрания не требовался.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Настройка способов присоединения к собранию

![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью центра администрирования группами Майкрософт**

1. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**. 

2. В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**. 

3. В области **Настройки моста** включите или отключите **уведомления о входе на собрание и выходе из него**. Этот флажок установлен по умолчанию. Если его снять, пользователи, уже присоединившиеся к собранию, не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.
    
4. В области **Тип объявлений о входе или выходе** выберите **Имена или номера телефонов** или **Тональные сигналы**.
    
5. Если вы выбрали **Имена или номера телефонов**, включите или отключите функцию **Попросить абонентов записывать свои имена перед присоединением к собранию**.
    
6. Нажмите кнопку **Сохранить**.

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Связанные разделы

[Общие вопросы об аудиоконференциях](audio-conferencing-common-questions.md)
