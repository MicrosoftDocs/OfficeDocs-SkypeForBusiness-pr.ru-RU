---
title: Настройка номеров телефонов, включенных в приглашения в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 7136a8108a5ecd9e55d2def1e4cedd1076b270ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729058"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Настройка номеров телефонов, включенных в приглашения в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Сведения о номерах телефонов для приглашения на собрание в Microsoft Teams см. в этой [Microsoft Teams.](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)

Аудиоконференция в Microsoft 365 или Office 365 позволяет пользователям в организации создавать собрания Skype для бизнеса, а затем звонить на них по телефону. В Microsoft 365 и Office 365 вы можете использовать мост аудиоконференций Майкрософт или сторонний мост аудиоконференций, который находится у утвержденного поставщика аудиоконференций (ACP).
  
> [!NOTE]
> Не существует никакого ресурса, который содержит список всех номеров для аудиоконференций с подключением по телефону. Если вы хотите узнать, есть ли телефонные номера для телефонного звонка, доступные в вашем регионе или вашей стране или регионе, используйте центр администрирования **Skype для бизнеса**  >  **Голосовая** Телефон  >  **номера**,  нажмите кнопку Добавить, а затем — Новые номера служб. Для фильтрации поиска используйте списки  страна **или** **регион,** область или регион и город.> Кроме того,  если вы ищете бесплатные номера служб, выберите Бесплатный в списке Область **или** регион.
  
Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.
  
> [!NOTE]
> Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Настройка номера телефона для телефонного звонка по умолчанию для организатора собрания

1. Во войти с помощью своей учебной или учебной учетной записи.
    
2. Выберите **Центры администрирования** > **Skype для бизнеса**.
    
3. Выберите **Пользователи**.
    
    ![Выбор пользователей в центре Skype для бизнеса администрирования.](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Выберите пользователей, которые вы хотите изменить.
    
   - Чтобы выбрать одного пользователя, выберите его имя.
    
   - Чтобы выбрать всех пользователей на странице, выберите поле Отображаемая **имя** в верхней части списка.
    
   - Чтобы выбрать несколько пользователей, выберите поле рядом с именем каждого из них.
    
5. В области справа выберите **Изменить**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Выберите **аудиоконференцию**.
    
7. На странице **Свойства** в списке **Имя поставщика** выберите поставщика для пользователя. В зависимости от выбранного поставщика заполните следующие поля.
    
   - **Майкрософт — поставщик.**  Используйте списки  Платный номер по умолчанию и Бесплатный номер по умолчанию, чтобы выбрать номера по умолчанию для пользователя.
    
     > [!NOTE]
     > Прежде чем мост конференц-связи может быть задан как бесплатный номер по умолчанию для пользователей, ему следует назначить хотя бы один бесплатный номер. Чтобы получить бесплатный номер, см. получение [номеров](/microsoftteams/getting-service-phone-numbers)телефонов служб для Skype для бизнеса. 
  
   - **Сторонний поставщик — это** поставщик: введите номера для пользователя с помощью полей Платный номер и Бесплатный номер.  


## <a name="reset-audio-conferencing-phone-numbers"></a>Сброс номеров доступа к конференции с телефонным подключением

1. В **Центр администрирования Skype для бизнеса** выберите **Аудиоконференция**.
    
2. В верхней части страницы щелкните **Пользователи**.
    
3. Выберите пользователей, которые вы хотите сбросить, а затем в области действий нажмите кнопку **Очистить**.
    
По умолчанию при изменении параметров для пользователя для настройки параметров conferencing пользователю отправляется сообщение электронной почты. Чтобы изменить это, см. параметр Включить или отключить отправку сообщений электронной почты при изменении параметров [аудиоконференции.](enable-or-disable-sending-emails-when-their-settings-change.md)
  
> [!IMPORTANT]
> При изменении параметров аудиоконференции пользователя повторяющиеся и будущие собрания Skype для бизнеса должны быть обновлены и отправлены участникам. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Сведения по управлению с помощью Windows PowerShell

- Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Используйте командлет [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) для изменения платного или бесплатного номера по умолчанию для определенных пользователей.
    
    Чтобы изменить бесплатный номер по умолчанию для определенного пользователя, выполните командлет
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Используйте командлет **Set-CsOnlineDialInConferencingUserDefaultNumber** для изменения платного или бесплатного номера по умолчанию для пользователей на основе исходного номера по умолчанию, свойственного для местоположения этих пользователей.
    
    > [!NOTE]
    > Чтобы найти код BridgeID, используйте **cmdlet Get-CsOnlineDialInConferencingBridge.**
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, не имеющих номера по умолчанию, выполните командлет
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Чтобы изменить бесплатный номер по умолчанию для всех пользователей с бесплатным номером по умолчанию +18005551234 на +18005551239, выполните командлет
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Чтобы задать бесплатный номер +18005551234 в качестве номера по умолчанию для всех пользователей, расположенных в США, выполните командлет
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?
- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Зачем нужно использовать Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центр администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Статьи по теме

[Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
