---
title: 'Lync Server 2013: создание или изменение новой политики версий клиентов'
description: 'Lync Server 2013: создание или изменение новой политики версий клиентов.'
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
ms.openlocfilehash: d4d100e21591a27646784161614ff6c248dc6ae6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574615"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Создание или изменение новой политики версий клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Политики версий клиентов можно использовать для указания версий клиентов, которые поддерживаются в вашей среде. С помощью управления версиями клиентов можно сократить затраты, связанные с поддержкой нескольких версий клиентов. Кроме того, это может привести к улучшению взаимодействия с пользователем, так как при взаимодействии более ранних и последующих версий клиентов доступные функции могут быть ограничены более ранней версией клиента. Политики версий клиентов можно создавать и изменять с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Создание или изменение политик версий клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой области навигации щелкните элемент **Клиенты**.
    
    <div>
    

    > [!NOTE]  
    > Окно будет открыто на вкладке <STRONG>Политика версий клиентов</STRONG> по умолчанию.

    
    </div>

4.  На странице **Политика версий клиентов** выполните одно из следующих действий.
    
      - Чтобы создать политику версий клиентов, нажмите кнопку **создать**, выберите пункт **Политика сайта**, **Политика пула**или **Политика пользователя**, а затем нажмите кнопку **ОК**.
    
      - Чтобы изменить глобальную политику или другую существующую политику версий клиентов, выберите политику, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**.

5.  На странице **изменение политики версий клиентов** Создайте или измените правила, как описано в статье [Создание или изменение нового правила политики версий клиентов в Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Создание или изменение политик версий клиентов с помощью командлетов Windows PowerShell

Политики версий клиентов можно создавать с помощью командлета **New – CsClientVersionPolicy** и изменять их с помощью командлета **Set – CsClientVersionPolicy** . Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Создание новой политики версий клиентов на уровне сайта

  - Следующая команда создает новую политику версий клиентов, применяемую к сайту Redmond. Так как никакие дополнительные параметры не указаны, Новая политика будет использовать параметры версий клиентов по умолчанию.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Создание новой политики версий клиентов на уровне пользователя

  - Чтобы создать политику на уровне пользователя, используйте команду, аналогичную следующей:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Дополнительные сведения можно найти в разделах справки для командлета [New – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) и командлета [Set – CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

