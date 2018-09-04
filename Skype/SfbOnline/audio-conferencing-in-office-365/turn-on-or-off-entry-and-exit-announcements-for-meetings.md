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
description: 'Узнайте, как включать и выключать уведомления о входе и выходе из собраний Skype для бизнеса Online с помощью центра администрирования Skype для бизнеса. '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779038"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Включение и отключение уведомлений о входе и выходе из собраний в Skype для бизнеса Online

> [!Note]
> Информацию об уведомлениях о входе и выходе в Microsoft Teams см. в статье [Включение или отключение уведомлений о входе и выходе из собраний в Microsoft Teams](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams).

При установке аудиоконференций в Office 365, вы получите аудио-конференц-канал. Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать для звонков на собрание Skype для бизнеса. 
  
Конференц-канал отвечает на звонок пользователя, подключающегося к собранию с помощью телефона. Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности. ПИН-код предоставляется организатору собрания Skype для бизнеса и позволяет ему начать собрание, если он не может начать собрание с помощью приложения Skype для бизнеса. Тем не менее, вы можете настроить работу приложения так, чтобы ПИН-код не требовался, чтобы начать собрание.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Настройка параметров присоединения к собранию
    
1. В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Аудиоконференция с телефонным подключением** > **Параметры моста Microsoft**.
    
2. В разделе **При присоединении к собраниям**установите или снимите флажок **Разрешить включение уведомлений о входе и выходе из собрания**. Данная опция включена по умолчанию. Если снять этот флажок, то пользователи, которые уже присоединились к собранию, не получат уведомления о присоединении или выходе из него других участников.
    
3. В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.
    
4. Установите или снимите флажок **Просить абонентов записывать свое имя перед присоединением к собранию**.
    
5. После внесения изменений нажмите кнопку **Сохранить**.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Можно сэкономить время и автоматизировать процесс, используя командлет [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps).
    
-  Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Почему следует использовать Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ по скорости, простоте и производительности по сравнению с использованием только центра администрирования Office 365, например, когда выполняются изменения параметров для нескольких пользователей сразу. Подробнее об этих преимуществах можно узнать в следующих разделах: 
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Связанные разделы

[Общие вопросы по аудиоконференциям](/MicrosoftTeams/audio-conferencing-common-questions)
