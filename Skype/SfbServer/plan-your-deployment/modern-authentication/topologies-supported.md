---
title: Топологии Skype для бизнеса, поддерживаемые современной проверкой подлинности
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: В этой статье перечислены сетевые и локальной топологии, поддерживаемые современной проверкой подлинности в Skype для бизнеса, а также функции безопасности, применимые к каждой топологии.
ms.openlocfilehash: b7582b6f77a3286a2b245b4b390efee7bbef62c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810109"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Топологии Skype для бизнеса, поддерживаемые современной проверкой подлинности

В этой статье перечислены сетевые и локальной топологии, поддерживаемые современной проверкой подлинности в Skype для бизнеса, а также функции безопасности, применимые к каждой топологии.

## <a name="modern-authentication-in-skype-for-business"></a>Современная проверка подлинности в Skype для бизнеса

Skype для бизнеса может использовать преимущества безопасности современной проверки подлинности. Так как Skype для бизнеса тесно работает с Exchange, на поведение входа пользователей клиента Skype для бизнеса также влияет состояние ma Exchange. This will also apply if you have a Skype for Business split-domain hybrid. Это много перемещающихся частей, но цель здесь — просто визуализировать список поддерживаемыхpologies.

С учетом Skype для бизнеса, Skype для бизнеса Online, Exchange Server и Exchange Online, какиеpologies поддерживаются с помощью ma?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Поддерживаемые topologies MA в Skype для бизнеса

Потенциально существует два серверных приложения и две рабочие нагрузки Microsoft 365 или Office 365, связанные с тополями Skype для бизнеса, используемыми ma.

- Локальное приложение Skype для бизнеса Server (CU 5)

- Skype для бизнеса Online (SFBO)

- Локальное сервер Exchange Server

- Exchange Server Online (EXO)

Еще одна важная часть проверки подлинности — знать, где будут проходить проверка подлинности (authN) и авторизация (authZ) пользователей. Возможны два варианта:

- Azure AD в Интернете в Microsoft Cloud

- Локальное сервер федерации Active Directory (ADFS)

Это немного похоже на exO и SFBO в облаке с Azure AD, а также на Exchange Server (EXCH) и на сервере Skype для бизнеса (SFB) на сервере sFB.

![Пример всех приложений (Exchange и Skype для бизнеса) и рабочих нагрузок (EXO и SFBO), а также обоих серверов авторизации (ADFS и dfS), которые могут быть задействованы при включаемой ma.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Вот поддерживаемые topologies. Обратите внимание на ключ для графики:

- Если значок серый или серый, он не используется в сценарии.

- EXO — Exchange Online.

- SFBO — Это Skype для бизнеса Online.

- EXCH — это локальное exchange.

- SFB — это локальное приложение Skype для бизнеса.

- Авторизованные серверы представлены треугольниками, например, Azure AD — это треугольник с облаком за ним.

- Стрелки указывают на авторизованный сервер, который будет использоваться при попытке клиентов связаться с указанным ресурсом сервера.

Сначала рассмотрим ma со Skype для бизнеса как в локальной, так и в облачной тоологиях.

> [!IMPORTANT]
> Готовы ли вы настроить современную проверку подлинности в Skype для бизнеса Online? Действия, необходимые для данной функции, представлены [здесь.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)

|Имя топологии  <br/> |Пример  <br/> |Описание  <br/> |Поддерживается  <br/> |
|:-----|:-----|:-----|:-----|
|Только в облаке  <br/> |![Поддерживаемый SFB с топологией ma, только облако.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Пользователи/ почтовые ящики, расположенные: Online  <br/> |MA is on for both EXO and SFBO.  <br/> Таким образом, сервером авторизации является Azure AD.  <br/> |Многофакторная проверка подлинности (MFA), проверка подлинности на основе сертификата клиента (CBA), условный доступ (ЦС) или управление мобильными приложениями (MAM) с Intune. \*  <br/> |
|Только на предварительной основе  <br/> |![Поддерживаемый SFB с топологией MA, только локально.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Пользователи/ почтовые ящики, расположенные: локально  <br/> |Ma is on for SFB on on on-premises.  <br/> Таким образом, сервером авторизации является ADFS.  <br/> Подробные сведения о конфигурации см. [в этой статье.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (только рабочий стол Windows — мобильные клиенты не поддерживаются). Нет функций интеграции Exchange.  <br/><p> **Этот подход не рекомендуется. См. здесь:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> Рекомендуется, чтобы состояние ma было одинаковым для Skype для бизнеса и Exchange (и их сетевых аналогов), чтобы уменьшить количество подсказок.

Смешанные topologies включают комбинации гибридных вариантов разделенного домена SFB. В настоящее время поддерживаются такие смешанные topologies:

|Имя топологии  <br/> |Пример  <br/> |Описание  <br/> |Поддерживается  <br/> |
|:-----|:-----|:-----|:-----|
|Смешанная 1  <br/> |![Поддерживаемый SFB с топологией ma, mixed 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Пользователи/ почтовые ящики, расположенные: EXO и SFB  <br/> |Ma не включен для SFB; В этой топологии недоступны функции SFB MA.  <br/> |Нет функций ma для SFB.  <br/> |
|Смешанный 2  <br/> |![Поддерживаемая ma с смешанной топологией S4B 2, SFBO и MA, работающими с EXCH на предварительной основе.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Пользователи/ почтовые ящики, расположенные: EXCH и SFBO  <br/> |Ma is on for SFBO only. Сервер авторизации — Это Azure AD для пользователей, которые были в SFBO, но AD для локальной службы EXCH.  <br/> |MFA, CBA, CA/MAM с Intune.\*  <br/> |
|Смешанный 3  <br/> |![Поддерживаемая ma с SFB, EXO с ma on, а также локально EXCH и SFB.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Пользователи/ почтовые ящики, расположенные: EXO + SFB или EXCH + SFB  <br/> |В этой топологии недоступны функции SFB MA  <br/> |Нет функций ma для SFB.  <br/> |
|Смешанный 4  <br/> |![Поддерживаемая ma с SFB, SFBO с ma on, а также EXCH и SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Пользователи/ почтовые ящики, расположенные: EXCH +SFBO или EXCH + SFB  <br/> |MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO. Пользователи на компьютере в SFB и EXO используют AD.  <br/> |MFA, CBA, CA/MAM с Intune только для пользователей в Интернете.\*  <br/> |
|Смешанная 5  <br/> |![Поддерживаемая ma в SFB, EXO с ma и SFBO с ma, а также EXCH и SFB локально.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Пользователи/ почтовые ящики, расположенные: EXO + SFBO, EXO + SFB, EXCH + SFBO или EXCH + SFB  <br/> |MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; пользователи на компьютере в EXCH и SFB используют AD.  <br/> |MFA, CBA, CA/MAM с Intune только для пользователей в Интернете.\*  <br/> |
|Смешанное 6  <br/> |![В топологии mixed 6 современная проверка подлинности находится во всех четырех расположениях possibile — идеальное расположение, когда речь идет о современной проверке подлинности.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Пользователи/ почтовые ящики, расположенные: EXO + SFBO, EXO + SFB, EXCH + SFBO или EXCH + SFB  <br/> |Ma is on everywhere, therefore the authorization server is Azure AD for all users. (в сети и локальной сети)  <br/>  См. [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) действия по развертыванию. <br/> |MFA, CBA и CA/MAM (через Intune) для всех пользователей.  <br/> |

\* - MFA включает настольные компьютеры с Windows, MAC, iOS, устройства с Android и Windows Phones; CBA включает настольные компьютеры с Windows, устройства с iOS и Android; Ca/MAM с Intune включает устройства с Android и iOS.

> [!IMPORTANT]
> Очень важно отметить, что в  некоторых случаях пользователи могут видеть несколько запросов, особенно если состояние ma не одинаково для всех серверных ресурсов, которые могут потребоваться и запрашивать клиенты, как в случае со всеми версиями смешанных topologies.

> [!IMPORTANT]
> Также обратите внимание, что в некоторых случаях (специально для смешанных 1, 3 и 5) для правильной настройки классических клиентов Windows необходимо настроить ключ реестра [AllowADALForNonLyncIndependentOfLync.](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)


