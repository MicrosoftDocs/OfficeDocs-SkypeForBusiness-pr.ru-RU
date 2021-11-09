---
title: Настройка параметров архива для обработки сбоев в Skype для бизнеса Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: Сводка. Сведения о блокировке сеансов im и conferencing в случае сбоя Skype для бизнеса Server, который предотвратит архивацию.
ms.openlocfilehash: f3f20bf53a784972c720ce5578d78462cbb222c8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836471"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Настройка параметров архива для обработки сбоев в Skype для бизнеса Server

**Сводка:** Узнайте, как блокировать сеансы чата и конференций в случае сбоя Skype для бизнеса Server, который предотвратит архивацию.
  
Если архивативная деятельность является требованием для вашей организации, вы можете заблокировать сеансы чата и конференций в случае сбоя Skype для бизнеса Server, который предотвратит архивацию. Это иногда называется критическим режимом. Например, при проблеме со службой хранения мгновенный доступ будет заблокирован для пользователей, чьи сообщения включены для архивирования. Сеансы обмена мгновенными сообщениями и конференции автоматически восстанавливаются после устранения ошибок. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Настройка критического режима с помощью панели управления

Чтобы указать, следует ли разрешать сеансы связи в случае сбоя, предотвращаемого архива:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**
    
4. Щелкните имя соответствующей глобальной конфигурации, сайта или пула в списке конфигураций архивации, нажмите кнопку **Изменить** и нажмите кнопку **Показать сведения**.
    
5. Чтобы задать поведение функции архивации при сбое, установите или снимите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.
    
6. Нажмите кнопку **Зафиксировать**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Настройка критического режима с помощью Windows PowerShell

Можно также указать, следует ли разрешать сеансы связи в случае сбоя, который предотвратит архивацию с помощью комлета **Set-CsArchivingConfiguration** с параметром BlockOnArchiveFailure.
  
Например, следующая команда отключает связь в случае сбоя архива:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Следующая команда включает связь в случае сбоя архива:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Дополнительные сведения см. в разделе Справка для [cmdlet Set-CsArchivingConfiguration.](/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
