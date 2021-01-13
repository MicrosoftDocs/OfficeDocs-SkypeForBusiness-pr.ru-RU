---
title: Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: Сводка. В этом разделе вы узнаете, как настроить заявление об отказе от архива для Skype для бизнеса Server.
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820669"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Настройка отказов от архива для внешних пользователей в Skype для бизнеса Server
 
**Сводка:** В этом разделе вы узнаете, как настроить заявление об отказе от архива для Skype для бизнеса Server.
  
Если ваша организация взаимодействует с внешними партнерами, необходимо сообщить им о том, что с ними архивироваться. При развертывании edge Server и включите федерацию для организации, вам будет предложено автоматически отправить заявление об отказе от архива внешним партнерам. 
  
Если необходимо изменить эту конфигурацию, можно использовать панель управления Skype для бизнеса Server или Windows PowerShell **Set-CsAccessEdgeConfiguration.** Можно запускать команды из оболочки управления Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.
  
Чтобы позволить внешним пользователям взаимодействовать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки доступа внешних пользователей. Подробные сведения см. в под управлением федераированных партнеров XMPP для вашей организации. Подробные сведения об управлении доступом для определенных федераированных доменов см. в подконтролированном доступе отдельных федераированных доменов.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Включить или отключить заявление об отказе от архива с помощью панели управления

1. Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. На левой панели навигации щелкните **Federation and External Access** (Федерация и внешний доступ), а затем щелкните **Access Edge Configuration** (Конфигурация Access Edge).
    
4. На **вкладке "Конфигурация края доступа"** щелкните **"Глобальная",** **"Изменить"** и **"Показать подробности".**
    
5. In **Edit Access Edge Configuration**, under Enable federation and public IM **connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.
    
6. Щелкните **Исполнить**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Включить или отключить заявление об отказе от архива с помощью Windows PowerShell

Чтобы включить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение True ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Чтобы отключить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение False ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


