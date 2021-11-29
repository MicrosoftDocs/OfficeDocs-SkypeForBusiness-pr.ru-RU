---
title: Установите Microsoft Teams с помощью Microsoft Endpoint Configuration Manager
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Используйте Microsoft Endpoint Configuration Manager для массового развертывания Microsoft Teams для выбора пользователей или компьютеров.
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
ms.openlocfilehash: c7ff835715bd91e66160817410312734c6949f5c
ms.sourcegitcommit: 949fbc3215f96e48c01b75b13c400bdb47c37e4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/29/2021
ms.locfileid: "61216635"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Установите Microsoft Teams с помощью Microsoft Endpoint Configuration Manager

> [!Tip]
> Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients).

Чтобы использовать Microsoft Endpoint Configuration Manager, или групповую политику, или любые сторонние механизмы распространения для широкого развертывания, Microsoft предоставила файлы MSI (как 32-разрядные, так и 64-разрядные), которые администраторы могут использовать для массового развертывания команд для выбора пользователей или компьютеры. Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams. После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере. (Вы можете отключить автоматический запуск после установки приложения. [См. ниже](#disable-auto-launch-for-the-msi-installer).) Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.

Это ссылки на файлы MSI:

|Объект  |32-разрядная      |64-разрядная      | ARM64 |
|---------|---------|---------|-----------|
|Коммерческий сектор     | [32-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Государственные правительственные GCC     | [32-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64-разрядная версия](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Государственные правительственные правительственные GCC Высокий    | [32-разрядная версия](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64-разрядная версия](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Правительственные правительственные компании США     | [32-разрядная версия](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-разрядная версия](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**Чтобы обеспечить успешное развертывание, учитывайте следующее:**

- Устанавливайте 64-разрядную версию Teams в 64-разрядных операционных системах. При попытке установить 64-разрядную версию Teams в 32-разрядной операционной системе, установка завершится неудачно, и вы не получите сообщение об ошибке.

- Приложение Teams также может быть включено в развертывание приложений Microsoft 365 для предприятий. Дополнительные сведения см. в статье [Развертывание Microsoft Teams с помощью Приложений Microsoft 365 для предприятий](/deployoffice/teams-install).

- Дополнительные сведения о Microsoft Endpoint Configuration Manager см. в разделе [Что такое Configuration Manager?](/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Процедура развертывания (рекомендуется)

1. Получите последний пакет.
2. Используйте настройки по умолчанию, заданные MSI.
3. По возможности разверните на компьютерах.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Принцип работы пакета MSI Microsoft Teams

### <a name="pc-installation"></a>Установка на компьютере

MSI Teams помещает установщик в папку Program Files. Всякий раз, когда пользователь входит в новый профиль пользователя Windows, запускается установщик, и в папку `AppData` этого пользователя устанавливается копия приложения Teams. Если у пользователя уже есть приложение Teams, установленное в папке `AppData`, установщик MSI пропустит процесс для этого пользователя.

Не используйте MSI для развертывания обновлений, так как клиент обновляется автоматически при обнаружении новой версии в службе. Чтобы повторно развернуть последний установщик, используйте описанную ниже процедуру для MSI. Если вы развертываете более старую версию пакета MSI, клиент обновится автоматически (кроме применения в средах VDI), когда это возможно для пользователя. При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.

> [!IMPORTANT]
> По умолчанию папка C:\Program Files (x86)\Teams Installer в 32-битной операционной системе и C:\Program Files\Teams Installer в 64-битной операционной системе.
> Мы не рекомендуем изменять расположения установки по умолчанию, так как это может нарушить поток обновления. Наличие слишком старой версии не позволит пользователям обращаться к службе.

#### <a name="target-computer-requirements"></a>Требования к целевому компьютеру

- .NET Framework версии 4.5 или более поздней
- Windows 8.1 или новее
- Windows Server 2012 R2 или более поздняя версия
- 3 ГБ места на диске для каждого профиля пользователя (рекомендуется)

### <a name="vdi-installation"></a>Установка в VDI

Полное руководство по развертыванию настольного приложения Teams в VDI см. В разделе [Teams для инфраструктуры виртуальных настольных систем](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Процедура очистки и повторного развертывания

При удалении пользователем Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя. Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, выполните следующее:

> [!IMPORTANT]
> Следующие шаги содержат сведения об изменении реестра. Убедитесь, что резервная копия реестра создана, прежде чем вносить в него изменения, а также что вы знаете, как восстановить реестр в случае возникновения неисправности. Дополнительные сведения о резервном копировании, восстановлении и изменении реестра см. в разделе [Сведения о реестре Windows для опытных пользователей](https://support.microsoft.com/help/256986).

1. Удалите установленное приложение Teams для каждого профиля пользователя. Дополнительные сведения см. в разделе [Удаление Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Рекурсивно удалите каталог в `%localappdata%\Microsoft\Teams\`.
3. Удалите значение реестра `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`.
4. Повторно разверните пакет MSI на этом конкретном компьютере.

> [!TIP]
> Вы можете использовать наш сценарий для [очистки развертывания Teams](scripts/powershell-script-deployment-cleanup.md) для выполнения шагов 1 и 2.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Предотвратить автоматический запуск команд после установки

Поведение MSI по умолчанию заключается в установке приложения Teams, как только пользователь входит в систему, а затем автоматически запускает команды. Если вы не хотите, чтобы Teams запускалась автоматически для пользователей после их установки, вы можете использовать групповую политику, чтобы установить параметр политики или отключить автоматический запуск для установщика MSI.

### <a name="use-group-policy-recommended"></a>Использовать групповую политику (рекомендуется)

Включите параметр **Запретить автоматический запуск Microsoft Teams после установки** групповой политики. Вы можете найти этот параметр политики в Конфигурация пользователя\Политики\Административные шаблоны\Microsoft Teams. Это рекомендуемый метод, потому что вы можете отключить или включить параметр политики в соответствии с потребностями вашей организации.

Когда вы включаете этот параметр политики до установки Teams, Teams не запускаются автоматически при входе пользователей в Windows. После первого входа пользователя в Teams команды запускаются автоматически при следующем входе в систему.

Дополнительные сведения см. В разделе [Использование групповой политики для предотвращения автоматического запуска Teams после установки](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Если вы уже развернули команды и хотите настроить эту политику на отключение автоматического запуска команд, сначала установите для параметра групповой политики нужное значение, а затем запустите [сценарий сброса автоматического запуска Teams ](scripts/powershell-script-teams-reset-autostart.md) для каждого пользователя.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Отключение автоматического запуска для установщика MSI

Вы можете отключить автоматический запуск установщика MSI, используя параметр **OPTIONS="noAutoStart=true"**, как показано ниже.  

Для 32-разрядной версии

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Для 64-разрядной версии

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Когда пользователь входит в Windows, Teams устанавливаются вместе с MSI, и ярлык для запуска команд добавляется на рабочий стол пользователя. Teams не запускаются, пока пользователь не запустит Teams вручную. После того, как пользователь вручную запускает Teams, Teams автоматически запускаются при каждом входе пользователя в систему.

Обратите внимание, что в этих примерах также используется параметр **ALLUSERS=1**. При установке этого параметра, установщик Teams на уровне компьютера отображается в пункте "Программы и компоненты" на панели управления и в пункте "Приложения и функция" в параметрах Windows для всех пользователей компьютера. После этого все пользователи могут удалить Teams при наличии учетных данных администратора на компьютере.

> [!Note]
> Запуск MSI вручную требуется выполнять с повышенными разрешениями. Даже если вы запустите его как администратор, без запуска с повышенными правами, установщик не сможет настроить параметр для отключения автоматического запуска.
