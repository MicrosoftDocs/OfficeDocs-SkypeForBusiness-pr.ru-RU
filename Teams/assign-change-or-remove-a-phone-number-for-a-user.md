---
title: Назначение, изменение и удаление номера телефона пользователя
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Узнайте, как назначать, изменять или удалять рабочий номер телефона для пользователей Teams, чтобы внешние компании и клиенты могли выполнять звонки.
ms.openlocfilehash: d26df14f2f75e205c1824b66c9b8f2f394972d43
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551663"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Назначение, изменение и удаление номера телефона пользователя

При настройке планов звонков, Operator Connect или Teams Phone Mobile пользователям назначаются номера телефонов. В Microsoft Teams номер телефона, который вы назначаете, отображается при нажатии пользователем кнопки "Звонки **"**.

Эта статья относится к тарифным планам, Operator Connect и Teams Phone Mobile. Сведения о назначении, изменении или удалении номера телефона пользователя в сценарии прямой маршрутизации см. в разделе "Включение прямой маршрутизации, голосовой почты и [голосовой](./direct-routing-enable-users.md) почты для пользователей".

Перед назначением номера для тарифного плана, оператора Connect или мобильного пользователя Teams Phone необходимо получить номера для пользователей. Дополнительные сведения см. в статьях "Получение номеров для пользователей плана звонков [", "](getting-phone-numbers-for-your-users.md)Настройка номеров для пользователей [Operator Connect](operator-connect-configure.md#set-up-phone-numbers)" или "Настройка номеров для [пользователей Teams Phone Mobile"](operator-connect-mobile-configure.md).

> [!NOTE]
> Чтобы узнать, назначена ли пользователю лицензия, перейдите в Центр администрирования Microsoft Teams > **Users**. Если лицензия назначена, она будет указана на странице.  Вы также можете использовать Центр администрирования Microsoft 365.

> [!NOTE]
> Это примечание относится к клиентам с гибридным развертыванием с локальная служба Active Directory. Если вы хотите назначить план звонков или номер телефона оператора Connect пользователю или учетной записи ресурса, необходимо убедиться, что любой номер телефона, хранимый в атрибуте msRTCSIP-Line в объекте учетной записи пользователя или ресурса в локальная служба Active Directory, был удален, а изменение синхронизировано с Microsoft 365.

## <a name="assign-a-phone-number-to-a-user"></a>Назначение номера телефона пользователю

При назначении пользователю номера телефона убедитесь, что номер телефона и расположение использования пользователя находятся в одной стране.

Чтобы назначить номер с помощью Центра администрирования Teams:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Чтобы назначить числа с помощью PowerShell, используйте командлет [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) следующим образом:

Для номеров планов звонков:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Для номеров Operator Connect:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Для мобильных номеров телефонов Teams:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OCMobile
```

Например:

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550103" -PhoneNumberType OCMobile
```







> [!NOTE]
> Из-за задержки между Microsoft 365 и Teams для включения пользователей может потребоваться до 24 часов. Если номер телефона не назначен правильно через 24 часа, см. раздел ["Центр обслуживания номеров телефонов"](https://pstnsd.powerappsportals.com/).

## <a name="change-a-phone-number-for-a-user"></a>Изменение номера телефона для пользователя

Чтобы изменить номер телефона пользователя с помощью Центра администрирования Teams, скажите следующее:

1. В области навигации слева щелкните "Пользователи **", найдите** и дважды щелкните нужного пользователя, выберите "Учетная запись **", а** затем в разделе "Общие сведения" запишите номер телефона, назначенный пользователю.

2. В области навигации слева щелкните номера **голосовых** \> **телефонов**.

3. На странице **"Номера телефонов** " выберите номер, указанный на шаге 1, и нажмите кнопку "Изменить **"**.

4. В области **правки** в **разделе "Назначено**" щелкните **значок X** , чтобы удалить пользователя.

5. Нажмите кнопку **Сохранить**.

6. На странице **"Номера телефонов** " выберите неназначенных номеров в списке и нажмите кнопку "Изменить **"**.

7. В области **"** Правка" в разделе **"** Назначено" найдите пользователя по отображаемого имени или имени пользователя, а затем нажмите кнопку **"Назначить"**.

8. Чтобы назначить или изменить связанное местоположение для экстренного реагирования, в разделе "Местоположение для экстренного **реагирования**" найдите и выберите расположение.

      > [!NOTE]
      > Если вы изменяете номера для пользователей Operator Connect или Teams Phone Mobile, вы можете или не сможете назначить или изменить связанное местоположение для экстренного реагирования. Эта функция будет зависеть от оператора. Для получения дополнительных сведений обратитесь к оператору.

9. Нажмите кнопку **Сохранить**.

Пример PowerShell см. в [разделе Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Удаление номера телефона пользователя

Чтобы удалить номер телефона с помощью Центра администрирования Teams, скажите следующее:

1. В области навигации слева щелкните "Пользователи **", найдите** и дважды щелкните нужного пользователя, выберите "Учетная запись **", а** затем в разделе "Общие сведения" запишите номер телефона, назначенный пользователю.

2. В области навигации слева щелкните номера **голосовых** \> **телефонов**.

3. На странице **"Номера телефонов** " выберите номер, указанный на шаге 2, и нажмите кнопку "Изменить **"**.

4. В области **правки** в **разделе "Назначено**" щелкните **значок X** , чтобы удалить пользователя.

5. Нажмите кнопку **Сохранить**.

Пример PowerShell см. в [разделе Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>См. также

[Что такое проверка адреса?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Управление номерами телефонов для организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)

[Метка заявления об отказе от экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
