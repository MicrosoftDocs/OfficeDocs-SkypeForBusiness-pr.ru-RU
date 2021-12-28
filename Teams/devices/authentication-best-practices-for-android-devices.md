---
title: Лучшие методики проверки подлинности для устройств с Android
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 12/16/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Руководство по проверке подлинности Teams устройств с Android.
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ffa30efd7f122b6d95c4545dd2d2517f3669472
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2021
ms.locfileid: "61576169"
---
# <a name="authentication-best-practices-for-teams-android-devices"></a>Лучшие методики проверки подлинности Teams устройствах с Android

В этой статье приводится общее руководство и рекомендации по развертыванию политик проверки подлинности для Teams телефонов и устройств для звонков.

>[!NOTE]
>Для условного доступа требуется подписка Azure Active Directory (Azure AD) Premium подписка.

>[!NOTE]
>Политики для мобильных устройств с Android могут не применяться Teams устройствах Android.


## <a name="personal-and-shared-devices"></a>Личные и общие устройства

Общие Teams, такие как устройства комнаты собраний или обычные телефоны, не могут использовать те же требования для регистрации и соответствия требованиям, которые обычно применяются к личным устройствам. Применение требований к проверке подлинности личных устройств к общим устройствам приведет к следующим проблемам со входом:

1.  **Устройства вышли из-за политик паролей**

Для учетных записей, Teams устройствах, применяется политика срока действия паролей. В отличие от пользователей, учетные записи, используемые с общими устройствами, не назначены пользователям для обновления и восстановления их в допустимом состоянии по истечении срока действия паролей. Если вашей организации требуется периодически сбрасывать пароли, эти учетные записи перестанут работать на Teams устройствах, пока администратор Teams не сбросит пароль и не вернется в учетную запись.

2.  **Устройства не могут войти из-за политик условного доступа**

Общие устройства не соответствуют политикам условного доступа Azure AD для учетных записей пользователей и личных устройств. Если общие устройства сгруппировали с учетными записями пользователей или личными устройствами для политики условного доступа, вход в учетную запись не удастся войти.

Например, если для доступа к учетной записи требуется многофакторная проверка подлинности, Teams, для завершения проверки подлинности требуется вмешательства пользователя. Общие устройства не поддерживают многофакторную проверку подлинности. Аналогичным образом, если учетная запись настроена на повторное просмотр каждые X дней, общее устройство не сможет устранить проблему без вмешательства пользователя.

## <a name="best-practices-for-teams-shared-device-deployments"></a>Лучшие методики для развертывания Teams устройств с общим доступом

Корпорация Майкрософт рекомендует следующие параметры при развертывании Teams в организации.

### <a name="password-policy"></a>**Политика паролей**

Teams общие устройства должны использовать учетную [запись Exchange ресурса.](/exchange/recipients-in-exchange-online/manage-resource-mailboxes) Эти учетные записи можно синхронизировать из Active Directory или создать непосредственно в Azure AD. Любые политики срока действия паролей для пользователей также применяются к учетным Teams устройств.

Чтобы избежать сбоев, вызванных политиками срока действия паролей, установите политику срока действия паролей для общих устройств так, чтобы она никогда не истекла.

Начиная с Teams устройств CY21 [Update #1](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Desk_phones) (Teams версии 1449/1.0.94.2021022403 для телефонов Teams) и [CY2021 Обновление No 2](https://support.microsoft.com/office/what-s-new-in-microsoft-teams-devices-eabf4d81-acdd-4b23-afa1-9ee47bb7c5e2#ID0EBD=Teams_Rooms_on_Android) (Teams версии 1449/1.0.96.2021051904 для Комнаты Microsoft Teams на Android) администраторы клиентов могут войти в Teams устройства удаленно. Не делитесь паролями со специалистами по настройкам устройств. Администратор может использовать удаленный вход для проверки кодов, а затем войти в эти устройства из Teams администрирования.

Дополнительные сведения см. в документе Удаленная подготовка и вход [Teams устройствах с Android.](/MicrosoftTeams/devices/remote-provision-remote-login) 

### <a name="conditional-access-policies"></a>**Политики условного доступа**

Условный доступ Azure AD задает дополнительные требования, которые должны соответствовать устройствам для регистрации. Если Teams устройств, просмотрите следующие рекомендации, чтобы определить, были ли вы авторами соответствующих политик. Общие сведения об условном доступе см. в статью [Что такое Условный доступ.](/azure/active-directory/conditional-access/overview)

### <a name="multi-factor-authentication"></a>Многофакторная проверка подлинности

Учетные записи общих устройств связаны с комнатой или физическим пространством, а не с учетной записью пользователя. Так как общие устройства не поддерживают многофакторную проверку подлинности, исключить их из политик многофакторной проверки подлинности.

>[!TIP]
>Используйте [именоватое расположение](/azure/active-directory/conditional-access/location-condition) [или требуть устройства, которое соответствует](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device) требованиям, для защиты общих устройств.

### <a name="location-based-access-with-named-locations"></a>Доступ на основе расположения с именоваными расположениями

Если общие устройства находятся в определенном расположении, которое можно определить с диапазоном IP-адресов, вы можете настроить условный доступ, используя именоваемые расположения для этих устройств. [](/azure/active-directory/conditional-access/location-condition) Это условное условие позволит таким устройствам получать доступ к корпоративным ресурсам только в том случае, если они находятся в вашей сети.

### <a name="require-compliant-device"></a>Требование устройства, которое соответствует требованиям

>[!NOTE]
>Для соблюдения требований к устройствам требуется лицензия Intune.

Если вы регистр хотите зарегистрировать общие устройства в Intune, вы можете настроить соответствие устройства требованиям в качестве средства контроля в Условном доступе, чтобы доступ к корпоративным ресурсам могли получить только устройства, которые соответствуют требованиям. Teams можно настроить политики условного доступа на основе соответствия требованиям. Дополнительные сведения см. в теме [Условный доступ: требуется соответствие](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)требованиям или гибридное присоединенное устройство Azure AD.

Чтобы настроить параметры соответствия для ваших устройств с помощью Intune, см. использование политик соответствия для настройки правил для устройств, управляемых [с помощью Intune.](/intune/protect/device-compliance-get-started)

>[!NOTE]
> Общие устройства, используемые для использования hotdesking, следует исключить из политик соответствия требованиям. Согласно требованиям устройства не могут быть зарегистрированы в учетной записи пользователя службы поддержки. Вместо этого используйте именованые расположения для защиты этих устройств.
> Для повышения безопасности в [](/azure/active-directory/authentication/tutorial-enable-azure-mfa) дополнение к политикам расположения может потребоваться многофакторная проверка подлинности для пользователей службы поддержки.

### <a name="sign-in-frequency"></a>Частота входов

В условном доступе [](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime#user-sign-in-frequency) можно настроить частоту входов так, чтобы пользователи могли повторно входить в службу для доступа к ресурсу после заданного периода времени. Если для учетных записей комнаты используется частота входов, общие устройства будут выходить из учетной записи, пока администратор не будет снова входить в нее. Корпорация Майкрософт рекомендует исключить общие устройства из политик частоты входов.

### <a name="filters-for-devices"></a>Фильтры для устройств

[Фильтры для устройств](/azure/active-directory/conditional-access/concept-condition-filters-for-devices) — это функция условного доступа, которая позволяет настраивать более детализируемые политики для устройств на основе свойств устройств, доступных в Azure AD. Вы также можете использовать собственные настраиваемые значения, настроив атрибуты расширения 1–15 на объекте устройства, а затем используя их.

Используйте фильтры для устройств, чтобы определить общие устройства и включить политики в двух ключевых сценариях:

1.  Исключение общих устройств из политик, применяемых к личным устройствам. Например, требование соответствия требованиям к устройствам не применяется для общих устройств, используемых для службы hot-desk, но применяется для всех других устройств на основе номера модели.

2.  Применение специальных политик на общих устройствах, которые не следует применять к личным устройствам. Например, требование именоваемого расположения в качестве политики только для общих устройств с учетом атрибута расширения, задаваемого для этих устройств (например, "CommonAreaPhone").

>[!NOTE] 
> Некоторые атрибуты, такие как **модель,** **производитель** и **операционнаясистемаSystemVersion,** можно настроить только в том случае, если устройствами управляет Intune. Если intune не управляет вашими устройствами, используйте атрибуты расширения.