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
description: Узнайте, как назначить, изменить или удалить рабочий номер телефона для пользователей Teams, чтобы внешние организации и клиенты могли звонить.
ms.openlocfilehash: 0dd126f3aa19e0b65b7a0c789f769cef1803f8c8
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414687"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Назначение, изменение и удаление номера телефона пользователя

При настройке тарифных планов, оператора Connect или Мобильного телефона Teams вы назначаете своим пользователям телефонные номера. В Майкрософт Teams назначенный номер телефона отображается, когда пользователь нажимает кнопку **"Звонки**".

Эта статья относится к тарифным планам, оператору Connect и Мобильной связи Teams. Сведения о назначении, изменении или удалении номера телефона пользователя в сценарии прямой маршрутизации см. в статье [Включение прямой маршрутизации пользователей для прямой маршрутизации, голосовой связи и голосовой почты](./direct-routing-enable-users.md).

Прежде чем назначить номер для пользователя плана звонков, оператора Connect или мобильного телефона Teams, необходимо получить номера для пользователей. Дополнительные сведения см. в [разделах Получение номеров для пользователей плана звонков](getting-phone-numbers-for-your-users.md), [Настройка номеров для пользователей Оператора Connect](operator-connect-configure.md#set-up-phone-numbers) или [Настройка номеров для пользователей Teams Phone Mobile](operator-connect-mobile-configure.md).

> [!NOTE]
> Один из способов узнать, назначена ли пользователю лицензия, — перейти в Центр администрирования Майкрософт Teams > **пользователи**. Если лицензия назначена, она будет указана на странице.  Вы также можете использовать Центр администрирования Microsoft 365.

> [!NOTE]
> Это примечание относится к клиентам, которые имеют гибридное развертывание с локальная служба Active Directory. Если вы хотите назначить пользователю или учетной записи ресурса номер телефона плана звонков или оператора Connect, необходимо убедиться, что любой номер телефона, хранящийся в атрибуте msRTCSIP-Line в объекте учетной записи пользователя или ресурса в локальная служба Active Directory, удален, а изменения синхронизированы с Майкрософт 365.

## <a name="assign-a-phone-number-to-a-user"></a>Назначение номера телефона пользователю

При назначении номера телефона пользователю убедитесь, что номер телефона и место использования пользователя находятся в одной стране.

Чтобы назначить номер с помощью Центра администрирования Teams, выполните следующие действия:

[!INCLUDE [assign-phone-numbers-to-users-steps](./includes/assign-phone-numbers-to-users-steps.md)]


Чтобы назначить номера с помощью PowerShell, используйте командлет [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) следующим образом:

Для номеров плана звонков:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Для номеров Оператор Connect:

```PowerShell
Set-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Для телефонных номеров Teams:

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
> Из-за задержки между Майкрософт 365 и Teams для включения пользователей может потребоваться до 24 часов. Если номер телефона не назначен правильно через 24 часа, см. раздел [Центр обслуживания номеров телефонов](https://pstnsd.powerappsportals.com/).

> [!NOTE]
> При назначении номера телефона для флага EnterpriseVoiceEnabled автоматически устанавливается значение True.

## <a name="change-a-phone-number-for-a-user"></a>Изменение номера телефона пользователя

Чтобы изменить номер телефона пользователя с помощью Центра администрирования Teams, выполните следующие действия:

1. В области навигации слева щелкните **Пользователи**, найдите и дважды щелкните нужного пользователя, щелкните **Учетная запись**, а затем в разделе **Общие сведения** запишите номер телефона, назначенный пользователю.

2. В области навигации слева щелкните **Номера голосовых** \> **телефонов**.

3. На странице **Номера телефонов** выберите номер, указанный на шаге 1, и нажмите кнопку **Изменить**.

4. В области **Правка** в разделе **Назначено** щелкните **X** , чтобы удалить пользователя.

5. Нажмите кнопку **Сохранить**.

6. На странице **Номера телефонов** выберите в списке неназначаемый номер и нажмите кнопку **Изменить**.

7. В области **Правка** в разделе **Назначено** найдите пользователя по отображаемому имени или имени пользователя, а затем нажмите кнопку **Назначить**.

8. Чтобы назначить или изменить связанное расположение для аварийного реагирования, в разделе **Расположение для экстренного** реагирования найдите и выберите расположение.

      > [!NOTE]
      > Если вы изменяете номера для пользователей Оператор Connect или Teams Phone Mobile, вы можете назначить или изменить соответствующее место для экстренного реагирования. Эта функция будет зависеть от оператора. За дополнительными сведениями обратитесь к оператору.

9. Нажмите кнопку **Сохранить**.

Пример PowerShell см. в разделе [Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment).

## <a name="remove-a-phone-number-from-a-user"></a>Удаление номера телефона пользователя

Чтобы удалить номер телефона с помощью Центра администрирования Teams, выполните следующие действия:

1. В области навигации слева щелкните **Пользователи**, найдите и дважды щелкните нужного пользователя, щелкните **Учетная запись**, а затем в разделе **Общие сведения** запишите номер телефона, назначенный пользователю.

2. В области навигации слева щелкните **Номера голосовых** \> **телефонов**.

3. На странице **Номера телефонов** выберите номер, указанный на шаге 2, и нажмите кнопку **Изменить**.

4. В области **Правка** в разделе **Назначено** щелкните **X** , чтобы удалить пользователя.

5. Нажмите кнопку **Сохранить**.

Пример PowerShell см. в разделе [Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment).

## <a name="related-topics"></a>См. также

[Что такое проверка адреса?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Управление номерами телефонов для организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)

[Метка заявления об отказе от ответственности для экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)
