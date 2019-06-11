---
title: 'Lync Server 2013: создание или изменение коллекции параметров конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ec5383a8050370ba259350aed4528765838b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Создание и изменение коллекции параметров конфигурации CDR в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.

При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации CDR. Администраторы также могут создавать особые параметры на уровне сайта. Если такие параметры на уровне сайта используются, то они имеют преимущество перед глобальными параметрами. Например, если создаются параметры для сайта Redmond на уровне сайта, то эти параметры (а не глобальные параметры) будут использоваться для управления CDR на сайте Redmond.

Вы можете создавать параметры конфигурации CDR с помощью либо панели управления Lync Server, либо командлета [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . Вы можете использовать панель управления Lync Server или командлет [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) для изменения существующих параметров. Если вы используете панель управления Lync Server для создания и изменения параметров, вам будут доступны следующие параметры:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Параметр пользовательского интерфейса</th>
<th>Параметр PowerShell</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Имя</p></td>
<td><p>Identity</p></td>
<td><p>Уникальный идентификатор создаваемых параметров конфигурации CDR. Эти параметры можно создавать только на уровне сайта.</p></td>
</tr>
<tr class="even">
<td><p>Enable monitoring of CDRs (Включить мониторинг CDR)</p></td>
<td><p>EnableCDR</p></td>
<td><p>Указывает, включен ли CDR.</p></td>
</tr>
<tr class="odd">
<td><p>Enable purging of CDRs (Включить очистку CDR)</p></td>
<td><p>EnablePurging</p></td>
<td><p>Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.</p></td>
</tr>
<tr class="even">
<td><p>Keep CDRs for maximum duration (days) (Сохранять CDR не более (дней))</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Указывает число дней, в течение которых записи CDR должны храниться в базе данных CDR. Все записи старше указанного числа дней будут автоматически удаляться (обратите внимание, что удаление выполняется только при включении очистки).</p></td>
</tr>
<tr class="odd">
<td><p>Keep error report data for maximum duration (days) (Сохранять данные отчетов об ошибках не более (дней))</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR. Все отчеты старше указанного числа дней будут автоматически удаляться. Отчеты об ошибках CDR представляют собой диагностические отчеты, которые отправляют клиентские приложения.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Командлеты New-Кскдрконфигуратион и Set-Кскдрконфигуратион включают дополнительные параметры, недоступные на панели управления Lync Server. Для получения дополнительных сведений ознакомьтесь с разделами справки <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-кскдрконфигуратион</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-кскдрконфигуратион</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Создание параметров конфигурации CDR с помощью панели управления Lync Server

1.  На панели управления Lync Server откройте вкладку **наблюдение и архивация**.

2.  На вкладке **запись сведений о звонке** нажмите кнопку **создать**.

3.  В диалоговом окне **выбора сайта** выберите сайт, в котором должны быть созданы новые параметры конфигурации. Если диалоговое окно пустое, это означает, что всем вашим сайтам уже назначена коллекция параметров конфигурации CDR. На каждом сайте может быть только одна такая коллекция. В этом случае можно либо удалить параметры и создать их заново, либо просто изменить существующие параметры.

4.  В диалоговом окне **создания параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Изменение существующих параметров конфигурации CDR с помощью панели управления Lync Server

1.  На панели управления Lync Server откройте вкладку **наблюдение и архивация**.

2.  Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**. Note that you can only modify a single collection at a time. Чтобы внести одни и те же изменения в несколько коллекций, вместо этого используйте командную консоль Lync Server Management Shell.

3.  В диалоговом окне **изменения параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации CDR с помощью командлетов Windows PowerShell

Вы также можете создавать параметры конфигурации CDR с помощью Windows PowerShell и командлета **New-кскдрконфигуратион** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Создание новой коллекции параметров конфигурации CDR

  - Следующая команда создает новую коллекцию параметров конфигурации CDR, относящуюся к сайту Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Создание коллекции параметров конфигурации CDR, которая отключает регистрацию вызовов

  - Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации CDR, которая по умолчанию отключает регистрацию вызовов, используйте команду, аналогичную следующей:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Указание нескольких значений свойств при создании новой коллекции параметров конфигурации CDR

  - Можно изменить несколько значений свойств, включив несколько параметров. Например, следующая команда настраивает новые параметры таким образом, чтобы записи CDR хранились 30 дней, а отчеты об ошибках 90 дней:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Дополнительные сведения можно найти в разделе справки по командлету [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

