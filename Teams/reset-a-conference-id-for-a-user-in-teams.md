---
title: Сброс идентификатора конференции для пользователя в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
- seo-marvel-mar2020
description: Описание шагов по сбросу идентификатора конференции для пользователя в Microsoft Teams, а также получения ссылок на средства для изменения и переноса собраний.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662129"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Сброс идентификатора конференции для пользователя в Microsoft Teams

Динамический идентификатор конференции указан в нижней части приглашений на собрания вместе с телефонными номерами, которые вызывающие абоненты могут использовать для подключения к собранию по телефону. Когда пользователь наберет этот телефонный номер, автосекретарь собрания попросит его ввести идентификатор конференции, чтобы присоединиться к собранию.
  
> [!NOTE]
> Коды конференций создаются автоматически, от 7 до 9 цифр и задаются при включлении аудиоконференции для пользователя. **Статические ИД конференции не поддерживаются.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Сброс ИД конференции для пользователя

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.

2. Нажмите **кнопку "Изменить".**

3. В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.

2. В окне **Сбросить идентификатор конференции** нажмите кнопку **Сброс**. Автоматически создается идентификатор конференции, после чего пользователю отправляется сообщение электронной почты с новым идентификатором. По умолчанию сообщения пользователям отправляются, но это можно отключить.   

    
> [!NOTE]
> После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. Во многих случаях это сообщение электронной почты отправляется на основной адрес электронной почты их почтового ящика Microsoft 365 или Office 365. Сообщение электронной почты содержит новый идентификатор конференции, номера для телефонного подключения по умолчанию и инструкции по изменению существующих собраний. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Что еще мне нужно знать?

- Всю информацию о конференц-связи, включая идентификатор конференции и номера для телефонного подключения, можно отправить пользователю по электронной почте, щелкнув элемент **Отправить сведения о конференции по эл. почте** в разделе **Аудиоконференции**. При этом ПИН-код не отправляется.
    
- Код конференции из 7–9 цифр создается службой Teams. Его длину изменить нельзя.
    
- После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.
    
- После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Связанные разделы

[Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md)
