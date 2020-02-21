---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f80192db366f5a691724078ba8f8c6948b3472f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Удаление существующей коллекции параметров конфигурации магистрали SIP в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-22_

Параметры конфигурации линий связи SIP определяют возможности и связи между сервером-посредником и шлюзом телефонной сети общего пользования (ТСОП), IP-PBX или пограничным контроллером сеансов (SBC) на стороне поставщика услуг. Эти параметры позволяют определить:

  - Следует ли включить обход медиаданных на линиях связи.

  - Условия, при которых передаются пакеты по протоколу RTCP.

  - Требуется ли шифрование по протоколу SRTP на каждой магистрали.

При установке Microsoft Lync Server 2013 создается глобальная коллекция параметров конфигурации магистрали SIP. Эта глобальная коллекция параметров не подлежит удалению. Однако с помощью панели управления Lync Server или командлета [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) можно сбросить свойства в глобальной коллекции на значения по умолчанию. Например, если задать свойство Enable3pccRefer как True, то при сбросе глобальной коллекции для свойства Enable3pccRefer возвращается значение по умолчанию False.

Администраторы могут также создавать пользовательские параметры конфигурации магистральной линии для области сайта или службы (отдельного шлюза ТСОП); эти пользовательские параметры могут быть удалены. При удалении данных пользовательских параметров следует учитывать следующее.

  - Если удалить параметры области службы, магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к их сайту, если эти параметры существуют. Если параметры сайта не существуют, эти магистральные линии будут управляться глобальной коллекцией параметров конфигурации магистральной линии.

  - Если удалить параметры области сайта, любые магистральные линии SIP, управляемые этими параметрами, будут управляться глобальной коллекцией параметров конфигурации магистральной линии.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Удаление параметров конфигурации магистрали с помощью панели управления Lync Server

1.  В панели управления Lync Server щелкните **Маршрутизация голосовой связи** , а затем щелкните **Конфигурация магистрали**.

2.  На вкладке **Настройка линии связи** выберите коллекцию параметров конфигурации магистральной линии SIP, которую следует удалить, щелкните **Изменить**, затем нажмите **Удалить**. Чтобы удалить несколько коллекций одновременно, щелкните первую удаляемую коллекцию, затем, удерживая нажатой клавишу Ctrl, щелкайте любые другие коллекции, которые следует удалить.

3.  Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.

4.  В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.

5.  В диалоговом окне **Панель управления Microsoft Lync Server 2013** нажмите кнопку **ОК**.

6.  Если решено не удалять коллекцию, щелкните **Сохранить**, затем **Отменить все несохраненные изменения**. При появлении диалогового окна **Панель управления Microsoft Lync Server 2013** нажмите кнопку **ОК**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Удаление параметров конфигурации магистрали с помощью командлетов Windows PowerShell

Параметры конфигурации магистрали можно удалить с помощью Windows PowerShell и командлета **Remove – CsTrunkConfiguration** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Удаление заданной коллекции параметров

  - Следующая команда удаляет параметры конфигурации магистральной линии в сайте Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Удаление всех коллекций, примененных к области сайта

  - Эта команда удаляет все параметры конфигурации магистральной линии, примененные на уровне службы:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Удаление всех коллекций, где включен обход сервера-посредника

  - Следующая команда удаляет все параметры конфигурации, где был включен обход мультимедиа.
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

