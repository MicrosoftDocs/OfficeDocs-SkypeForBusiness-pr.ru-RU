---
title: Сброс ИД конференции для пользователя в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как сбросить ИД конференции пользователя в Skype для бизнеса Online и получить ссылки на средства обновления собраний и миграции. '
ms.openlocfilehash: 24037de3849ae54920777636e7eb745671ae2f57
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237775"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Сброс ИД конференции для пользователя в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Сведения о сбросе ИД конференции в Microsoft Teams см. в этой [Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)

Динамический ИД конференции включается в нижней части приглашений на собрание, а также номера телефонов для телефонного звонка, которые могут использоваться звоня на собрание. Когда пользователь наберет номер телефона, автозаводщик собрания попросит вызывающего пользователя ввести этот номер конференции, чтобы он принял участие в собрании.
  
> [!NOTE]
> Если вашим поставщиком конференц-связи является корпорация Майкрософт, для ваших пользователей задайте только динамические ID-записи конференций. Эта настройка не может быть изменена. ИД конференции автоматически устанавливаются только для пользователей Skype для бизнеса для аудиоконференции. 

## <a name="resetting-the-conference-id-for-a-user"></a>Сброс ИД конференции для пользователя
   
1. В Центре **Skype для бизнеса** щелкните Пользователи аудиоконференции , выберите пользователя, а затем в области действий в области "ИД конференции" нажмите  >  кнопку **Сброс**. 
    
2. В **окне Сбросить ИД конференции?** нажмите кнопку **Да.** A conference ID will be automatically created and an email sent to the user with the new conference ID. По умолчанию сообщения отправляются пользователям, но это можно отключить.
    
> [!NOTE]
> После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции. Во многих случаях это сообщение отправляется на основной адрес электронной почты Microsoft 365 или Office 365 почтовый ящик. Сообщение электронной почты содержит новый идентификатор конференции, номера телефонов для телефонного подключения по умолчанию и инструкции по использованию средства обновления для собраний Skype для бизнеса. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Дополнительные сведения

- Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и  телефонные номера для телефонного звонка, щелкнув Отправить сведения о конференции по электронной почте пользователю в области действий. ПИН-код не отправляется.
    
- ИД конференции будет содержать 7 цифр, и вы не сможете изменить его длину в центре администрирования Skype для бизнеса или с помощью Windows PowerShell.
    
- После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.
    
- При выборе пользователя на странице Пользователи в нижней части области действий можно просмотреть ИД конференции для пользователя для  аудиоконференции. 
    
- После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Пользователи могут использовать Skype для бизнеса собраний для обновления существующих собраний. Чтобы узнать, как скачать, установить и запустить средство обновления Skype для бизнеса собраний, см.:
    
  - [Средство обновления для собраний Skype для бизнеса и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype для бизнеса Online, инструмент переноса собраний (64-разрядная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype для бизнеса Online, инструмент переноса собраний (32-разрядная версия)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме

[Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin.md)
