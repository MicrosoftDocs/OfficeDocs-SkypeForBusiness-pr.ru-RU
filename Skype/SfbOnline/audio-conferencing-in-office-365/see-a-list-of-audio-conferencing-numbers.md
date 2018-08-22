---
title: Список номеров аудиоконференции в Скайп для бизнеса в Интернет
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: 'Узнайте, как для поиска номерам конференц-связь в пределах Скайп для бизнеса в Интернет. '
ms.openlocfilehash: 84d6f4d1d1d1358a62ec8d0eb2334c92c416adea
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490598"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Список номеров аудиоконференции в Скайп для бизнеса в Интернет

> [!NOTE]
> Сведения о номерах аудиоконференции в группах Microsoft [перечень аудиоконференции номеров в группах Microsoft](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)см.

При настройке аудиоконференций для Скайп для бизнес-пользователей, можно просмотреть номера телефонов, им доступны для аудиоконференций. Этот список будет содержать все номера телефонов аудиоконференций, доступных для вашей организации.
  
 **Ищете цены?** В разделе [ценообразования для аудиоконференций](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону.** Если вы хотите узнать, если существует телефонные номера телефонов в области или страны или региона, перейдите к **Скайп по центру администрирования Business** > **голосовой связи** > **Телефонных номеров**, нажмите кнопку **Добавить**и нажмите кнопку **новую службу Номера**. Для фильтрации поиска воспользуйтесь списками **Страна или регион**, **Область** и **Город**. Кроме того, если вы ищете службы бесплатных номеров, выберите **бесплатный номер** из **состояние и область** списка.
  
Если в организации имеется только один телефонный номер, он будет использоваться как значение по умолчанию для всех пользователей. Если доступно несколько телефонных номеров, можно выбрать номер телефона по умолчанию для каждого пользователя. Этот номер по умолчанию будут включены в Скайп Business приглашения на собрания.
  
Вы можете увидеть [задать телефона, приглашает номера, находящимся на](set-the-phone-numbers-included-on-invites.md) для изменения номера телефона-связи для одного пользователя.
  
> [!NOTE]
> Внутренние телефонных номеров выделенным для вашей организации и являются единственными, которые могут быть заданы как номер телефона по умолчанию. Тем не менее международных телефонных номеров может совместно использоваться несколькими организациями. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Чтобы просмотреть номера телефонов аудиоконференций

1. Sign in to Office 365 with your work or school account.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **Microsoft bridge**, а затем:
    
  - Вы можете просмотреть номера телефонов, которые доступны для аудиоконференций.
    
  - Также можно увидеть местоположение и основных и дополнительных языков, которые будут использоваться звукового конференц-связи, принимаемые автосекретарем.
    
> [!NOTE]
> Можно перейти к **аудиоконференции** > **пользователей** и выберите Свойства пользователя, чтобы изменить значение по умолчанию, какой номер, выбрав новый номер из списка доступных номеров в вашей организации. В разделе [Задайте телефона, номера, находящимся на приглашает](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) .
    
- Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
