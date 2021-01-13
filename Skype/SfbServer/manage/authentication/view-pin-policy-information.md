---
title: Просмотр сведений о политике ПИН-кодов в Skype для бизнеса Server
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
description: Сводка. Просмотр сведений о политике ПИН-кодов для Skype для бизнеса Server.
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806529"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Просмотр сведений о политике ПИН-кодов в Skype для бизнеса Server
 
**Сводка:** Просмотр сведений о политике ПИН-кодов для Skype для бизнеса Server.
  
Вкладку "Политика ПИН-кодов" можно использовать для просмотра проверки подлинности пользователей, подключающихся к Skype для бизнеса с ПОМОЩЬЮ IP-телефонов.  Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы.
  
Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Просмотр сведений о политике ПИН-кодов на панели управления Skype для бизнеса Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.
    
4. На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик ПИН-кодов с помощью Windows PowerShell-кодов

Политики ПИН-кодов также можно просмотреть с помощью Windows PowerShell и Get-CsPinPolicy управления. Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell". В Skype для бизнеса Server этот процесс тот же.
  
### <a name="to-view-pin-policies"></a>Просмотр политик ПИН-кодов

Чтобы просмотреть сведения обо всех политиках ПИН-кодов, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:
    
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

Дополнительные сведения см. в разделе справки по [cmdlet Get-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>См. также

[Создание новой политики ПИН-кодов в Skype для бизнеса Server](create-a-new-pin-policy.md)
