---
title: Включение и отключение входа и выхода из объявлений для собрания в Скайп для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включить запись и выхода из Включение и отключение оповещений в Скайп для бизнеса собрания с помощью Скайп по центру администрирования бизнес. '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490488"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Включение и отключение входа и выхода из объявлений для собрания в Скайп для бизнеса в Интернет

> [!Note]
> Сведения о входе и выходе участников в группами Майкрософт содержатся в разделе [Включение или отключение входе и выходе участников собраний в группах Microsoft](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

При установке аудиоконференций в Office 365, вы получите звукового конференц-канала. Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать вызывает Скайп для собраний. 
  
Мост конференц-связи ответы звонка для пользователя, который, к собрания с помощью телефона. Мост конференц-связи ответы вызывающего абонента с голосовые приглашения участников автосекретарь конференц-связи и затем, в зависимости от параметров, можно воспроизводить уведомления, попросите звонящих записать их имя и настройка безопасности ПИН-код. ПИН-код предоставляется Скайп для бизнеса Организатор собрания и позволяет им начало собрания, если они не может начать собрание, с помощью Скайп для бизнес-приложения. Тем не менее, устанавливать, чтобы ПИН-код не требуется для запуска собрания.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Настройка параметров присоединения к собранию
    
1. В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.
    
2. В разделе **при присоединении к собраниям**установите или снимите флажок **Включить запись собрание и выйти из уведомления, чтобы быть включенным**. Этот флажок установлен по умолчанию. Если снять, пользователей, которые уже присоединились к собранию не уведомления, когда кто-то или выходе из собрания.
    
3. В разделе **объявлений типа входа и выхода**выберите **имена или номера телефонов** или **тона**.
    
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

[Общие вопросы по аудиоконференциям](audio-conferencing-common-questions.md)
