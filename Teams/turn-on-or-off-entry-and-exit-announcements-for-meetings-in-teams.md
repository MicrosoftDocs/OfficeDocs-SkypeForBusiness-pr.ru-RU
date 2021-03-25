---
title: Включите или отключите объявления о входе и выходе для собраний в Teams
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Администратор может узнать, как включить или отключить объявления о входе и выходе на собрании Microsoft Teams.
ms.openlocfilehash: 6be1c6dc86d8088b5ddb54b2141a10172ba13cc5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121337"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams

При настройке аудиоконференции в Microsoft 365 или Office 365 вы получите мост аудиоконференции. Мост конференц-связи может содержать один или несколько телефонных номеров, которые люди будут использовать для подключения к собранию Microsoft Teams по телефону.
  
Мост конференц-связи отвечает на звонок для пользователя, подключающегося к собранию по телефону. Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности. Организатору собрания Microsoft Teams выдается ПИН-код, позволяющий начать собрание, если это не удается сделать с помощью приложения Microsoft Teams. Однако вы можете настроить систему так, чтобы ПИН-код для начала собрания не требовался.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Настройка параметров присоединения к собранию

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

Вы должны быть администратором службы Teams, чтобы вносить эти изменения. Сведения о получении ролей и разрешений администратора см. в статье [Управление Teams с помощью ролей администратора Teams](./using-admin-roles.md).

1. Войдите в Центр администрирования.

2. На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.

3. В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.

4. В области **Настройки моста** включите или отключите **уведомления о входе на собрание и выходе из него**. Этот флажок установлен по умолчанию. Если его снять, пользователи, уже присоединившиеся к собранию, не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.

5. В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.

   > [!NOTE]
   > По умолчанию внешние участники не могут видеть телефонные номера участников телефонного звонка. Если необходимо соблюдать конфиденциальность этих номеров телефонов, выберите **Тональные сигналы** для пункта **Тип оповещения входа/выхода** (это позволяет предотвратить прочтение номеров приложением Teams).

6. Если вы выбрали **Имена или номера телефонов**, включите или отключите функцию **Попросить абонентов записывать свои имена перед присоединением к собранию**.

7. Нажмите кнопку **Сохранить**.

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.

- [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Связанные разделы

[Общие вопросы об аудиоконференциях](audio-conferencing-common-questions.md)