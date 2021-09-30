---
title: Просмотр сведений о политике ПИН-кода в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: Сводка. Просмотр сведений о пин-политике пользователя для Skype для бизнеса Server.
ms.openlocfilehash: fca606d00507f199e09d84604d60cc8004ad9a9b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013733"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Просмотр сведений о политике ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Просмотр сведений о пин-политике пользователя для Skype для бизнеса Server.
  
Вы можете использовать **вкладку ПОЛИТИКИ** ПИН-кода для просмотра проверки подлинности личного идентификационного номера (ПИН-кода) пользователей, подключающихся к Skype для бизнеса с IP-телефонами. Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.
  
Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Просмотр сведений о политике ПИН-кода в Skype для бизнеса Server панели управления

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой вы развернули Skype для бизнеса Server.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.  
    
3. На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.
    
4. На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик ПИН-кода с помощью Windows PowerShell cmdlets

Политики ПИН-кода можно также просматривать с помощью Windows PowerShell и Get-CsPinPolicy. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в [материале Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Этот процесс в Skype для бизнеса Server.
  
### <a name="to-view-pin-policies"></a>Просмотр политик PIN-кода

Чтобы просмотреть сведения обо всех политиках ПИН-кода, введите следующую команду в командной Skype для бизнеса Server и нажмите кнопку ENTER:
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Это приведет к возврату приблизительно такой информации:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Дополнительные сведения см. в разделе Справка для [cmdlet Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>См. также

[Создание новой политики ПИН-кода в Skype для бизнеса Server](create-a-new-pin-policy.md)