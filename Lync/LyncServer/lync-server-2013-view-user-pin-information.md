---
title: 'Lync Server 2013: Просмотр сведений о КОНТАКТах пользователя'
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
ms.openlocfilehash: b1e6f8e12e7b6d2dde684a4cf558eec0ece216a9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Просмотр сведений о ПИН-коде пользователя в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Чтобы присоединиться к Конференции с телефонным подключением в качестве пользователя, прошедшего проверку подлинности, пользователю Lync Server 2013 с учетными данными доменных служб Active Directory (AD DS) требуется персональный идентификационный номер (ПИН-код). КОНТАКТНЫЕ данные пользователя можно просмотреть на панели управления Lync Server 2013.

<div>


> [!NOTE]  
> Можно просмотреть сведения о состоянии ПИН, такие как когда ПИН был определен или когда был в последний раз изменен, однако сведения о состоянии не содержат самого ПИН. Если пользователь потерял свой ПИН-код, вы можете сбросить его, следуя инструкциям в разделе <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Настройка контакта конференц-связи с телефонным подключением пользователя в Lync Server 2013</A>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>Просмотр PIN-кода пользователя на панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  Используйте один из следующих методов для обнаружения пользователя:
    
      - В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.
    
      - Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.

5.  (Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:
    
    1.  Щелкните **Добавить фильтр**.
    
    2.  Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.
    
    3.  В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).
    
    4.  В зависимости от выбранного свойства пользователя, введите условия, которые хотели бы использовать для фильтрации результатов поиска, введя их с клавиатуры или щелкнув стрелку соответствующего раскрывающегося списка.
        
        <div>
        

        > [!TIP]  
        > Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.

        
        </div>
    
    5.  Щелкните **Поиск**.
    
    <div>
    

    > [!NOTE]  
    > Если ПИН-код заблокирован, перед определением необходимо его разблокировать. Чтобы разблокировать ПИН-код, щелкните <STRONG>Действие</STRONG>, затем <STRONG>Разблокировать ПИН-код</STRONG>.

    
    </div>

6.  Щелкните пользователя в результатах поиска, щелкните **Действие**, затем щелкните **Просмотреть состояние ПИН-кода**.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Просмотр сведений о ПИН-коде пользователя с помощью командлетов Windows PowerShell

You can view user PIN information by using the Get-CsClientPinInfo cmdlet. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-user-pin-information"></a>Порядок просмотра сведений о ПИН-коде пользователя

  - Чтобы просмотреть сведения о ПИН-коде для пользователя, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Команда возвращает примерно следующую информацию:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-ксконференцедисклаимер](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .

</div>

<div>

## <a name="see-also"></a>См. также


[Установка ПИН-кода конференц-связи с телефонным подключением пользователя в Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Блокировка и Разблокировка PIN-кода пользователя в Lync Server 2013](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

