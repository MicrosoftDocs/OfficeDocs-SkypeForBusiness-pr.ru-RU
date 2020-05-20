---
title: Установка предварительной версии модуля PowerShell Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Выполните указанные ниже действия, чтобы установить предварительную версию модуля PowerShell Teams из коллекции тестов PowerShell.
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321772"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>Установка предварительной версии модуля PowerShell Teams

В этой статье описано, как установить последнюю предварительную версию модуля PowerShell Teams из [коллекции тестов PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). Вам потребуется предварительная версия модуля PowerShell Teams в сценариях, где командлеты для управления компонентом Teams не поддерживаются в общедоступной версии модуля и доступны только в предварительной версии.

Выполните указанные ниже действия, чтобы установить последнюю предварительную версию модуля PowerShell Teams из коллекции тестов PowerShell.

> [!NOTE]
> Не устанавливайте модуль PowerShell Teams из коллекции тестов PowerShell рядом с версией модуля из [общедоступной галереи PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Выполните эти действия, чтобы сначала удалить модуль Teams PowerShell из общедоступной коллекции PowerShell, а затем установить последнюю версию модуля из коллекции тестов PowerShell.

1. Закройте все существующие сеансы PowerShell.
2. Начните новый экземпляр модуля Windows PowerShell.
3. Выполните указанные ниже действия, чтобы удалить модуль PowerShell Teams из общедоступной галереи PowerShell.

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Закройте все существующие сеансы PowerShell.
5. Запустите модуль Windows PowerShell еще раз, а затем выполните указанные ниже действия, чтобы зарегистрировать библиотеку тестов PowerShell в качестве надежного источника.

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Выполните указанные ниже действия, чтобы установить последнюю версию модуля PowerShell для Teams из коллекции тестов PowerShell.

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Обновите модуль PowerShell до последней версии из коллекции тестовых команд PowerShell.

Если вы уже установили модуль Teams PowerShell из коллекции тестов PowerShell, выполните указанные ниже действия, чтобы обновить его до последней версии.

1. Закройте все существующие сеансы PowerShell.
2. Начните новый экземпляр модуля Windows PowerShell.
3. Выполните указанные ниже действия, чтобы обновить текущую установленную версию модуля PowerShell Teams из коллекции тестов PowerShell.

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Выполните указанные ниже действия, чтобы убедиться в том, что новейшая версия модуля Teams PowerShell из коллекции тестов PowerShell успешно установлена.

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>Статьи по теме

- [Обзор PowerShell в Teams](teams-powershell-overview.md)
