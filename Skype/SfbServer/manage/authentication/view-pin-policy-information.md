---
title: Просмотр сведений о политике контактов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Сводка: Просмотр сведений о политике PIN-кода пользователя в Skype для бизнеса Server.'
ms.openlocfilehash: 57a54e960a0c89408f173567a78449cad21de9ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818701"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Просмотр сведений о политике контактов в Skype для бизнеса Server
 
**Сводка:** Просмотр сведений о политике PIN-кода пользователя в Skype для бизнеса Server.
  
С помощью вкладки " **политика закрепления** " можно просмотреть персональный идентификационный номер (PIN) пользователей, которые подключаются к Skype для бизнеса с помощью IP-телефонов. Чтобы использовать проверку подлинности по ПИН-коду, необходимо установить флажок **Разрешить проверку подлинности на основе ПИН-кода** в настройках веб-службы.
  
Выполните следующие действия, чтобы изменить политику ПИН-кода на уровне пользователя или узла. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Просмотр сведений о политике закрепления на панели управления Skype для бизнеса Server

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. В левой панели навигации последовательно выберите пункты **Безопасность** и **Политика ПИН-кода**.
    
4. На странице **Политика ПИН-кода** выберите политику, нажмите кнопку **Правка**, а затем щелкните **Подробнее**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell

Вы также можете просматривать политики ПИН с помощью Windows PowerShell и командлета Get-Кспинполици. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.
  
### <a name="to-view-pin-policies"></a>Просмотр политик ПИН-кодов

Чтобы просмотреть сведения обо всех политиках для ПИН-кода, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.
    
  ```PowerShell
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

Дополнительные сведения можно найти в разделе справки по командлету [Get-кспинполици](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>См. также

[Создание новой политики ПИН-кода в Skype для бизнеса Server](create-a-new-pin-policy.md)
