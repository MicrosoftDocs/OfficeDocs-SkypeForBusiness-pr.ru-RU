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
ms.openlocfilehash: 735833208a3e8194224dd234f551ae346cca11fe
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58622411"
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

Политики ПИН-кода можно также просматривать с помощью Windows PowerShell и Get-CsPinPolicy. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". Этот процесс в Skype для бизнеса Server.
  
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