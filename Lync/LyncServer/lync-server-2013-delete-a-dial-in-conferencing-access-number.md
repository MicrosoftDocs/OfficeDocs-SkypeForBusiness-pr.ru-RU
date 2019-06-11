---
title: 'Lync Server 2013: Удаление номера доступа к конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2559b8a3e053c02a6a67ccc17ab5a1f25b46a05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Удаление номера доступа для конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Чтобы удалить номер доступа к конференц-связи с телефонным подключением, выполните указанные ниже действия.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Удаление номера доступа к конференц-связи с телефонным подключением

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации выберите **Конференция**, а затем щелкните **Номер для телефонного подключения**.

4.  На странице выберите номер доступа, который нужно удалить, в списке, нажмите кнопку **Изменить**, а затем — **Удалить**.

5.  Нажмите **ОК**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Удаление номеров доступа для конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell

Номера доступа для конференц-связи с телефонным подключением можно удалить с помощью Windows PowerShell и командлета **Remove-ксдиалинконференЦингакцесснумбер** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Чтобы удалить определенный номер доступа к конференц-связи с телефонным подключением

  - Эта команда удаляет номер доступа к конференц-связи с телефонным подключением с удостоверением sip:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Удаление всех номеров доступа для конференц-связи с телефонным подключением, назначенных определенному региону

  - Эта команда удаляет все номера доступа для конференц-связи с телефонным подключением, связанные с этим регионом:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Удаление номеров доступа для конференц-связи с телефонным подключением на основе основного языка

  - Эта команда удаляет все номера для конференц-связи с телефонным подключением, где основной язык — итальянский:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

