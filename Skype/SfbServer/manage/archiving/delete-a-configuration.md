---
title: Удаление конфигурации архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: Сводка. Сведения об удалении конфигурации архивации в Skype для бизнеса Server.
ms.openlocfilehash: f0489fb26526a8e68935754a8689e28eca9ef335
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767887"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Удаление конфигурации архивации в Skype для бизнеса Server

**Сводка:** Узнайте, как удалить конфигурацию архивации в Skype для бизнеса Server.
  
Вы можете удалить конфигурацию сайта или конфигурацию пула, но не можете удалить глобальную конфигурацию. Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Удаление конфигурации архивации с помощью панели управления

Удаление конфигурации архивации с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**
    
4. В списке конфигураций архивации щелкните конфигурацию сайта или пула, которую необходимо удалить, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).
    
    > [!NOTE]
    > Вы также можете щелкнуть глобальную конфигурацию, но выберите этот параметр только в том случае, если вы хотите сбросить глобальную конфигурацию до значений по умолчанию. 
  
5. Щелкните **Исполнить**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Удаление конфигурации архивации с помощью Windows PowerShell

Вы также можете удалить конфигурацию архивации с помощью **cmdlet Remove-CsArchivingConfiguration.**
  
Например, следующая команда удаляет параметры конфигурации архивации, примененные к сайту Redmond. При удалении политики, настроенной в области сайта, пользователи, ранее управляемые политикой сайта, будут автоматически управляться глобальной политикой архива:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации архивации, применяемые к области службы:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Следующая команда удаляет все параметры конфигурации архивации, Exchange архивация отключена:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Для сброса глобальных параметров к значениям по умолчанию можно также использовать комлет **Remove-CsArchivingConfiguration.** Например, предположим, что вы включили архивировку сеансов im на глобальном уровне; Следующая команда сбросит значение по умолчанию none, что отключит архивировать на глобальном уровне:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsArchivingConfiguration.](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)