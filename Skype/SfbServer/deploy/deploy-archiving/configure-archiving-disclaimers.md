---
title: Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как настроить отказ от архива для Skype для бизнеса Server.
ms.openlocfilehash: d607bf05d1aca413194a793ed08f84ca57c16f96
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392281"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
 
**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как настроить отказ от архива для Skype для бизнеса Server.
  
Если ваша организация взаимодействует с внешними партнерами, необходимо сообщить им, что вы архивировать сообщения с ними. При развертывании edge Server и включите федерацию для организации, вас спрашивают, хотите ли вы автоматически отправлять об отказе от архивизации внешним партнерам. 
  
Если вам нужно изменить эту конфигурацию, можно использовать панель управления Skype для бизнеса Server или Windows PowerShell **set-CsAccessEdgeConfiguration**. Команды можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell.
  
Чтобы внешние пользователи могли сотрудничать с пользователями в Skype для бизнеса Server развертывания, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки внешнего доступа пользователей. Подробные сведения см. в материале Manage XMPP Federated Partners for Your Organization. Сведения об управлении доступом для определенных федераированных доменов см. в материале Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Включить или отключить отказ от архива с помощью панели управления

1. С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **Access Edge Configuration** (Конфигурация Access Edge).
    
4. На **вкладке Конфигурация края** доступа щелкните **Глобальный**, нажмите **кнопку Изменить**, а затем нажмите **кнопку Показать сведения**.
    
5. В статье **Изменение** конфигурации края доступа в статье Включить подключение федерации и общедоступных мгновенных сообщений  **выберите или** уберите сообщение об отказе от архивации отправки федеративным партнерам, чтобы включить или отключить автоматическое отправку обязыватель архивации.
    
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


