---
title: Включить или отключить архивировать в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: Сводка. Узнайте, как включить или отключить архивировать в Skype для бизнеса Server.
ms.openlocfilehash: c2aff3706505e8977080c92259f7d73a5c2b2b17
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839961"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Включить или отключить архивировать в Skype для бизнеса Server

**Сводка:** Узнайте, как включить или отключить архивировать в Skype для бизнеса Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Включить или отключить архивировать с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**
    
4. В списке конфигураций архивации выберите глобальную конфигурацию, конфигурацию на уровне сайта или пула, щелкните **Edit** (Изменить), щелкните **Show details** (Показать сведения) и затем выполните следующие действия:
    
   - Чтобы включить только архивацию сеансов обмена мгновенными сообщениями, щелкните **Archive IM sessions** (Архивировать сеансы обмена мгновенными сообщениями).
    
   - Чтобы включить архивацию сеансов обмена мгновенными сообщениями и конференций, щелкните **Archive IM and conferencing sessions** (Архивировать сеансы обмена мгновенными сообщениями и конференций).
    
   - Чтобы отключить архивацию для конфигурации, нажмите **кнопку Отключение архивации**.
    
5. Щелкните **Исполнить**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Включить или отключить архивировать с помощью Windows PowerShell

Вы также можете включить или отключить архивацию с помощью **комлета Set-CsArchivingConfiguration.** Например, следующая команда изменяет все параметры конфигурации архивации, чтобы архивировать только сеансы чата. Команда вызывает **командлет Get-CsArchivingConfiguration** без параметров, чтобы вернуть все параметры конфигурации архивации, которые в настоящее время используются в организации. Затем эта коллекция передается в cmdlet **Where-Object,** который выбирает только те параметры, в которых свойство EnableArchiving равно (-eq) "ImAndWebConf". Затем фильтруемая коллекция передается в **cmdlet Set-CsArchivingConfiguration,** который принимает каждый элемент в коллекции и изменяет значение EnableArchiving на "ImOnly":
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
