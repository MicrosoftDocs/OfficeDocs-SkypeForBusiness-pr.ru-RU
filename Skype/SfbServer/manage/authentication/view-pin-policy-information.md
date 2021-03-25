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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: Сводка. Просмотр сведений о ПИН-коде пользователя для Skype для бизнес-сервера.
ms.openlocfilehash: 80383ce7e78ba8806119121f8c27c6e469363003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119538"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Просмотр сведений о политике ПИН-кода в Skype для бизнеса Server
 
**Сводка:** Просмотр сведений о ПИН-коде пользователя для Skype для бизнес-сервера.
  
Вы можете использовать **вкладку PIN-политики** для просмотра проверки подлинности личного идентификационного номера (ПИН-кода) пользователей, подключающихся к Skype для бизнеса с ПОМОЩЬЮ IP-телефонов. Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.
  
Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Просмотр сведений о политике ПИН-кода в панели управления Skype для бизнес-серверов

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.  
    
3. На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.
    
4. На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик ПИН-кода с помощью Windows PowerShell cmdlets

Политики ПИН-кода можно также просматривать с помощью Windows PowerShell и Get-CsPinPolicy. Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс является одинаковым.
  
### <a name="to-view-pin-policies"></a>Просмотр политик PIN-кода

Чтобы просмотреть сведения обо всех политиках ПИН-кода, введите следующую команду в командной оболочке Skype для бизнес-серверов и нажмите кнопку ENTER:
    
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