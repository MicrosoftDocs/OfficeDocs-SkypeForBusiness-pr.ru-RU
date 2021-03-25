---
title: Используйте средство восстановления приложения "Комнаты Microsoft Teams"
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: В этой статье рассмотрено использование средства восстановления для комнат Microsoft Teams, с помощью которого можно привести устарелную систему в поддерживаемый штат.
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117497"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Используйте средство восстановления приложения "Комнаты Microsoft Teams"

В этой статье рассмотрено использование средства восстановления для комнат Microsoft Teams, с помощью которого можно привести устарелную систему в поддерживаемый штат. Это средство следует применять, если в консоли комнат Microsoft Teams появляется сообщение об ошибке "системные настройки устарели" или перед выполнением кнопки "сбросить заводские [настройки".](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)

## <a name="prerequisites"></a>Необходимые компоненты

Скачайте последний [пакет установки комнат Microsoft Teams и](https://go.microsoft.com/fwlink/?linkid=851168) извлеките его на USB-накопитель или в обойму, доступную на устройстве Комнаты Microsoft Teams.

> [!NOTE]
> Извлечь файлы из MSI-файла можно многими способами. Любой механизм, который извлекает все файлы и сохраняет их структуру каталогов, приемлем. Один из таких способов — использовать команду, которая представляет полный путь к пакету установки комнаты Microsoft Teams Room и полный путь к папке, в которой должны быть извлечены `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` файлы.

## <a name="running-the-tool"></a>Запуск средства

1) Во sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.
2) Убедитесь, что с устройства комнат Microsoft Teams у вас есть доступ к файлам, извлеченным из пакета установки `RecoveryTool.ps1 file` комнат Microsoft Teams. Комплект можно найти в сетевой сетевой сети или USB-накопителе, используемом при подготовке предварительных условий.
3) Запустите `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` .
4) Чтобы восстановить заводские функции:
   1. При запросе сценария выберите вариант 2: **Сброс.**
   2. Если bitLocker отключен, следуйте инструкциям в конце сценария.
   3. Выполните восстановление до заводских насов.
      1. Откройте приложение **"Параметры"** и выберите "Обновить & **безопасности"**
      2. Перейдите на **вкладку "Восстановление".**
      3. Под **кнопкой "Восстановить этот компьютер"** выберите **"Начать работу"**
      4. Выберите **"Удалить все",** затем **"Далее"** и **"Сброс"**
        > [!WARNING]
        > Устройство комнат Microsoft Teams может стать непригодным для работы, если команда "Сохранить мои файлы" — удаляет приложения и **параметры,** но сохраняет параметр "Сохранить личные файлы" во время сброса Windows. Не выбирайте этот параметр.
      5. Система будет перезагружаема несколько раз. После завершения сброса система будет работать на экране Windows "Выход из окна" (OOBE).



## <a name="see-also"></a>См. также

[Справка по приложению "Комнаты Microsoft Teams"](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Управление приложением "Комнаты Microsoft Teams"](rooms-manage.md)