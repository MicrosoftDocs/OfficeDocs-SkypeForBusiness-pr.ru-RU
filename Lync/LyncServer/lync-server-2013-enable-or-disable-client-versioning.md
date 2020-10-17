---
title: 'Lync Server 2013: Включение и отключение управления версиями клиентов'
description: 'Lync Server 2013: Включение или отключение управления версиями клиентов.'
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
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546625"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Включение или отключение управления версиями клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Параметры конфигурации версий клиентов используются для включения или отключения управления версиями клиентов (глобально или для определенных сайтов). Конфигурация глобальной версии клиента устанавливается вместе с Lync Server 2013 и используется для включения или отключения управления версиями клиентов для всего развертывания сервера. Когда Глобальная конфигурация включена, все политики версий клиентов, которые вы используете, вступят в силу при попытке пользователей войти в систему. Вы можете отключить конфигурацию глобальной версии клиента, если не хотите, чтобы клиентский элемент управления версии не выполнялся. Вы можете включить или отключить управление версиями клиентов с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>


> [!NOTE]  
> Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Включение и выключение управления версиями клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .

4.  Выполните указанные ниже действия.
    
      - Чтобы глобально включить или отключить управление версиями клиентов, дважды щелкните **глобальную** конфигурацию, а затем измените параметры.
    
      - Чтобы включить или отключить управление версиями клиентов для определенного сайта, нажмите кнопку **создать**, выберите сайт, нажмите кнопку **ОК**, а затем измените параметры сайта.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Включение или отключение управления версиями клиентов с помощью командлетов Windows PowerShell

Вы можете включить или отключить управление версиями клиентов с помощью командлета **Set – CsClientVersionConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-client-versioning"></a>Включение управления версиями клиентов

  - Можно включить управление версиями клиентов, задав для свойства **Enabled** значение True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Отключение управления версиями клиентов

  - Вы можете отключить управление версиями клиентов, задав для свойства **Enabled** значение False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Дополнительные сведения см. в разделе справки для командлета [Set – CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

