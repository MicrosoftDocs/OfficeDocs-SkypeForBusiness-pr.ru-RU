---
title: Установка Microsoft Teams с помощью MSI (через SCCM)
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
ms.openlocfilehash: e32eb60b238d606ac30fe74c7551e01efe88242a
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002233"
---
# <a name="install-microsoft-teams-using-msi"></a>Установка Microsoft Teams с помощью MSI

> [!Tip]
> Просмотрите следующее видео, чтобы узнать о преимуществах классического клиента для Windows, его планировании и развертывании: [Классический клиент Teams для Windows](https://aka.ms/teams-clients)

Чтобы использовать System Center Configuration Manager, групповую политику или любые сторонние механизмы распространения для обширного развертывания, корпорация Майкрософт предоставила файлы MSI (как 32-, так и 64-разрядные), которые администраторы могут использовать для массового развертывания Teams для отдельных пользователей или на отдельных компьютерах. Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams. После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере. (Вы можете отключить автоматический запуск после установки приложения. [См. ниже](#disable-auto-launch-for-the-msi-installer).) Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.

Ниже указаны ссылки на MSI-файлы.


|Компании  |32 бит      |64 бит      |
|---------|---------|---------|
|Промышленной     | [32 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Федеральный правительственный орган – GCC     | [32 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 бит](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Федеральный правительственный орган – GCC High    | [32 бит](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 бит](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Федеральный правительственный орган – DoD     | [32 бит](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 бит](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Приложение Teams также может быть включено в развертывание Office 365 профессиональный плюс. Дополнительные сведения см. в статье [Развертывание Microsoft Teams с Office 365 профессиональный плюс](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Дополнительные сведения о SCCM см. в статье [Знакомство с System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

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
- 3 ГБ места на диске для каждого профиля пользователя (рекомендуется)

### <a name="vdi-installation"></a>Установка в VDI

Полное руководство по развертыванию классического приложения Teams в VDI можно найти в разделе [Teams для виртуализованной инфраструктуры для настольных компьютеров](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Процедура очистки и повторного развертывания

Если пользователь удаляет Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя. Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, сделайте следующее:

1. Удалите установленное приложение Teams для каждого профиля пользователя.
2. После удаления рекурсивно удалите каталог, вложенный в %localappdata%\Microsoft\Teams\.
3. Повторно разверните пакет MSI на этом конкретном компьютере.

> [!TIP]
> Вы можете использовать наш сценарий для [очистки развертывания Microsoft Teams](scripts/Powershell-script-teams-deployment-clean-up.md), чтобы выполнить шаги 1 и 2 через SCCM.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Отключение автоматического запуска для установщика MSI

Поведением по умолчанию для MSI является установка клиента Teams сразу после входа пользователя с последующим запуском Teams. Это поведение можно изменить с помощью указанных ниже параметров.

- Когда пользователь входит в Windows, приложение Teams устанавливается с помощью MSI
- Однако клиент Teams не запустится, пока пользователь не запустит его вручную
- Ярлык для запуска Teams добавляется на рабочий стол пользователя
- После запуска вручную приложение Teams будет автоматически запускаться при каждом входе пользователя

Для 32-разрядной версии
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Для 64-разрядной версии
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> Запуск MSI вручную требуется выполнять с повышенными разрешениями. Даже если вы запускаете его от имени администратора, не используя повышенные разрешения, установщик не сможет настроить параметр для отключения автозапуска.
