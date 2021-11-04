---
title: Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как настроить отказ от архива для Skype для бизнеса Server.
ms.openlocfilehash: a5777a416d634f6d767efbec97f2c72bc7899c47
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773399"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
 
**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как настроить отказ от архива для Skype для бизнеса Server.
  
Если ваша организация взаимодействует с внешними партнерами, необходимо сообщить им, что вы архивировать сообщения с ними. При развертывании edge Server и включите федерацию для организации, вас спрашивают, хотите ли вы автоматически отправлять об отказе от архивизации внешним партнерам. 
  
Если требуется изменить эту конфигурацию, можно использовать панель управления Skype для бизнеса Server или Windows PowerShell **set-CsAccessEdgeConfiguration.** Команды можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell.
  
Чтобы внешние пользователи могли сотрудничать с пользователями в Skype для бизнеса Server развертывания, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки внешнего доступа пользователей. Подробные сведения см. в материале Manage XMPP Federated Partners for Your Organization. Сведения об управлении доступом для определенных федераированных доменов см. в материале Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Включить или отключить отказ от архива с помощью панели управления

1. С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **Access Edge Configuration** (Конфигурация Access Edge).
    
4. На **вкладке Конфигурация края** доступа щелкните **Глобальный,** нажмите **кнопку Изменить,** а затем нажмите **показать сведения**.
    
5. В **статье Изменение** конфигурации края доступа в статье Включить  подключение федерации и общедоступных мгновенных сообщений **выберите** или очистить отказ от архивации отправки в федеративную проверку партнеров, чтобы включить или отключить автоматически отправку обязыватель для архивации.
    
6. Щелкните **Исполнить**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Включить или отключить отказ от архива с помощью Windows PowerShell

Чтобы включить отказ от архива, установите значение свойства **EnableArchivingDisclaimer** true ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Чтобы отключить отказ от архива, установите значение свойства **EnableArchivingDisclaimer** false ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


