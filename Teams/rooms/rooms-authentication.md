---
title: Проверка подлинности в комнатах Microsoft Teams
ms.author: v-lanac
author: lanachin
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
description: Сведения о настройке современной проверки подлинности в комнатах Microsoft Teams
ms.openlocfilehash: ba6259efac5d1e429bbcc33aeaef19759930e345
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308262"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Проверка подлинности в комнатах Microsoft Teams

Управление учетными записями в Microsoft Teams комнаты обрабатываются на уровне приложения. Приложение подключается к Microsoft Teams, Skype для бизнеса и Exchange, чтобы получить доступ к ресурсам для учетной записи комнаты, чтобы обеспечить возможность звонков и собраний. Это устройство остается независимым для обеспечения постоянной поддержки, сценариев вызова (для устройств, настроенных с помощью абонентского плана) и настраиваемых механизмов блокировки, реализованных на этих устройствах. Это означает, что проверка подлинности для этих устройств происходит не так, как для конечных пользователей.  

Современная проверка подлинности рекомендуется для всех пользователей, использующих устройства с Microsoft Teams, с помощью Microsoft 365 или Office 365. Если вы используете локальное развертывание Exchange Server или Skype для бизнеса Server, настройте [гибридную современной проверку подлинности](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) с помощью Azure Active Directory (Azure AD), чтобы включить использование современной проверки подлинности.

Современная проверка подлинности поддерживается в комнатах Microsoft Teams версии 4.4.25.0 и более поздних.

## <a name="modern-authentication"></a>Современная проверка подлинности

При использовании современной проверки подлинности в приложении Microsoft Teams комнаты, Библиотека проверки подлинности Active Directory (ADAL) используется для подключения к Microsoft Teams, Exchange и Skype для бизнеса. Устройство Microsoft Teams является общим устройством и выполняет ночную перезагрузку для обеспечения бесперебойной работы и получения критической операционной системы, драйвера, встроенного по или обновлений приложения. Механизм современной проверки подлинности использует для авторизации учетных данных, предоставленных для [пароля владельца ресурса](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) , тип Grant в OAuth 2,0, для которого не требуется вмешательство пользователя. Это является одной из основных различий в том, как технология современной проверки подлинности работает для учетных записей пользователей и ресурсов, используемых приложением Microsoft Teams. Из-за этой возможности учетные записи ресурсов в Microsoft Teams не должны быть настроены на использование многофакторной проверки подлинности (MFA), проверки подлинности на основе сертификатов и проверки подлинности клиента (для конечных пользователей).

Другие ключевые различия между работой современной проверки подлинности в Microsoft Teams в устройствах и устройствах конечных пользователей в том, что вы не можете использовать учетную запись ресурса для применения политик условного доступа на уровне устройства в Azure Active Directory и диспетчере конечных точек, так как при использовании этого типа предоставленных данных не передается информация об устройстве. Вместо этого вы можете зарегистрировать устройство в Microsoft Endpoint Manager и применить политики соответствия с помощью руководства, предоставленного в разделе [Управление комнатами собраний Teams с помощью Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Включение современной проверки подлинности на устройстве с комнатой Microsoft Teams

В помещениях Microsoft Teams для использования современной проверки подлинности в Skype для бизнеса и Exchange включите параметр на стороне клиента для современной проверки подлинности на устройстве Microsoft Teams. Это можно сделать в разделе Параметры устройства или XML-файл конфигурации.

> [!NOTE]
> Перед включением параметра на стороне клиента для современной проверки подлинности убедитесь, что ваша среда правильно настроена для использования современной проверки подлинности.

### <a name="using-device-settings"></a>Использование параметров устройства

1. На устройстве "комнаты группы Microsoft" перейдите на вкладку " **Дополнительно** " (**...**).
    
2. Выберите **Параметры**, а затем введите имя пользователя и пароль администратора устройства.
3. Перейдите на вкладку **учетная запись** , включите функцию **современной проверки подлинности**, а затем нажмите кнопку **сохранить и выйти**.

### <a name="using-the-xml-config-file"></a>Использование XML-файла конфигурации

В файле SkypeSettings.xml задайте для современного XML-элемента проверки подлинности **значение true**, как описано ниже.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

Чтобы применить этот параметр, в разделе [Управление параметрами консоли Microsoft Teams можно удаленно с помощью XML-файла конфигурации](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>Подготовка среды для современной проверки подлинности

Прежде чем начать, убедитесь в том, что вы понимаете модели удостоверений, которые нужно использовать с Office 365 и Azure AD. Дополнительные сведения можно найти в [моделях удостоверений Office 365 и Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) , а также в [гибридной идентификации и синхронизации каталогов для Microsoft 365 или Office 365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization).

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Включение современной проверки подлинности в Microsoft 365 или Office 365

Чтобы включить современной проверки подлинности в Exchange Online, ознакомьтесь со сведениями [Включение современной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online). Если вы используете Skype для бизнеса Online, вам также необходимо убедиться, что для Skype для бизнеса Online включена современная проверка подлинности. Дополнительные сведения можно найти в статье [Skype для бизнеса Online: Включите клиент для современной проверки подлинности](https://aka.ms/SkypeModernAuth).

Мы рекомендуем не удалять основные политики проверки подлинности для Exchange Online и отключать обычную проверку подлинности для клиента, пока вы не проверили, что устройства Microsoft Teams в комнатах могут успешно входить в систему с помощью Exchange Online, Teams и Skype для бизнеса Online.

Дополнительные сведения об отключении обычной проверки подлинности в Exchange Online можно найти [в разделе Отключение обычной проверки подлинности в Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online).

## <a name="hybrid-modern-authentication"></a>Гибридная современная проверка подлинности

Чтобы убедиться, что проверка подлинности выполнена для локального сервера Exchange Server и/или Skype для бизнеса Server, необходимо убедиться, что учетная запись ресурса, используемая в комнатах Microsoft Teams, настроена на получение авторизации из Azure AD. 

Потоки для проверки подлинности в рабочих помещениях зависят от конфигурации проверки подлинности. Для пользователей, использующих управляемый домен, комнаты Teams используют [учетные данные владельца ресурса OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) с помощью Azure Active Directory. Тем не менее, для клиентов, использующих федеративные домены, используется [поток утверждений OAuth 2,0 SAML-Bearer](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) .

> [!NOTE]
> Поставщику удостоверений могут потребоваться определенные конфигурации или параметры для интеграции с Azure Active Directory или Office 365. Если вам нужна помощь по настройке проверки подлинности в комнатах Teams, обратитесь к поставщику удостоверений.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Предварительные требования для комнат Microsoft Teams

Требования, необходимые для включения современной проверки подлинности в гибридной топологии, рассматриваются в [обзорах гибридной современной проверки подлинности и предварительных требованиях для их использования с локальными серверами Skype для бизнеса и Exchange Server](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview). Применимы все предварительные требования, описанные в этой статье.

Тем не менее, поскольку комнаты Microsoft Teams используют для проверки подлинности [учетных данных владельца ресурсов](https://tools.ietf.org/html/rfc6749#section-1.3.3) и базовые API для RESTful, ниже приведены важные различия, которые необходимо учитывать в помещениях Microsoft Teams.

- У вас должен быть сервер Exchange Server 2016 обновления HF1 или более поздней версии или Exchange Server 2019 CU1 или более поздней версии.
- У вас должен быть Skype для бизнеса Server 2015 CU5 или более поздней версии или Skype для бизнеса Server 2019 или более поздней версии.
- MFA не поддерживается вне зависимости от того, какая у вас топология.
- Комнаты Microsoft Teams не поддерживают несоответствие SIP и UPN. Для работы с учетной записью комнаты Microsoft Teams необходимо использовать один и тот же UPN и SIP.
- Если вы используете сторонний поставщик проверки подлинности, который поддерживается Azure AD, он должен поддерживать активный поток проверки подлинности через WS-Trust.
- Не используйте политики условного доступа на уровне устройства для учетной записи ресурсов, настроенной для приложения. Это может привести к сбоям при входе. Вместо этого зарегистрируйте устройство в Microsoft Intune и примените политики соответствия с помощью руководства, опубликованного в разделе [Управление комнатами собраний Teams с помощью Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).

### <a name="configure-exchange-server"></a>Настройка сервера Exchange Server

Сведения о включении гибридной современной проверки подлинности в Exchange Server можно узнать в разделе [Настройка локального сервера Exchange Server для использования гибридной современной проверки подлинности](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>Настройка Skype для бизнеса Server

Для включения гибридной современной проверки подлинности в Skype для бизнеса Server ознакомьтесь со [сведениями о том, как настроить гибридную современной проверки подлинности в локальной среде Skype для бизнеса](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Удаление и отключение Skype для бизнеса и Exchange

Если в вашей настройке не разрешена Гибридная современная проверка подлинности или вы хотите удалить или отключить гибридную современной проверки подлинности для Exchange или Skype для бизнеса, ознакомьтесь с разрядом [Удаление и отключение гибридной современной проверки подлинности в Skype для бизнеса и Exchange](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha).

### <a name="azure-ad-conditional-access"></a>Условный доступ Azure AD

Вы можете настроить учетную запись ресурса, используемую в комнатах Microsoft Teams, для IP и доступа на основе местоположения. Дополнительные сведения можно найти в разделе [Условный доступ: блокировать доступ по местоположению](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

Другие политики условного доступа не поддерживаются. Дополнительные сведения о требованиях к устройствам можно найти [в разделе Управление комнатами собраний Teams с помощью Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230).  
