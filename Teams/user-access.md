---
title: "Управление доступом пользователей к Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Сведения о том, как включить или отключить доступ на уровне пользователей для отдельных лиц."
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd2c7490c837e34e242feed295e63a7ebac11dc6
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="manage-user-access-to-microsoft-teams"></a>Управление доступом пользователей к Microsoft Teams
=====================================

Доступ к Microsoft Teams на уровне пользователей можно включать и отключать для отдельных лиц, назначая или удаляя лицензию на продукт Microsoft Teams.

Другие параметры политики для полного или частичного включения или отключения функций Microsoft Teams на уровне отдельных пользователей сейчас отсутствуют.



> [!NOTE]
>Корпорация Майкрософт рекомендует включить Microsoft Teams для всех пользователей в организации, чтобы обеспечить согласованное формирование команд под проекты и другие инициативы. Даже если вы хотите провести пилотный проект, все равно лучше включить Microsoft Teams для всех пользователей, ограничив доступ только к тестируемым функциям.

Управление лицензиями Microsoft Teams на уровне пользователей осуществляется непосредственно через Центр администрирования Office 365. Администратор может назначать лицензии для новых пользователей при создании их учетных записей, а также для пользователей с существующими учетными записями. Для управления лицензиями Microsoft Teams нужны права администратора управления пользователями или глобального администратора Office 365.

Когда пользователю назначается номер SKU лицензии, например E3 или E5, он автоматически получает лицензию Microsoft Teams и права на использование этого продукта. Администраторы могут детально управлять всеми лицензиями и службами Office 365, а также включать и отключать лицензию Microsoft Teams для отдельного пользователя или группы пользователей.

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Лицензию пользователя Microsoft Teams можно отключить в любое время. После этого пользователь не может получить доступ к Microsoft Teams, а также не видит Microsoft Teams на домашней странице и в средстве запуска приложений Office 365.

![Снимок экрана с разделом лицензий продуктов в Центре администрирования Office 365, где выбрана служба Microsoft Teams.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Кроме Центра администрирования Office 365, для назначения и удаления лицензий вы можете использовать PowerShell в Office 365. Чтобы назначить лицензию пользователю, используйте следующий синтаксис:

```
Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"
```

Следующий пример назначает лицензию из плана лицензирования litwareinc:ENTERPRISEPACK (Office 365 корпоративный E3) пользователю без лицензии belindan@litwareinc.com.

```
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Дополнительные сведения и примеры: [Назначение лицензий для учетных записей пользователей с помощью PowerShell в Office 365](https://go.microsoft.com/fwlink/?linkid=855755).

Чтобы удалить лицензию из существующей учетной записи пользователя, используйте следующий синтаксис:

```
Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"
```

Следующий пример удаляет лицензию litwareinc:ENTERPRISEPACK (Office 365 корпоративный E3) из учетной записи пользователя BelindaN@litwareinc.com.

```
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

Дополнительные сведения и примеры: [Использование PowerShell в Office 365 для удаления лицензий из учетных записей пользователей](https://go.microsoft.com/fwlink/?linkid=855756).

| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Точка принятия решений         |<ul><li>Каков план вашей организации по повсеместной адаптации Microsoft Teams  (в пилотном или открытом режиме)?</li></ul>         |
|![Значок дальнейших действий.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Дальнейшие действия         |<ul><li>Если адаптация планируется в закрытом пилотном режиме, определите, будет ли это реализовано с помощью лицензирования либо адресного взаимодействия.</li><li>При необходимости примите соответствующие меры, чтобы предоставить доступ к Microsoft Teams только пользователям пилотного проекта.</li><li>Задокументируйте указания относительно того, какие пользователи будут (или не будут) иметь доступ к Microsoft Teams.</li></ul>         |
