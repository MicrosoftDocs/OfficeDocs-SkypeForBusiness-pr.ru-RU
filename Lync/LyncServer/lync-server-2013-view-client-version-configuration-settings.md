---
title: 'Lync Server 2013: Просмотр параметров конфигурации версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec472bff967bc2a8ffb75d09e3515654487be41
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506606"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Просмотр параметров конфигурации версий клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Параметры конфигурации используются для включения и отключения управления версиями клиентов. Конфигурация глобальной версии клиента устанавливается вместе с Lync Server 2013 и используется для включения или отключения управления версиями клиентов для всего развертывания сервера. Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов. Параметры конфигурации версий клиентов можно просматривать на панели управления Lync Server 2013 или в командной консоли Lync Server 2013.

<div>


> [!NOTE]  
> Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Просмотр параметров конфигурации версий клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации **Конфигурация версии клиента** .

4.  Дважды щелкните имя конфигурации версии клиента, которую вы хотите просмотреть.

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Просмотр параметров конфигурации версий клиентов с помощью командлетов Windows PowerShell

Параметры конфигурации версий клиентов можно просмотреть с помощью командлета **Get – CsClientVersionConfiguration** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-client-version-configuration-information"></a>Просмотр сведений о конфигурации версий клиентов

  - Чтобы просмотреть сведения о всех параметрах конфигурации версии клиента, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsClientVersionConfiguration
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

Дополнительные сведения см. в разделе справки по командлету [Get – CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

