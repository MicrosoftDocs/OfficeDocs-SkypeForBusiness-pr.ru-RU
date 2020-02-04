---
title: 'Lync Server 2013: создание и изменение новой политики версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1469bb017f9597bcd1fffba54f39e62dc0bd6e96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Создание или изменение новой политики версии клиента в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете использовать политики версии клиента, чтобы указать версии клиентов, которые поддерживаются в вашей среде. Использование клиентских версий помогает сократить затраты, связанные с поддержкой нескольких клиентских версий. Кроме того, это может улучшить взаимодействие с пользователем, так как при взаимодействии более ранних и более поздних версий клиентов доступные функции могут быть ограничены более ранней версией клиента. Вы можете создавать и изменять политики версий клиентов из панели управления Lync Server 2013 или оболочки управления Lync Server 2013.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Создание и изменение политик версий клиента с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**.
    
    <div>
    

    > [!NOTE]  
    > По умолчанию выбрана вкладка <STRONG>политика Client Version</STRONG> .

    
    </div>

4.  На странице **политики версия клиента** выполните одно из указанных ниже действий.
    
      - Чтобы создать политику версии клиента, нажмите кнопку **создать**, выберите пункт **Политика сайта**, **Политика пула**или **Политика пользователя**, а затем нажмите кнопку **ОК**.
    
      - Чтобы изменить глобальную политику или другую существующую, выберите ее и нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.

5.  На странице **изменение политики версии клиента** Создайте или измените правила, как описано в разделе [Создание или изменение нового правила политики для версий клиентов в Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Создание и изменение политик версий клиента с помощью командлетов Windows PowerShell

Вы можете создавать политики версии клиента с помощью командлета **New-ксклиентверсионполици** и изменять их с помощью командлета **Set-ксклиентверсионполици** . Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Создание политики версии клиента уровня сайта

  - Следующая команда создает новую политику версии клиента, примененную к сайту Redmond. Так как никакие дополнительные параметры не указаны, Новая политика будет использовать параметры версии клиента по умолчанию.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Создание новой политики клиентской версии для пользователей

  - Чтобы создать политику для пользователя, используйте следующую команду:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Подробные сведения можно найти в разделах справки по командлетам [New-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) и командлету [Set-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

