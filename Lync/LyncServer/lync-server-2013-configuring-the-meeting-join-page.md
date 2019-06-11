---
title: 'Lync Server 2013: конфигурация страницы присоединения к собранию'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984386eb15aac3c3d2d46c9d7aaab53457915b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a>Конфигурация страницы присоединения к собранию в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-12-14_

Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, уже установлен ли клиент Lync 2013 на компьютере пользователя. Если клиент уже установлен, клиент открывает и присоединяется к собранию. Если клиент не установлен, по умолчанию открывается версия 2013 для Lync Web App.

Вы можете изменить поведение страницы присоединения к собранию, если вы хотите разрешить пользователям присоединяться к собраниям с помощью Office Communicator 2007 R2 или Lync 2010. Эти параметры конфигурации были удалены из панели управления Lync Server 2013, но их можно настроить с помощью командлета Set-Ксвебсервицеконфигуратион.

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a>Наборы страниц для присоединения к собранию — параметры Ксвебсервицеконфигуратион

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр Set-Ксвебсервицеконфигуратион</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Шовжоинусинглегациклиентлинк</p></td>
<td><p>Если установлено значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync, получают возможность присоединиться к собранию с помощью Office Communicator 2007 R2. Значение по умолчанию — False.</p></td>
</tr>
<tr class="even">
<td><p>Шовалтернатежоиноптионсекспандед</p></td>
<td><p>Если установлено значение true, дополнительные параметры для присоединения к онлайн-конференции (например, Office Communicator 2007 R2) автоматически развертываются и появятся для пользователей. Если задано значение false (по умолчанию), эти параметры будут доступны, но пользователю потребуется отобразить список параметров.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a>Настройка страницы присоединения к собранию с помощью управляющей оболочки Lync Server 2013

1.  Запустите командную консоль Lync Server 2013: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и щелкните **Командная консоль управления Lync Server**.

2.  Чтобы просмотреть параметры конфигурации веб-службы, выполните следующий командлет:
    
        Get-CsWebServiceConfiguration

3.  Выполните следующую команду, если для параметров задано значение истина или ложь, в зависимости от предпочтения (Дополнительные сведения о параметрах этого командлета можно найти в статье [Set-ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) в документации по среде управления Lync Server 2013).
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a>См. также


[Set-Ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

