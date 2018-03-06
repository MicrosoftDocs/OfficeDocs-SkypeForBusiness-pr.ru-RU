---
title: "Лицензирование Office 365 для Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, ninadara
description: "Сведения о различных лицензиях Office 365, лицензия, позволяющих пользователям работать с Microsoft Teams, а также о способах включения и отключения этого продукта."
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 868b84d48a85464dc0d9b1890354dad42d9cb068
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>Лицензирование Office 365 для Microsoft Teams
========================================

Следующие подписки Office 365 позволяют пользователям работать с Microsoft Teams.

|Планы для малого бизнеса  |Корпоративные планы  |Планы для образования  |
|---------|---------|---------|
|Office 365 бизнес базовый     |Office 365 корпоративный E1         |Office 365 для образования         |
|Office 365 бизнес премиум     |Office 365 корпоративный E3         |Office 365 для образования плюс         |
|     |Office 365 корпоративный E4 (устарел)         |Office 365 для образования E3 (устарел)         |
|     |Office 365 корпоративный E5         |Office 365 для образования E5   
      |Office 365 корпоративный F1 |  |

> [!NOTE]
> Продукт Microsoft Teams также доступен для некоммерческих организаций. Лицензирование для государственных организаций сейчас не поддерживается, но работа в этом направлении ведется.
        


С точки зрения базовых функций Teams разные подписки Office 365 не отличаются. Но от уровня подписки зависят возможности по обеспечению соответствия. Дополнительные сведения: [Обзор обеспечения безопасности и соответствия в Teams.](security-compliance-overview.md)

Все поддерживаемые планы подписки предоставляют право на использование веб-клиента, классических клиентов и мобильных приложений Microsoft Teams.

Teams не предоставляется в виде автономной службы.

<a name="teams-license"></a>Лицензия Microsoft Teams
-------------

По умолчанию лицензия Microsoft Teams активна для всех пользователей с соответствующими подписками Office 365.

![Снимок экрана с параметрами в разделе лицензий в Центре администрирования Office 365, где включена служба Microsoft Teams.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


Microsoft Teams можно включить или отключить для всего типа лицензии в организации. Эта служба включена по умолчанию для всех типов лицензий, кроме гостевых.

> [!IMPORTANT]
> Центр администрирования Office 365 не позволяет включить Teams лишь частично для определенного типа лицензии. Если необходимо включить Microsoft Teams для одних пользователей организации и отключить для других (например, планируется пилотный проект Microsoft Teams с выбранными пользователями), включите переключатель лицензий Microsoft Teams для всех пользователей, а затем выключите его для отдельных пользователей.

![Снимок экрана с параметрами в разделе типов лицензий/пользователей в Центре администрирования Office 365, где включена служба Microsoft Teams.](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


> [!TIP]
> Включение и отключение в PowerShell лицензии на рабочую нагрузку Microsoft Teams выполняются точно так же, как и для других нагрузок. План обслуживания для Microsof Teams называется TEAMS1. (Дополнительные сведения: [Отключение доступа к службам с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)

**Пример:** Ниже представлен краткий пример, как отключить Microsoft Teams у всех пользователей с определенным типом лицензии. Сначала выполните эту операцию, а затем отдельно активируйте лицензии для каждого пользователя, которому нужен доступ в рамках пилотной программы.

Чтобы отобразить типы подписок в вашей организации, используйте следующую команду.

      Get-MsolAccountSku

Введите название плана, которое включает название организации и план для вашего образовательного заведения (например, ContosoSchool:ENTERPRISEPACK_STUDENT), после чего выполните следующие команды.

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
Чтобы отключить Microsoft Teams для всех пользователей с активной лицензией по названному вами плану, выполните следующую команду.

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x