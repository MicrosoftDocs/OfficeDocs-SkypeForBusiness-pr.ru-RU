---
title: Используйте средство восстановления приложения "Комнаты Microsoft Teams"
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: В этой статье рассмотрено, как использовать средство восстановления для Комнаты Microsoft Teams, с помощью которого можно привести систему в поддерживаемый режим.
ms.openlocfilehash: 4abd13abcfd20385c6f26e029dae1435883f0f8e
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503696"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Используйте средство восстановления приложения "Комнаты Microsoft Teams"

В этой статье рассмотрено, как использовать средство восстановления для Комнаты Microsoft Teams, с помощью которого можно привести систему в поддерживаемый режим. Это средство должно применяться, если в консоли Комнаты Microsoft Teams появляется сообщение об ошибке "устарела системная конфигура" или перед выполнением кнопки сбросить заводские [настройки.](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Необходимые компоненты

Скачайте последнюю [версию Комнаты Microsoft Teams и](https://go.microsoft.com/fwlink/?linkid=851168) извлеките его на USB-накопитель или в сетевую долю, доступную Комнаты Microsoft Teams.

> [!NOTE]
> Извлечение файлов из MSI-файла может быть выполнено многими способами. Любой механизм, который извлекает все файлы и сохраняет их структуру каталогов, приемлем. Один из `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` таких способов — использовать команду, которая представляет полный путь к пакету установки Microsoft Teams Room, и полный путь к папке, `PathToTarget` в которой вы хотите извлечь файлы.

## <a name="running-the-tool"></a>Запуск средства

1) Во sign in to the admin account on your Комнаты Microsoft Teams device, and launch an elevated command prompt.
2) Убедитесь Комнаты Microsoft Teams `RecoveryTool.ps1` что у устройства есть доступ к файлу, который входит в файлы, извлеченные из Комнаты Microsoft Teams установки. Комплект можно найти на сетевой диске или USB-накопителе, используемом при подготовке предварительных условий.
3) Запустите `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.
4) Чтобы выполнить восстановление до заводских насеок:
   1. При запросе сценария выберите вариант 2. **Сброс**.
   2. Если bitLocker включит, выполните инструкции, предоставленные в конце результата сценария, чтобы отключить его.
   3. Выполните восстановление до заводских насеок.
      1. Откройте приложение **Параметры** и выберите **Обновить & безопасность**
      2. Перейдите на **вкладку** Восстановление.
      3. В **области Сброс этого компьютера** выберите **Начать работу**
      4. Выберите **"Удалить все"**, затем " **Далее"** и " **Сброс"**
        > [!WARNING]
        > Устройство Комнаты Microsoft Teams может стать неиспользоваемым, если во время сброса выбран параметр Сохранить мои файлы: удаление приложений и параметров Windows **,** но сохранение личных файлов. Не выбирайте этот параметр.
      5. Система будет перезагружаема несколько раз. После завершения сброса система будет на экране Windows "Вне окна" (OOBE).



## <a name="see-also"></a>См. также

[Справка по приложению "Комнаты Microsoft Teams"](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Управление приложением "Комнаты Microsoft Teams"](rooms-manage.md)
