---
title: 'Управление номерами доступа к телефонной сети в Skype для бизнеса Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: Сводка. Сведения об управлении номерами доступа к телефонной сети в Skype для бизнеса Server.
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806489"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Управление номерами доступа к телефонной сети в Skype для бизнеса Server
 
**Сводка:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.
  
При развертывании конференц-связи с телефонным подключением необходимо настроить телефонные номера, которые пользователи смогут набирать из ТСОП, чтобы подключиться к звуковому каналу конференции. Такие телефонные номера доступа отображаются в приглашениях на собрания и на веб-странице параметров конференц-связи с телефонным подключением. 
  
В этом разделе описывается, как просматривать, изменять или удалять существующие номера доступа к телефонной связи. Дополнительные сведения о создании исходных номеров доступа к телефонной сети см. в подстройке "Настройка телефонного доступа" в [Skype для бизнеса Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Просмотр номеров доступа к телефонной связи с телефонным доступом

You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Просмотр номеров доступа для телефонного доступа с помощью панели управления Skype для бизнеса Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.
    
4. На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.
    
5. В **окне**"Правка" выберите **"Показать сведения".**
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Просмотр номеров доступа для телефонного доступа с помощью skype для бизнеса Server Management Shell

Чтобы просмотреть сведения о номерах доступа для телефонного доступа, используйте **get-CsDialInConferencingAccessNumber.**
  
Следующая команда возвращает коллекцию всех номеров доступа к телефонной сети, настроенных для использования в организации: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Ниже приводится пример типа возвращаемой информации:
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

Дополнительные сведения см. в сведениях [о get-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Изменение номеров доступа к телефонной сети

Номера доступа к телефонной сети можно изменять с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Modify dial-in access numbers by using Skype for Business Server Control Panel

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.
    
4. На странице **"Телефонный номер** доступа" выберите один из номеров доступа для телефонного доступа в списке, нажмите кнопку "Изменить" и выберите **"Показать подробности".**
    
    > [!NOTE]
    > Использование поля поиска для поиска содержимого столбца в списке номеров доступа с телефонным номером может не дать результатов, которые вы ожидаете. Вместо этого отсортировать список по интересуемого столбца, чтобы определить номер доступа к телефонной связи, который необходимо просмотреть или изменить. 
  
5. Введите **в отображаемом** номере номер телефона, который пользователи телефонной сети общего звонков (PSTN) набирают, чтобы присоединиться к конференции. 
    
    Этот номер отображается в приглашениях на собрания и на веб-странице параметров телефонной связи.
    
6. В **отображаемом имени** введите описание номера доступа к телефонной сети. Это имя, связанное с номером доступа для телефонного номера в результатах поиска Skype для бизнеса.
    
    Это имя отображается в клиенте, когда пользователь вызывает номер доступа. 
    
7. В **строке URI** введите номер E.164 номера для телефонного доступа в формате TEL URI, включая символ +перед номером и исключая пробелы. Например, tel:+14255550200.
    
    > [!NOTE]
    > Один и тот же URI линии не может повторно использоваться другим номером доступа к телефонной линии. 
  
8. В **SIP URI** сделайте следующее:
    
   В текстовом поле введите уникальный SIP URI для этого номера доступа к телефонной связи. Этот SIP URI отображается в различных расположениях, включая уведомления о вызовах и предыдущие версии клиентов Lync.
    
    > [!NOTE]
    > Один и тот же URI SIP не может повторно использоваться другим номером доступа к телефонной сети. URI SIP нельзя изменить после создания номера доступа. Единственный способ изменить URI SIP — удалить и повторно создать номер доступа. 
  
   В списке выпадающего списка щелкните домен приложения помощника по конференцию, которое поддерживает этот номер доступа к телефонной сети.
    
9. В **пуле** выберите пул, в который запущен экземпляр помощника по конференцию, который поддерживает этот номер доступа к телефонной связи.
    
    > [!NOTE]
    > Если необходимо изменить пул после создания номера доступа, необходимо использовать cmdlet **Move-CsApplicationEndpoint** или удалить и повторно создать номер доступа.
  
10. На **основном языке** выберите язык, на котором будут играть подсказки для этого номера доступа к телефонной сети. 
    
    Основной язык — это язык, который помощник по конференцию использует для ответа на вызов. Поддерживаемые языки отображаются рядом с каждым номером телефона доступа на веб-странице параметров телефонной связи.
    
11. (Необязательно) На дополнительных языках (не более **четырех)** нажмите кнопку "Добавить", выберите один или несколько дополнительных языков, которые будут поддерживаться для вызывающих на этот номер доступа по телефонной связи, а затем нажмите кнопку **"ОК".** 
    
    Для каждого номера доступа к телефонной сети можно выбрать до четырех дополнительных языков. Пользователи могут выбрать дополнительный язык перед вводом ИД конференции при наборе номера для конференции.
    
12. Чтобы добавить регион для номера доступа к телефонной связи, в области "Связанные регионы" нажмите кнопку "Добавить", выберите один или несколько регионов, связанных с телефонными планами для этого номера доступа, а затем нажмите кнопку "ОК".  
    
13. Чтобы удалить регион из номера доступа по телефонной связи, в области "Связанные регионы" щелкните регион, который нужно удалить, а затем нажмите кнопку **"Удалить".**
    
14. Щелкните **Исполнить**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Modify dial-in access numbers by using Skype for Business Server Management Shell

Чтобы изменить номера доступа к телефонной сети, используйте **cmdlet Set-CsDialInConferencingAccessNumber.**
  
Следующая команда изменяет свойство DisplayName для номера доступа к телефонной связи с идентификатором sip:RedmondDialIn@litwareinc.com. В этом примере для отображаемого имени задается "Redmond Dial-In Access Number":
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

В следующем примере номер доступа к телефонной связи с идентификатором sip:RedmondDialIn@litwareinc.com включает два региона: Редмонд и Сиэтл. Для указания городов используется параметр Regions и названия городов (два строковых значения, разделенных запятыми). Обратите внимание, что эта команда завершится с ошибкой, если города Redmond (Редмонд) и Seattle (Сиэтл) не определены в абонентских группах.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Дополнительные сведения см. в [подстроке Set-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Удаление номера доступа к присоединению к телефонной сети

You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Delete a dial-in conferencing access number by using Skype for Business Server Control Panel

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации выберите **Конференции**, а затем щелкните **Удаленный доступ (через телефонную сеть)**.
    
4. На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем нажмите **Удалить**.
    
5. Нажмите кнопку **ОК**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Delete a dial-in conferencing access number by using Skype for Business Server Management Shell

To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.
  
Следующая команда удаляет номер доступа к телефонной связи с удостоверением sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Следующая команда удаляет все номера доступа к телефонной связи, связанные с регионом "Северо-Запад":
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Следующая команда удаляет все номера доступа к телефонной сети, где основным языком является итальянский:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Дополнительные сведения см. в [remove-CsDialInConferencingAccessNumber.](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)
  

