---
title: Видеть, изменение и сброс идентификатор конференции, назначенных пользователю
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как назначить пользователю в Скайп для бизнеса идентификатор конференции и какие конференции идентификатор приложения-службы должны быть параметров. '
ms.openlocfilehash: 4922f896daa2bec976d7fb72dd519e9dd91d74f4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>Видеть, изменение и сброс идентификатор конференции, назначенных пользователю

Идентификатор конференц-связи автоматически назначается Скайп для пользователя Business или группами Майкрософт, если они зависят от выбора звукового конференц-связи в Office 365 и использовать Microsoft в качестве поставщика аудиоконференций. Идентификатор конференции, назначенный отправляется в приглашении на собрание, при планировании собрания. Каждое собрание, который пользователь планирует будет присваивает идентификатор уникальный конференции. 
  
Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или при пользователи не могут не забудьте или теряют их идентификатор конференции. **Скайп по центру администрирования бизнеса** и Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.
  
Сообщения электронной почты будут отправляться пользователю с идентификатор конференции и телефонных номеров конференции по умолчанию, или если сбросить идентификатор конференции разных электронной почты будут отправлены, что будут включать идентификатор конференции, но не ПИН-кода. Дополнительные сведения о сброс ПИН-кода инициатора конференции, [Перейдите сюда](reset-a-conference-id-for-a-user.md). 
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-view-and-change-conference-ids"></a>![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) Просмотр и изменение конференции идентификаторы

### <a name="to-view-the-conference-id"></a>Чтобы просмотреть идентификатор конференции

Можно просматривать их идентификатор конференции и отправьте его для пользователей.
  
1. Sign in to Office 365 with your work or school account.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, выберите пользователя, которому требуется идентификатор конференции.
    
4. На странице "действия" найдите в разделе **Идентификатор конференции**.
    
    > [!TIP]
    > Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и звуковых телефонных номеров, щелкнув ссылку **Отправить сведения о конференции по электронной почте** , после выбора пользователя на странице " **Пользователи** ".
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Windows PowerShell можно использовать для просмотра идентификатор конференции для пользователя. Для этого выполните следующую команду:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
### <a name="to-assign-or-change-the-conference-id"></a>Чтобы назначить или изменить идентификатор конференции

Можно назначить или изменить идентификатор конференции для пользователя, если, например, кто-то хочет идентификатор конференции, который легко запомнить.

  > [!NOTE]
  > Скайп по центру администрирования бизнес не может использоваться для изменения идентификатора конференции, который автоматически создается, но можно использовать Windows PowerShell для изменения или измените идентификатор конференции, задания. 
     
Чтобы изменить или идентификатор конференции для пользователя, выполните следующую команду:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > Идентификатор конференции должен содержать 7 символов, и его нельзя изменить в Скайп для бизнеса центра администрирования или с помощью Windows PowerShell. 
  
### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-to-reset-the-conference-id"></a>![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) Чтобы сбросить идентификатор конференции

Можно восстановить идентификатор конференции для пользователя, если, например, если они забыли.
  
1. Sign in to Office 365 with your work or school account.
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, в области действий в разделе **Идентификатор конференции**, нажмите кнопку **Сброс**.
    
4. В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    Можно восстановить идентификатор конференции для пользователя с помощью Windows PowerShell. Для этого выполните команду:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Дополнительные сведения

   > [!IMPORTANT]
   >  После создания новый идентификатор или один сбрасывается, старый идентификатор конференции не может использоваться с абонентов. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний. Чтобы узнать, как загрузить, установить и запустить средство, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](http://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, средство миграции собрания (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.
    
- Идентификатор конференции должны соответствовать длина цифрами на звукового конференц-канала. Нельзя использовать буквы или специальных символов в конференции идентификаторы; можно использовать только цифры.
    
- Идентификатор конференции для всех пользователей аудиоконференций будет 7 символов по умолчанию, и количество знаков, нельзя изменить.
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Пробная и платная аудиоконференции в Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

