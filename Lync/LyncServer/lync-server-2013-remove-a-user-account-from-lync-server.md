---
title: 'Lync Server 2013: Удаление учетной записи пользователя из Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Удаление учетной записи пользователя из Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-22_

Для удаления ранее добавленной учетной записи пользователя в Lync Server 2013 можно использовать описанную ниже процедуру.

<div>


> [!NOTE]  
> Удаление пользователя приведет к потере всех параметров, настроенных для учетной записи пользователя. Если вы хотите временно отключить учетную запись пользователя, ознакомьтесь с разделом <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Отключение или повторное включение учетной записи пользователя для Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Удаление учетной записи пользователя с помощью командной консоли Lync Server Management Shell

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, которую вы хотите отключить или включить заново. и нажмите кнопку **найти**.

5.  В таблице выберите учетную запись пользователя, которую вы хотите удалить.

6.  В меню **действия** выберите команду **удалить из Lync Server**, и появится диалоговое окно.

7.  В диалоговом окне нажмите кнопку **ОК** , чтобы удалить пользователя.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Удаление учетных записей пользователей с помощью командлетов Windows PowerShell

Вы можете удалить учетные записи пользователей с помощью командлета Disable-CsUser. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-remove-a-user-account"></a>Удаление учетной записи пользователя

  - Чтобы удалить учетную запись пользователя, используйте командлет Disable-CsUser. Например:
    
        Disable-CsUser -Identity "Ken Myer"
    
    После запуска этой команды вы не сможете повторно активировать учетную запись и ее предыдущие параметры. Вместо этого, чтобы создать новую учетную запись для Кен мер, вам нужно будет использовать командлет Enable-CsUser.

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>См. также


[Отключение и повторное включение учетной записи пользователя для Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Включение и отключение пользователей для Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

