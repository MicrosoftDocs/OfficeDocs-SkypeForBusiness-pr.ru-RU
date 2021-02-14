---
title: Удаление конфигурации архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: Сводка. Узнайте, как удалить конфигурацию архивации в Skype для бизнеса Server.
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817629"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Удаление конфигурации архивации в Skype для бизнеса Server

**Сводка:** Узнайте, как удалить конфигурацию архивации в Skype для бизнеса Server.
  
Вы можете удалить конфигурацию сайта или пула, но не глобальную конфигурацию. Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Удаление конфигурации архивации с помощью панели управления

Чтобы удалить конфигурацию архивации с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**
    
4. В списке конфигураций архивации щелкните конфигурацию сайта или пула, которую необходимо удалить, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).
    
    > [!NOTE]
    > Вы также можете щелкнуть глобальную конфигурацию, но выбрать этот параметр только в том случае, если необходимо сбросить значения по умолчанию для глобальной конфигурации. 
  
5. Щелкните **Исполнить**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Удаление конфигурации архивации с помощью Windows PowerShell

Вы также можете удалить конфигурацию архивации с помощью **cmdlet Remove-CsArchivingConfiguration.**
  
Например, следующая команда удаляет параметры конфигурации архивации, примененные к сайту Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которыми ранее управляла политика сайта, будут автоматически управляться глобальной политикой архива:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации архивации, применяемые к области службы:
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Следующая команда удаляет все параметры конфигурации архивации, для которых отключена архивация Exchange:
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Для сброса глобальных параметров до значений по умолчанию можно также использовать cmdlet **Remove-CsArchivingConfiguration.** Например, предположим, что вы включили архивировку сеансов im на глобальном уровне; Следующая команда сбросит значение по умолчанию None, что отключит архив на глобальном уровне:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)
