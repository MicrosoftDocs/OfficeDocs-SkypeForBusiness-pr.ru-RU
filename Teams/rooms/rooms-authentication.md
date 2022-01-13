---
title: Проверка подлинности в Комнаты Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Узнайте, как настроить современную проверку подлинности для Комнаты Microsoft Teams
ms.openlocfilehash: d38bf63e0ed1dc9e5cb52445fab88e617fda6169
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015199"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Проверка подлинности в Комнаты Microsoft Teams

Управление учетной Комнаты Microsoft Teams для учетных записей обрабатывается на уровне приложения. Приложение подключается к Microsoft Teams, Skype для бизнеса и Exchange, чтобы получить ресурсы для учетной записи ресурса для звонков и собраний. Комнаты Teams использует специальную учетную запись ресурса, чтобы обеспечить постоянное использование возможностей, сценарии звонков (для устройств, настроенных с планом звонков) и настраиваемые механизмы блокировки. Это означает, что проверка подлинности Комнаты Teams происходит не так, как на устройствах с конечными пользователями.  

Современная проверка подлинности рекомендуется для всех клиентов, использующих Комнаты Microsoft Teams с Microsoft 365 или Office 365. Если у вас есть локальное развертывание серверов Exchange или Skype для бизнеса, [](/office365/enterprise/hybrid-modern-auth-overview) настройте гибридную современную проверку подлинности с помощью Azure Active Directory (Azure AD), чтобы использовать современную проверку подлинности.

Современная проверка подлинности поддерживается Комнаты Microsoft Teams версии 4.4.25.0 и более поздних.

## <a name="modern-authentication"></a>Современная проверка подлинности

При использовании современной проверки подлинности с приложением Комнаты Microsoft Teams для подключения к Microsoft Teams, Exchange и Skype для бизнеса. Современный механизм проверки [](/azure/active-directory/develop/v2-oauth-ropc) подлинности использует тип разрешения авторизации паролей владельца ресурса в OAuth 2.0, который не требует вмешательства пользователя. Это одно из основных различий между современной проверкой подлинности для учетных записей пользователей и учетных записей ресурсов, которые используются Комнаты Microsoft Teams. Поэтому учетные записи Комнаты Microsoft Teams ресурсов не должны быть настроены для использования многофакторной проверки подлинности (MFA), проверки подлинности смарт-карт или проверки подлинности на основе клиентских сертификатов (все они доступны для конечных пользователей).

Еще одно важное различие между современной проверкой подлинности на устройствах Комнаты Microsoft Teams и конечных пользователей заключается в том, что учетную запись ресурса нельзя использовать для применения политик условного доступа на уровне устройств в Azure Active Directory и Endpoint Manager так как сведения об устройствах не передаются при использовании этого типа предоставления. Вместо этого вы можете зарегистрировать устройство в Microsoft Endpoint Manager и применить политики соответствия требованиям с помощью инструкций, предоставленных в Teams помещений для собраний [в Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Включить современную проверку подлинности на Комнаты Microsoft Teams

Чтобы Комнаты Microsoft Teams современную проверку подлинности с Skype для бизнеса и Exchange, в Комнаты Microsoft Teams. Это можно сделать в параметрах устройства или в XML-файле.

> [!NOTE]
> Прежде чем включить параметр на стороне клиента для современной проверки подлинности, убедитесь, что ваша среда настроена правильно для использования современной проверки подлинности.

### <a name="using-device-settings"></a>Использование параметров устройства

1. На Комнаты Microsoft Teams перейдите в **more** **(...**).
    
2. Выберите **Параметры**, а затем введите имя пользователя и пароль администратора устройства.
3. Перейдите на **вкладку Учетная** запись, включите **современную проверку подлинности** и выберите **Сохранить и выйти**.

### <a name="using-the-xml-config-file"></a>Использование файла XML-файла-конфигуры

В SkypeSettings.xml xML-элементе современной проверки подлинности задасте для элемента **True**(Истина).

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Чтобы применить этот параметр, см. статью Удаленное управление Комнаты Microsoft Teams консоли с [помощью файла конфигурации XML.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Подготовка среды к современной проверке подлинности

Прежде чем начать, убедитесь, что вы знаете, как использовать модели удостоверений Office 365 и Azure AD. Дополнительные сведения можно найти в Office 365 удостоверений и [Azure Active Directory,](/Office365/Enterprise/about-office-365-identity) а также в гибридных удостоверениях и синхронизации каталогов для Microsoft 365 [или Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Включить современную проверку подлинности в Microsoft 365 или Office 365

Чтобы включить современную проверку подлинности для Exchange Online, см. [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)

Мы рекомендуем не удалять основные политики проверки подлинности для Exchange Online и не отключать базовую проверку подлинности для клиента, пока не будет проверено, что устройства Комнаты Microsoft Teams смогут успешно войти с помощью Exchange Online и Teams.

Дополнительные сведения об отключке базовой проверки подлинности в Exchange Online см. в [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Гибридная современная проверка подлинности

Чтобы обеспечить успешную проверку подлинности на локальном сервере Exchange и (или) Skype для бизнеса-сервере, необходимо убедиться, что учетная запись ресурса, которая используется с Комнаты Microsoft Teams, настроена для получения авторизации из Azure AD.

Комнаты Teams проверки подлинности зависят от конфигурации проверки подлинности. Для клиентов, использующих управляемый домен, Комнаты Teams использует учетные данные владельца ресурса [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) с Azure Active Directory. Однако для клиентов, использующих федераированный домен, используется [OAuth 2.0 SAML Bearer Flow.](/azure/active-directory/develop/v2-saml-bearer-assertion)

> [!NOTE]
> Поставщику удостоверений могут потребоваться определенные конфигурации или параметры для интеграции с Azure Active Directory или Office 365. Обратитесь к поставщику удостоверений, если вам нужна помощь по настройке проверки подлинности в Комнаты Teams.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Необходимые условия для Комнаты Microsoft Teams

Необходимые условия для современной проверки подлинности в гибридной топологии можно найти в обзоре гибридной современной проверки подлинности и необходимые условия для ее использования с Skype для бизнеса и [Exchange серверов.](/office365/enterprise/hybrid-modern-auth-overview) Применяются все необходимые условия, рассмотренные в этой статье.

Однако поскольку Комнаты Microsoft Teams использует [](https://tools.ietf.org/html/rfc6749#section-1.3.3) авторизацию паролей владельцев ресурсов и API REST для современной проверки подлинности, следует помнить о следующих важных различиях, которые Комнаты Microsoft Teams.

- Вы должны иметь Exchange Server 2016 CU8 или более поздней или Exchange Server 2019 CU1 или более поздней.
- Вы должны иметь Skype для бизнеса Server 2015 CU5 или более поздней или Skype для бизнеса Server 2019 или более поздней.
- MFA не поддерживается независимо от топологии.
- Комнаты Microsoft Teams не поддерживает несоответствие SIP и UPN. Для работы необходимо создать учетную запись Комнаты Microsoft Teams с тем же ИП и SIP.
- Если используется сторонний поставщик проверки подлинности, который поддерживается Azure AD, он должен поддерживать активный поток проверки подлинности через WS-Trust.
- Не используйте политики условного доступа на уровне устройств для учетной записи ресурса, настроенной в приложении. Это приведет к ошибкам при входе. Вместо этого зарегистрировать устройство в Microsoft Intune и применить политики соответствия требованиям с помощью инструкций, опубликованных в Teams комнаты собраний [с помощью Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Настройка Exchange Server

Чтобы включить гибридную современную проверку подлинности в Exchange Server, см. Exchange Server локальном использовании [гибридной современной проверки подлинности.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Настройка Skype для бизнеса Server

Чтобы включить гибридную современную проверку подлинности Skype для бизнеса Server, см. Skype для бизнеса локальной проверки [подлинности.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Удаление и отключение Skype для бизнеса и Exchange

Если настройка не позволяет использовать гибридную современную проверку подлинности или вам нужно удалить или отключить гибридную современную проверку подлинности для Exchange или Skype для бизнеса, см. удаление или отключение гибридной современной проверки подлинности в Skype для бизнеса [и Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Условный доступ Azure AD

Вы можете настроить учетную запись ресурса, используемую Комнаты Microsoft Teams для доступа по IP-адресу или расположению. Подробнее см. в теме [Условный доступ: блокировка доступа по расположению.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Другие политики условного доступа не поддерживаются. Дополнительные сведения о соответствии устройств требованиям см. в Teams помещений для собраний [с помощью Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)
