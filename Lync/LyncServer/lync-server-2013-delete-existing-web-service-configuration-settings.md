---
title: 'Lync Server 2013: удаление существующих параметров конфигурации веб-службы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb310836e78d46f94412018f3034a4a5f7d7173
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Удаление существующих параметров конфигурации веб-службы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Чтобы удалить параметры конфигурации веб-службы, выполните следующие действия.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>Удаление параметров конфигурации существующей веб-службы

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.

4.  На странице **Веб-служба** в поле поиска введите полностью или частично имя политики, которую требуется удалить.

5.  В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.

6.  Нажмите **ОК**.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации веб-службы с помощью командлетов Windows PowerShell

Вы можете удалить параметры конфигурации веб-службы с помощью Windows PowerShell и командлета **Remove-ксвебсервицеконфигуратион** . Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Удаление конкретной коллекции параметров конфигурации веб-служб

  - Следующая команда удаляет параметры безопасности веб-служб, относящиеся к сайту Redmond:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Удаление всех параметров конфигурации веб-служб, относящихся к области сайта

  - Следующая команда удаляет все параметры безопасности веб-служб, относящиеся к области службы:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Удаление всех параметров конфигурации веб-служб, позволяющих проверку подлинности с помощью сертификатов

  - Следующая команда удаляет все параметры безопасности веб-служб, позволяющие использовать проверку подлинности с помощью сертификатов:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

Подробности можно найти в разделе [Remove-ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка проверки подлинности на панели управления Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

