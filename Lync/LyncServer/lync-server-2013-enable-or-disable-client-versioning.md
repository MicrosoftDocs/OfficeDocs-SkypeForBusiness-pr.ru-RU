---
title: 'Lync Server 2013: Включение и отключение управления версиями клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Включение и отключение управления версиями на клиентских компьютерах в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Параметры конфигурации клиентской версии используются для включения или выключения системы управления версиями на уровне клиента или для конкретных сайтов. Конфигурация глобальной версии клиента устанавливается вместе с Lync Server 2013 и используется для включения или отключения управления версиями для всего развертывания сервера. При включении глобальной конфигурации любые политики версий на вашем компьютере вступят в силу при попытке входа пользователя в систему. Если вы не хотите, чтобы клиентский элемент управления версии не появлялся, вы можете отключить конфигурацию глобальной версии клиента. Вы можете включать и отключать клиентскую версию с помощью панели управления Lync Server 2013 или оболочки управления Lync Server 2013.

<div>


> [!NOTE]  
> Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Включение и отключение управления версиями на клиентских компьютерах с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**, а затем нажмите кнопку Навигация по **конфигурации версии клиента** .

4.  Выполните указанные ниже действия.
    
      - Чтобы включить или отключить управление версиями клиента, дважды щелкните **глобальную** конфигурацию и измените параметры.
    
      - Чтобы включить или отключить клиентскую версию для определенного сайта, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, а затем измените параметры сайта.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Включение и отключение управления версиями клиента с помощью командлетов Windows PowerShell

Вы можете включить или отключить управление версиями клиента с помощью командлета **Set-ксклиентверсионконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-enable-client-versioning"></a>Включение управления версиями на клиентских компьютерах

  - Вы можете включить управление версиями клиентов, установив для свойства **Enabled** значение True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Отключение управления версиями на клиентских компьютерах

  - Чтобы отключить управление версиями клиента, задайте для свойства **Enabled** значение False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Set-ксклиентверсионконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

