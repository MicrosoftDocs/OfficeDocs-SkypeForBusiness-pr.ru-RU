---
title: Просмотр сведений о политике ПИН-код в Скайп для Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Сводка: Просмотр сведений политики ПИН-кода пользователя для Скайп для Business Server.'
ms.openlocfilehash: 8401f429184122539f66186c470034f2829536b3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21017157"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Просмотр сведений о политике ПИН-код в Скайп для Business Server
 
**Сводка:** Просмотр сведений политики ПИН-кода пользователя для Скайп для Business Server.
  
Для представления персонального идентификационного номера (ПИН-кода) проверки подлинности пользователей, которым подключаются к Скайп для бизнеса с IP-телефонов вкладка **Политики ПИН-кода** . Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в параметрах веб-службы.
  
Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Для просмотра сведений о политике ПИН-код в Скайп для панели управления Business Server

1.  Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.  
    
3. В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика в отношении ПИН-кодов**.
    
4. На странице **Политика в отношении ПИН-кодов** выберите политику, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell

Можно также просмотреть политики ПИН-кода с помощью командлета Get-CsPinPolicy и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876). Процесс одинаков в Скайп для Business Server.
  
### <a name="to-view-pin-policies"></a>Просмотр политик ПИН-кодов

Чтобы просмотреть сведения обо всех политиках ПИН-кода, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:
    
  ```
  Get-CsPinPolicy
  ```

Команда возвращает примерно следующую информацию:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Для получения дополнительных сведений см раздел справки для командлета [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>См. также

[Создание новой политики ПИН-код в Скайп для Business Server](create-a-new-pin-policy.md)