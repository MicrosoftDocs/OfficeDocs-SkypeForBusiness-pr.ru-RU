---
title: Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включать и выключать уведомления о входе и выходе из собраний Skype для бизнеса Online с помощью центра администрирования Skype для бизнеса. '
ms.openlocfilehash: b00c52d905fb031c7f0eaebc57f9fbb88549daa0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884063"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online

> [!Note]
> Информацию об уведомлениях о входе и выходе в Microsoft Teams см. в статье [Включение или отключение уведомлений о входе и выходе из собраний в Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

При установке аудиоконференций в Office 365, вы получите аудио-конференц-канал. Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать для звонков на собрание Skype для бизнеса. 
  
Конференц-канал отвечает на звонок пользователя, подключающегося к собранию с помощью телефона. Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности. ПИН-код предоставляется организатору собрания Skype для бизнеса и позволяет ему начать собрание, если он не может начать собрание с помощью приложения Skype для бизнеса. Тем не менее, вы можете настроить работу приложения так, чтобы ПИН-код не требовался, чтобы начать собрание.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Настройка параметров присоединения к собранию
    
1. В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.
    
2. В разделе **при присоединении к собраниям**установите или снимите флажок **Включить запись собрание и выйти из уведомления, чтобы быть включенным**. Данная опция включена по умолчанию. Если снять, пользователей, которые уже присоединились к собранию не уведомления, когда кто-то или выходе из собрания.
    
3. В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.
    
4. Установите или снимите флажок **задать абонентов записать их имя перед присоединением к собранию**.
    
5. После внесения изменений нажмите кнопку **Сохранить**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) .
    
-  Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, когда выполняются изменения параметров для нескольких пользователей за один раз. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>See also

[Общие вопросы по аудиоконференциям](/MicrosoftTeams/audio-conferencing-common-questions)
