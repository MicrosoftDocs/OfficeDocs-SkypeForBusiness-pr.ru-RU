---
title: Массовая установка Teams с помощью установщика Windows (MSI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Используйте файлы установщика Windows (MSI) для распространения клиента Teams среди нескольких пользователей и компьютеров.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713327"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Массовая установка Teams с помощью установщика Windows (MSI)

> [!Tip]
> Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients).

Корпорация Майкрософт предоставляет 32-разрядные, 64-разрядные и ARM64-MSI-файлы, которые можно использовать для массового развертывания Microsoft Teams для выбора пользователей и компьютеров. MSI-файлы можно использовать с [microsoft Endpoint Configuration Manager](/configmgr/core/understand/introduction), [групповая политика](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) или сторонней дистрибутивной программой для развертывания Teams в вашей организации. Массовые развертывания полезны, так как пользователям не нужно скачивать и устанавливать клиент Teams вручную. Вместо этого Teams развертывается на компьютерах, а затем автоматически запускается при первом входе пользователей на компьютер.

Рекомендуется развернуть пакет на компьютерах, а не на определенных пользователях. Благодаря ориентации на компьютеры все новые пользователи этих компьютеров будут использовать преимущества этого развертывания.

>[!NOTE]
> Teams также можно распространять в вашей организации в рамках Приложения Microsoft 365 для предприятий. Дополнительные сведения см. в статье [Развертывание Microsoft Teams с помощью Приложений Microsoft 365 для предприятий](/deployoffice/teams-install).

## <a name="msi-files"></a>MSI-файлы

В таблице ниже приведены ссылки на 32-разрядные, 64-разрядные и ARM64-MSI-файлы для Teams. Скачайте MSI, который требуется установить на компьютерах в организации. Архитектура x86 (32-разрядная или 64-разрядная) Teams поддерживается независимо от других приложений Office, установленных на компьютере.

Если у вас есть 64-разрядные компьютеры, рекомендуем установить 64-разрядную версию Teams MSI, даже если на компьютере установлена 32-разрядная версия Office. MSI ARM64 можно установить только на компьютерах, использующих архитектуру ARM, например на Surface Pro X.

> [!IMPORTANT]
> Установите 64-разрядную версию Teams только в 64-разрядных операционных системах. При попытке установить 64-разрядную версию Teams в 32-разрядной операционной системе установка не будет успешной и вы не получите сообщение об ошибке.

|Объект  |32-разрядная      |64-разрядная      | ARM64 |
|---------|---------|---------|-----------|
|Коммерческий сектор     | [32-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Правительство США — GCC     | [32-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Правительство США — GCC High    | [32-разрядная версия](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64-разрядная версия](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Правительство США — DoD     | [32-разрядная версия](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-разрядная версия](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Как работает MSI-файл Microsoft Teams

### <a name="pc-installation"></a>Установка на компьютере

MSI Teams помещает установщик в `%SystemDrive%\Program Files\Teams Installer` 32-разрядную версию Windows и `%SystemDrive%\Program Files (x86)\Teams Installer` в 64-разрядную версию Windows. Каждый раз, когда пользователь входит в новый профиль пользователя Windows, запускается установщик и в папке этого пользователя устанавливается копия приложения Teams `%LocalAppData%\Microsoft\Teams` . Если у пользователя уже установлено приложение Teams `%LocalAppData%\Microsoft\Teams` в папке, установщик MSI пропускает этот процесс для этого пользователя.

MSI-файлы нельзя использовать для развертывания обновлений. Клиент Teams будет автоматически обновляться при обнаружении новой версии, доступной в службе. Чтобы повторно развернуть последнюю версию установщика, используйте процесс повторного развертывания MSI, описанный ниже. При развертывании более старой версии MSI-файла клиент автоматически обновляется (за исключением сред VDI), когда это возможно для пользователя. При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.

> [!IMPORTANT]
> Не рекомендуется изменять расположения установки по умолчанию, так как это может нарушить поток обновления. Наличие слишком старой версии не позволит пользователям обращаться к службе.

#### <a name="target-computer-requirements"></a>Требования к целевому компьютеру

Убедитесь, что компьютеры, на которые вы устанавливаете Teams, соответствует требованиям, указанным в требованиях к оборудованию [для Microsoft Teams](hardware-requirements-for-the-teams-app.md).

### <a name="vdi-installation"></a>Установка в VDI

Полное руководство по развертыванию настольного приложения Teams в VDI см. В разделе [Teams для инфраструктуры виртуальных настольных систем](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Процедура очистки и повторного развертывания

При удалении пользователем Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя. Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, выполните следующее:

> [!IMPORTANT]
> Следующие шаги содержат сведения об изменении реестра. Убедитесь, что резервная копия реестра создана, прежде чем вносить в него изменения, а также что вы знаете, как восстановить реестр в случае возникновения неисправности. Дополнительные сведения о резервном копировании, восстановлении и изменении реестра см. в разделе [Сведения о реестре Windows для опытных пользователей](https://support.microsoft.com/help/256986).

1. Удалите установленное приложение Teams для каждого профиля пользователя. Дополнительные сведения см. в разделе [Удаление Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Рекурсивно удалите каталог для `%LocalAppData%\Microsoft\Teams\` каждого профиля пользователя.
3. Удалите значение `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` реестра для каждого профиля пользователя.
4. Повторно разверните MSI-файл на этом конкретном компьютере.

> [!TIP]
> Вы можете использовать наш сценарий для [очистки развертывания Teams](scripts/powershell-script-deployment-cleanup.md) для выполнения шагов 1 и 2.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Предотвратить автоматический запуск команд после установки

Поведение MSI по умолчанию заключается в установке приложения Teams, как только пользователь входит в систему, а затем автоматически запускает команды. Если вы не хотите, чтобы Teams запускалась автоматически для пользователей после их установки, вы можете использовать групповую политику, чтобы установить параметр политики или отключить автоматический запуск для установщика MSI.

### <a name="use-group-policy-recommended"></a>Использовать групповую политику (рекомендуется)

**Включите параметр "Запретить автоматический запуск Microsoft Teams** [групповая политика](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) установки". Этот параметр политики можно найти **в административных** шаблонах \\\\ политик конфигурации **пользователей**\\**Microsoft Teams**. Это рекомендуемый метод, потому что вы можете отключить или включить параметр политики в соответствии с потребностями вашей организации.

Когда вы включаете этот параметр политики до установки Teams, Teams не запускаются автоматически при входе пользователей в Windows. После первого входа пользователя в Teams команды запускаются автоматически при следующем входе в систему.

Дополнительные сведения см. В разделе [Использование групповой политики для предотвращения автоматического запуска Teams после установки](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Если вы уже развернули команды и хотите настроить эту политику на отключение автоматического запуска команд, сначала установите для параметра групповой политики нужное значение, а затем запустите [сценарий сброса автоматического запуска Teams ](scripts/powershell-script-teams-reset-autostart.md) для каждого пользователя.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Отключение автоматического запуска для установщика MSI

Вы можете отключить автоматический запуск для установщика MSI, используя указанный `OPTIONS="noAutoStart=true"` ниже параметр.  

Для 32-разрядной версии

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Для 64-разрядной версии

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Когда пользователь выполняет вход в Windows, Teams устанавливается с помощью MSI. Teams не запускаются, пока пользователь не запустит Teams вручную. После того, как пользователь вручную запускает Teams, Teams автоматически запускаются при каждом входе пользователя в систему.

Обратите внимание, что в этих примерах также используется параметр **ALLUSERS=1**. При установке этого параметра, установщик Teams на уровне компьютера отображается в пункте "Программы и компоненты" на панели управления и в пункте "Приложения и функция" в параметрах Windows для всех пользователей компьютера. После этого все пользователи могут удалить Teams при наличии учетных данных администратора на компьютере.

> [!Note]
> Запуск MSI вручную требуется выполнять с повышенными разрешениями. Даже если вы запустите его как администратор, без запуска с повышенными правами, установщик не сможет настроить параметр для отключения автоматического запуска.
