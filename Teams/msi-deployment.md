---
title: Установка Microsoft Teams с помощью MSI через диспетчер конфигурации конечных точек Майкрософт
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Администраторы могут использовать MSI Teams для массового развертывания Microsoft Teams для отдельных пользователей или на отдельных компьютерах.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f6902ae52c04d0087bb6718b119ae66dd920ced
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628135"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Установка Microsoft Teams с помощью диспетчера конфигураций конечных точек Майкрософт

> [!Tip]
> Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)

Чтобы использовать диспетчер конфигурации конечных точек Майкрософт или групповую политику, а также сторонние механизмы распространения для широкого развертывания, корпорация Майкрософт предоставила MSI-файлы (как 32, так и 64-разр), с помощью которых администраторы могут выполнять массовое развертывание Teams для выбора пользователей или компьютерах. Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams. После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере. (Вы можете отключить автоматический запуск после установки приложения. [См. ниже](#disable-auto-launch-for-the-msi-installer).) Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.

Ниже указаны ссылки на MSI-файлы.


|Компании  |32 бит      |64 бит      |
|---------|---------|---------|
|Промышленной     | [32 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Федеральный правительственный орган – GCC     | [32 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Федеральный правительственный орган – GCC High    | [32 бит](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 бит](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Федеральный правительственный орган – DoD     | [32 бит](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 бит](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Приложение Teams также может быть включено в развертывание Office 365 профессиональный плюс. Дополнительные сведения см. в статье [Развертывание Microsoft Teams с Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Дополнительные сведения о диспетчере настройки конечных точек Microsoft см. в разделе [что такое Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Процедура развертывания (рекомендуется)

1. Получите последний пакет.
2. Используйте настройки по умолчанию, заданные MSI.
3. По возможности разверните на компьютерах.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Принцип работы пакета MSI Microsoft Teams

### <a name="pc-installation"></a>Установка на компьютере

MSI Teams помещает установщик в папку Program Files. Когда пользователь входит в новый профиль пользователя Windows, запускается установщик и в папку appdata этого пользователя устанавливается копия приложения Teams. Если приложение Teams в папке appdata этого пользователя уже установлено, установщик MSI пропускает данную процедуру для этого пользователя.

Не используйте MSI для развертывания обновлений, так как клиент обновляется автоматически при обнаружении новой версии в службе. Чтобы повторно развернуть последний установщик, используйте описанную ниже процедуру для MSI.Если вы развертываете более старую версию пакета MSI, клиент обновится автоматически (кроме применения в средах VDI), когда это возможно для пользователя. При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.

> [!Important]
> Мы не рекомендуем изменять расположения установки по умолчанию, так как это может нарушить поток обновления. Наличие слишком старой версии не позволит пользователям обращаться к службе.

#### <a name="target-computer-requirements"></a>Требования к целевому компьютеру

- .NET Framework версии 4.5 или более поздней
- Windows 7 или более поздней версии
- Windows Server 2012 R2 или более поздняя версия
- 3 ГБ места на диске для каждого профиля пользователя (рекомендуется)

### <a name="vdi-installation"></a>Установка в VDI

Полное руководство по развертыванию классического приложения Teams в VDI можно найти в разделе [Teams для виртуализованной инфраструктуры для настольных компьютеров](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Процедура очистки и повторного развертывания

Если пользователь удаляет Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя. Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, сделайте следующее:

1. Удалите установленное приложение Teams для каждого профиля пользователя.
2. После удаления рекурсивно удалите каталог, вложенный в %localappdata%\Microsoft\Teams\.
3. Повторно разверните пакет MSI на этом конкретном компьютере.

> [!TIP]
> Вы можете использовать сценарий [очистки для развертывания Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md) , чтобы выполнить шаги 1 и 2 с помощью Configuration Manager.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Запрещение автоматического запуска групп после установки

По умолчанию MSI-файла устанавливают приложение Teams, как только пользователь входит в программу, а затем автоматически запускает Teams. Если вы не хотите, чтобы группы автоматически запускались для пользователей после установки, вы можете использовать групповую политику, чтобы настроить параметр политики или отключить автоматический запуск установщика MSI.

#### <a name="use-group-policy-recommended"></a>Использование групповой политики (рекомендуется)

Установите флажок **запретить автоматический запуск Microsoft Teams после установки** групповой политики. Этот параметр политики можно найти в группе Конфигурация пользователя Темплатес\микрософт Teams. Это рекомендуемый способ, так как вы можете отключить или включить параметр политики в соответствии с потребностями Организации.

Если вы включаете этот параметр политики до установки Teams, команды не запускаются автоматически при входе пользователя в Windows. После того как пользователь войдет в Teams в первый раз, команды запускаются автоматически при следующем входе пользователя в систему.

Дополнительные сведения можно найти в статье [Использование групповой политики для предотвращения автоматического запуска групп после установки](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Если вы уже развернули команды и хотите отключить функцию автозапуска Teams, сначала задайте для параметра групповой политики нужное значение, а затем запустите [сценарий сброса команд автоматического запуска](scripts/powershell-script-teams-reset-autostart.md) для каждого пользователя.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Отключение автоматического запуска для установщика MSI

Вы можете отключить автоматический запуск установщика MSI с помощью параметра **Options = "ноаутостарт = true"** , как описано ниже.  

Для 32-разрядной версии
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Для 64-разрядной версии
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Когда пользователь входит в систему Windows, программа Teams устанавливается вместе с MSI и ярлык для запуска Teams добавляется на Рабочий стол пользователя. Команды не запускаются до тех пор, пока пользователь не запустит Teams вручную. После того как пользователь вручную запускает Teams, группа автоматически запускается каждый раз, когда пользователь входит в систему.

> [!Note]
> Запуск MSI вручную требуется выполнять с повышенными разрешениями. Даже если вы запускаете учетную запись администратора, не запуская ее с повышенными разрешениями, установщик не сможет настроить параметр отключения автоматического запуска.
