---
title: Настройка параметров архива для обработки сбоев в Skype для бизнеса Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: Сводка. Узнайте, как заблокировать сеансы im и conferencing в случае сбоя Skype для бизнеса Server, который препятствует архивированию.
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817679"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>Настройка параметров архива для обработки сбоев в Skype для бизнеса Server

**Сводка:** Узнайте, как заблокировать сеансы im и conferencing в случае сбоя Skype для бизнеса Server, препятствующих архивированию.
  
Если для вашей организации существует требование к архивированию, вы можете заблокировать сеансы im и conferencing в случае сбоя Skype для бизнеса Server, который помешает архивированию. Этот режим иногда называют критическим. Например, при проблеме со службой хранения мгновенные сообщения будут заблокированы для пользователей, чьи коммуникации включены для архивирования. Сеансы обмена мгновенными сообщениями и конференции автоматически восстанавливаются после устранения ошибок. 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>Настройка критического режима с помощью панели управления

Чтобы указать, следует ли разрешить сеансы связи в случае сбоя, препятствующих архиванию:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**
    
4. Щелкните имя соответствующей глобальной конфигурации, сайта или пула в списке конфигураций архивации, нажмите кнопку "Изменить" и выберите **"Показать подробности".**
    
5. Чтобы задать поведение функции архивации при сбое, установите или снимите флажок **При сбое архивации заблокировать обмен мгновенными сообщениями или сеансы веб-конференции**.
    
6. Нажмите кнопку **Зафиксировать**.
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>Настройка критического режима с помощью Windows PowerShell

Можно также указать, следует ли разрешить сеансы связи в случае сбоя, который помешает архивации, с помощью cmdlet **Set-CsArchivingConfiguration** с параметром BlockOnArchiveFailure.
  
Например, следующая команда отключает связь в случае сбоя архива:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

Следующая команда включает связь в случае сбоя архива:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

Дополнительные сведения см. в разделе справки по [cmdlet Set-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)
  

