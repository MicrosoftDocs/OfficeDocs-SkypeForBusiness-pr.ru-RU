---
title: Используйте средство восстановления приложения "Комнаты Microsoft Teams"
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: В этой статье рассказывается о том, как использовать средство восстановления для комнат Microsoft Teams, которое можно использовать для выхода из системы, в которой она находится в поддерживаемом состоянии.
ms.openlocfilehash: cbfb3ef1ec033389894b3b7479e454160dc77b1b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305486"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Используйте средство восстановления приложения "Комнаты Microsoft Teams"
 
В этой статье рассказывается о том, как использовать средство восстановления для комнат Microsoft Teams, которое можно использовать для выхода из системы, в которой она находится в поддерживаемом состоянии. Это средство можно использовать, если на консоли Microsoft Teams появляется сообщение об ошибке "системные конфигурации устарели".
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>Необходимые компоненты

Скачайте последний [установочный пакет Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) и извлеките его в сетевую папку, доступную для устройства с поддержкой Microsoft Teams.

Также может потребоваться установить [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Проверка версии Windows 

1. Войдите в учетную запись администратора, перейдя в **Сеттингс_гт_ Windows сеттинг_гт_ для входа** в систему с устройства с комнатой Microsoft Teams. Этот параметр открывает экран входа.
2. Войдите в учетную запись администратора, `admin` используя учетную запись администратора по умолчанию с паролем. `sfb`
3. В меню "Пуск" введите текст `winver.exe` в поле поиска и нажмите **выполнить команду* .
4. Обратите внимание на число после "Version" на второй строке области сведений.

>[!NOTE]
>Если отображается версия 1607 или более ранней версии, выполните действия, описанные в статье <a href="#Windows-up">Обновление Windows перед восстановлением</a> , прежде чем припроцединг к выполнению действий по <a href="#Perform">восстановлению</a> . Если указанная версия больше 1607, выполните действия, описанные в разделе <a href="#Perform">выполнение восстановления</a>.

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>Обновление Windows перед восстановлением (при необходимости)

1. Войдя в систему под учетной записью администратора, запустите запрос PowerShell с повышенными привилегиями.
2. Запустите команду `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.
3. Запустите обновление Windows и установите обновление для Windows 1709.
4. После обновления 1709 снова войдите в учетную запись администратора и установите [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu). Обновление может быть выполнено из ссылки или с помощью центра обновления Windows.
5. На необязательном этапе установите дополнительные обновления, доступные в Windows Update.

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>Выполнение восстановления

1. Войдите в учетную запись администратора на устройстве комнат Microsoft Teams и запустите командную команду с повышенными привилегиями.
2. Убедитесь в том, что на устройстве Microsoft Teams есть доступ к `RecoveryTool.ps1` файлу, который входит в файлы, извлеченные из пакета установки комнат Microsoft Teams. Комплект можно найти в сетевой папке или USB-накопителе, используемом при подготовке необходимых компонентов.
3. Запустите команду `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.
4. При появлении запроса с параметром `1:"Repair System"`SELECT сценария.
5. После завершения работы перезагрузите устройство Microsoft Teams комнаты. Она будет автоматически перезагружена, а второй раз восстановить ее.



<a name="See"> </a>  
## <a name="see-also"></a>См. также
 
[Справка по приложению "Комнаты Microsoft Teams"](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Управление приложением "Комнаты Microsoft Teams"](skype-room-systems-v2.md)
