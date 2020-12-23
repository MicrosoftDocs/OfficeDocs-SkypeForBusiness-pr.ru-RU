---
title: Проверка подлинности в комнатах Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Узнайте, как настроить современную проверку подлинности для комнат Microsoft Teams
ms.openlocfilehash: 41a65743e5da851dd8e0197e9382deaf696cd9ec
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662584"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Проверка подлинности в комнатах Microsoft Teams

Управление учетными записями для устройств комнат Microsoft Teams обрабатывается на уровне приложения. Приложение подключается к Microsoft Teams, Skype для бизнеса и Exchange, чтобы получить ресурсы для учетной записи комнаты, чтобы обеспечить возможность звонков и собраний. На устройстве хранится учетная запись с agnostic, что позволяет использовать всегда возможности, сценарии звонков (для устройств, настроенных с помощью плана звонков), а также настраиваемые механизмы блокировки, реализованные на этих устройствах. Это означает, что проверка подлинности на этих устройствах происходит не так, как на устройствах пользователей.  

Современная проверка подлинности рекомендуется для всех клиентов, использующих устройства комнат Microsoft Teams с Microsoft 365 или Office 365. Если у вас развернут сервер Exchange Server или Skype для [](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) бизнеса, настройте гибридную современную проверку подлинности с помощью Azure Active Directory (Azure AD), чтобы использовать современную проверку подлинности.

Современная проверка подлинности поддерживается в комнатах Microsoft Teams версии 4.4.25.0 и более поздних.

## <a name="modern-authentication"></a>Современная проверка подлинности

При использовании современной проверки подлинности в приложении комнат Microsoft Teams для подключения к Microsoft Teams, Exchange и Skype для бизнеса используется библиотека проверки подлинности Active Directory (ADAL). Устройство комнат Microsoft Teams — это общее устройство, которое выполняет ночную перезагрузку, чтобы обеспечить плавную работу и получить критически важные обновления операционной системы, драйверов, полотен или приложений. Современный механизм проверки [](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) подлинности использует тип разрешения авторизации паролей владельца ресурса в OAuth 2.0, который не требует вмешательства пользователя. Это одно из ключевых различий между современной проверкой подлинности для учетных записей пользователей и учетных записей ресурсов, которые используются приложением комнат Microsoft Teams. В связи с этим учетные записи ресурсов комнат Microsoft Teams не должны быть настроены для использования многофакторной проверки подлинности (MFA), проверки подлинности смарт-карт или проверки подлинности на основе клиентских сертификатов (которые доступны для конечных пользователей).

Еще одно важное различие между современной проверкой подлинности на устройствах Microsoft Teams Rooms и устройствах пользователей состоит в том, что учетную запись ресурса нельзя использовать для применения политик условного доступа на уровне устройства в Azure Active Directory и Диспетчере конечных точек, так как при использовании этого типа предоставления не передаются сведения об устройстве. Вместо этого вы можете зарегистрировать устройство в Microsoft Endpoint Manager и применить политики соответствия требованиям, используя рекомендации, предоставленные в управлении комнатами собраний [Teams с помощью Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Включить современную проверку подлинности на устройстве с комнатами Microsoft Teams

Чтобы в комнатах Microsoft Teams можно было использовать современную проверку подлинности в Skype для бизнеса и Exchange, в включить параметр на стороне клиента для современной проверки подлинности на устройстве комнат Microsoft Teams. Это можно сделать в параметрах устройства или в XML-файле config.

> [!NOTE]
> Прежде чем включить настройку на стороне клиента для современной проверки подлинности, убедитесь, что среда настроена правильно для использования современной проверки подлинности.

### <a name="using-device-settings"></a>Использование параметров устройства

1. На устройстве "Комнаты команд" (Майкрософт) перейдите в **"Еще"** **(...).**
    
2. Выберите **"Параметры"** и введите имя пользователя и пароль администратора устройства.
3. Перейдите на вкладку **"Учетная запись",** включите современную проверку **подлинности** и выберите **"Сохранить и выйти".**

### <a name="using-the-xml-config-file"></a>Использование XML-файла config

В SkypeSettings.xml установите для XML-элемента современной проверки подлинности истинность, как поется в этом примере.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Чтобы применить этот параметр, см. статью "Удаленное управление настройками консоли комнат Microsoft Teams с [помощью XML-файла конфигурации".](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>Подготовка среды к современной проверке подлинности

Прежде чем начать, убедитесь, что вы понимаете модели удостоверений, которые используются в Office 365 и Azure AD. Дополнительные сведения можно найти в моделях [удостоверений Office 365, Azure Active Directory,](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) а также при синхронизации гибридных удостоверений и каталогов [для Microsoft 365 или Office 365.](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Включить современную проверку подлинности в Microsoft 365 или Office 365

Чтобы включить современную проверку подлинности для Exchange Online, см. в этом видео. [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Если вы используете Skype для бизнеса Online, убедитесь, что включена современная проверка подлинности для Skype для бизнеса Online. Дополнительные узнать см. в skype для бизнеса Online: "Как включить современную проверку [подлинности для клиента".](https://aka.ms/SkypeModernAuth)

Мы рекомендуем не удалять базовые политики проверки подлинности для Exchange Online и не отключать базовую проверку подлинности для клиента до тех пор, пока не будет проверено, что устройства комнат Microsoft Teams могут успешно войти с помощью Exchange Online, Teams и Skype для бизнеса Online.

Дополнительные сведения об отключке базовой проверки подлинности в Exchange Online см. в подмене основной проверки подлинности [в Exchange Online.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>Гибридная современная проверка подлинности

Чтобы обеспечить успешную проверку подлинности на локальном сервере Exchange и (или) сервере Skype для бизнеса, необходимо убедиться, что учетная запись ресурса, используемая с комнатами Microsoft Teams, настроена для получения авторизации через Azure AD. 

Потоки проверки подлинности в помещениях Teams зависят от конфигурации проверки подлинности. Для клиентов, использующих управляемый домен, в комнатах Teams используются учетные данные владельца ресурса [OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) с Azure Active Directory. Однако для клиентов, использующих федераальный домен, используется [OAuth 2.0 SAML Bearer Assertion Flow.](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion)

> [!NOTE]
> Для интеграции с Azure Active Directory или Office 365 поставщику удостоверений могут потребоваться определенные настройки или параметры. Если вам нужна помощь в настройке проверки подлинности в комнатах Teams, обратитесь к поставщику удостоверений.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Предварительные условия для комнат Microsoft Teams

Необходимые условия для того, чтобы включить современную проверку подлинности в гибридной топологии, можно найти в обзоре гибридной современной проверки подлинности и предварительных условия для ее использования с локальной версией Skype для бизнеса и [серверами Exchange.](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Применяются все необходимые условия, рассмотренные в этой статье.

Однако поскольку в комнатах Microsoft Teams используется авторизация паролей владельцев ресурсов и а также API REST, которые используются при современной проверке подлинности, следует помнить о следующих важных различиях, которые специфичные для Microsoft Teams Rooms. [](https://tools.ietf.org/html/rfc6749#section-1.3.3)

- Необходимо иметь Exchange Server 2016 с 8 или более поздней либо Exchange Server 2019 с 1 или более поздней.
- У вас должна быть skype для бизнеса Server 2015 с cu5 или более поздней либо Skype для бизнеса Server 2019 или более поздней.
- MFA не поддерживается независимо от топологии.
- Комнаты Microsoft Teams не поддерживают несоответствия SIP и UPN. Для работы комнат Microsoft Teams необходимо создать учетную запись с одинаковыми upN и SIP.
- Если вы используете стороннее поставщик проверки подлинности, который поддерживает Azure AD, он должен поддерживать активный поток проверки подлинности через WS-Trust.
- Не используйте политики условного доступа на уровне устройств для учетной записи ресурса, настроенной в приложении. Это приведет к сбоям при входе. Вместо этого зарегистрировать устройство в Microsoft Intune и применить политики соответствия требованиям с помощью инструкций, опубликованных в области управления комнатами собраний [Teams с помощью Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)

### <a name="configure-exchange-server"></a>Настройка Exchange Server

Чтобы включить гибридную современную проверку подлинности в Exchange Server, см. Exchange Server настройки локальной проверки для [использования гибридной современной проверки подлинности.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>Настройка сервера Skype для бизнеса

О том, как включить гибридную современную проверку подлинности в Skype для бизнеса Server, см. в локальной настройке Skype для бизнеса для использования [гибридной современной проверки подлинности.](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Удаление и отключение Skype для бизнеса и Exchange

Если настройка не позволяет использовать гибридную современную проверку подлинности или вам нужно удалить или отключить гибридную современную проверку подлинности для Exchange или Skype для бизнеса, см. также: "Удаление или отключение гибридной современной проверки подлинности в Skype для бизнеса и [Exchange".](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Условный доступ в Azure AD

Вы можете настроить учетную запись ресурса, используемую с комнатами Microsoft Teams для доступа по IP-адресу или расположению. Подробнее см. в теме ["Условный доступ: блокировка доступа по расположению".](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

Другие политики условного доступа не поддерживаются. Дополнительные сведения о соответствии устройства требованиям см. в [управлении комнатами собраний Teams с помощью Intune.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)  
