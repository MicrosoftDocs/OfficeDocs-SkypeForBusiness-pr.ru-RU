---
title: Удаление параметров конфигурации собрания в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Сводка: сведения о том, как удалить параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: a728f1c1de3470cf505163c5cb25996c190e9026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306477"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>Удаление параметров конфигурации собрания в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как удалить параметры конфигурации собрания в Skype для бизнеса Server.
  
Вы можете удалить параметры конфигурации собрания с помощью панели управления Skype для бизнеса Server или консоли управления Skype для бизнеса Server.
  
Можно удалить конфигурацию сайта или пользователя. Глобальную конфигурацию невозможно удалить. При попытке удалить глобальной конфигурации она автоматически восстанавливает значения по умолчанию.
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации собрания с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
4. В списке конфигураций собрания выберите конфигурацию сайта или пула, щелкните **Изменить**, а затем **Удалить**.
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Удаление параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server

Для удаления параметров собраний используйте командлет **Remove-CsMeetingConfiguration**.
  
Следующая команда удаляет параметры конфигурации собраний в сайте Redmond:
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации собрания, примененные к области сайта:
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

Дополнительные сведения, включая полный список параметров, можно найти в разделе [Remove-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).
  

