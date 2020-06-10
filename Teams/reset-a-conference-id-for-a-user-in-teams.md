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
ms.openlocfilehash: fbda2d65868d9f4082ae7b3ee835d0560c609e11
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666201"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Сброс идентификатора конференции для пользователя в Microsoft Teams

Динамический идентификатор конференции указан в нижней части приглашений на собрания вместе с телефонными номерами, которые вызывающие абоненты могут использовать для подключения к собранию по телефону. Когда пользователь наберет этот телефонный номер, автосекретарь собрания попросит его ввести идентификатор конференции, чтобы присоединиться к собранию.
  
> [!NOTE]
> Если вашим поставщиком услуг конференц-связи является корпорация Майкрософт, для идентификаторов конференции ваших пользователей по умолчанию задано значение Dynamic Only (Только динамические). К сожалению, нет никакой возможности сделать их статическими, так как сейчас эта функция не поддерживается. Идентификаторы конференции автоматически задаются только для пользователей Microsoft Teams, для которых включена поддержка аудиоконференций. 


## <a name="resetting-the-conference-id-for-a-user"></a>Сброс идентификатора конференции для пользователя

![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**

1. На панели навигации слева выберите пункт **Пользователи**, а затем выберите пользователя из списка доступных пользователей.

2. Нажмите кнопку **изменить**.

3. В разделе **Голосовая конференция** выберите **Сброс идентификатора конференции**.

2. В окне **Сброс идентификатора конференции** нажмите кнопку **Сброс**. A conference ID will be automatically created and an email sent to the user with the new conference ID. По умолчанию сообщения электронной почты отправляются пользователям, но их можно отключить.   

    
> [!NOTE]
> После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. Это сообщение будет отправлено на основной адрес электронной почты, во многих случаях — в почтовом ящике Microsoft 365 или Office 365. Сообщение электронной почты с новым ИДЕНТИФИКАТОРом конференции, номерами телефонов для подключения по умолчанию и инструкциями по обновлению существующих собраний. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Дополнительные сведения

- Вы можете отправить всем сведения о конференциях в сообщение электронной почты, содержащее идентификатор конференции и номера для телефонного подключения, нажав кнопку **отправить сведения о конференции по электронной почте** для пользователя в разделе " **звуковые конференции** ". ПИН-код не отправляется.
    
- Идентификатор конференции будет содержать 8 цифр, и его длину изменить нельзя.
    
- После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.
    
- После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Связанные разделы

[Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md)
