---
title: Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server
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
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: Сводка. Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server.
ms.openlocfilehash: fa5385c1ca318c4a41e17088368d9928fd6d0e0b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806509"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server
 
**Сводка:** Просмотр сведений о ПИН-коде пользователя в Skype для бизнеса Server.
  
Чтобы присоединиться к конференции с телефонным доступом в качестве пользователя с проверкой подлинности, пользователю Skype для бизнеса Server с учетными данными доменных служб Active Directory (AD DS) требуется персональный идентификационный номер (PIN-код). You can view a user's PIN information from Skype for Business Server Control Panel.
  
> [!NOTE]
> Можно просмотреть сведения о состоянии ПИН, такие как когда ПИН был определен или когда был в последний раз изменен, однако сведения о состоянии не содержат самого ПИН. If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Просмотр ПИН-кода пользователя на панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. В левой панели навигации щелкните **Пользователи**.
    
4. Используйте один из следующих методов для поиска пользователя:
    
   - В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.
    
   - Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.
    
5. (Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:
    
   а. Нажмите кнопку **Добавить фильтр**.
    
   б. Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.
    
   c. В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).
    
   г. В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.
    
    > [!TIP]
    > Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку **Добавить фильтр**. 
  
   д. Нажмите кнопку **Найти**.
    
    > [!NOTE]
    > Если ПИН заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН, щелкните **Действие**, затем **Разблокировать ПИН-код**. 
  
6. Щелкните пользователя в результатах поиска, щелкните **Действие**, затем щелкните **Просмотреть состояние ПИН-кода**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о ПИН-коде пользователя с помощью Windows PowerShell

Сведения о ПИН-коде пользователя можно просмотреть с помощью Get-CsClientPinInfo управления. Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с помощью удаленной службы PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) В Skype для бизнеса Server этот процесс тот же.
  
### <a name="to-view-user-pin-information"></a>Чтобы просмотреть сведения о ПИН пользователя

Чтобы просмотреть сведения о ПИН-коде для пользователя, введите команду, аналогичную следующей, в командной оболочке Skype для бизнеса Server и нажмите ввод:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Это приведет к возврату приблизительно такой информации:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Дополнительные сведения см. в разделе справки по [cmdlet Get-CsConferenceDisclaimer.](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)
  
## <a name="see-also"></a>См. также

[Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Блокировка или разблокировка ПИН-кода пользователя в Skype для бизнеса Server](lock-or-unlock-a-user-pin.md)
