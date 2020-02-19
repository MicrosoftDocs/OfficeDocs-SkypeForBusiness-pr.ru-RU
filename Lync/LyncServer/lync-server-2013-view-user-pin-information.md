---
title: 'Lync Server 2013: Просмотр сведений о ПИН-коде пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6aa9a07a74382c6ba5fd1fc304ffe13336f57a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Просмотр сведений о ПИН-коде пользователя в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Чтобы присоединиться к Конференции с телефонным подключением в качестве пользователя, прошедшего проверку подлинности, пользователю Lync Server 2013 с учетными данными доменных служб Active Directory (AD DS) требуется персональный идентификационный номер (ПИН-код). Вы можете просмотреть сведения о ПИН-коде пользователя в панели управления Lync Server 2013.

<div>


> [!NOTE]  
> Можно просмотреть сведения о состоянии ПИН, такие как когда ПИН был определен или когда был в последний раз изменен, однако сведения о состоянии не содержат самого ПИН. Если пользователь потеряет свой ПИН-код, его можно сбросить, выполнив действия, описанные в разделе <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Настройка ПИН-кода конференц-связи с телефонным подключением в Lync Server 2013</A>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Просмотр ПИН-кода пользователя в панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Пользователи**.

4.  Используйте один из следующих методов для поиска пользователя:
    
      - В поле **Поиск пользователей** введите полное отображаемое имя или его часть, имя, фамилию, имя учетной записи диспетчер учетных записей безопасности (SAM), SIP-адрес или URI учетной записи пользователя, а затем нажмите кнопку **Найти**.
    
      - Если вы сохранили запрос, щелкните значок **Открыть запрос**, используйте диалоговое окно **Открыть**, чтобы получить запрос (USF-файл), а затем нажмите кнопку **Найти**.

5.  (Необязательно) Укажите дополнительные критерии поиска, чтобы сузить результаты:
    
    1.  Нажмите кнопку **Добавить фильтр**.
    
    2.  Введите свойство пользователя, набрав его или нажав кнопку стрелки в раскрывающемся списке, чтобы выбрать свойство.
    
    3.  В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).
    
    4.  В зависимости от выбранного свойства пользователя введите критерии, которые будут использоваться для фильтрации результатов поиска, набрав его или нажав кнопку стрелки в раскрывающемся списке.
        
        <div>
        

        > [!TIP]  
        > Чтобы добавить дополнительные пункты в запрос поиска, нажмите кнопку <STRONG>Добавить фильтр</STRONG>.

        
        </div>
    
    5.  Нажмите кнопку **Найти**.
    
    <div>
    

    > [!NOTE]  
    > Если ПИН заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН, щелкните <STRONG>Действие</STRONG>, затем <STRONG>Разблокировать ПИН-код</STRONG>.

    
    </div>

6.  Щелкните пользователя в результатах поиска, щелкните **Действие**, затем щелкните **Просмотреть состояние ПИН-кода**.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о ПИН-коде пользователя с помощью командлетов Windows PowerShell

Вы можете просматривать сведения о ПИН-коде пользователя с помощью командлета Get-CsClientPinInfo. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-user-pin-information"></a>Чтобы просмотреть сведения о ПИН пользователя

  - Чтобы просмотреть сведения о ПИН-коде для пользователя, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .

</div>

<div>

## <a name="see-also"></a>См. также


[Установка ПИН-кода для конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Блокировка и разблокировка ПИН-кода пользователя в Lync Server 2013](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

