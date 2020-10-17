---
title: 'Lync Server 2013: создание или изменение коллекции параметров конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582df13f3bcd7c1d25e8bf15ce1534992ba6aeeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514796"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Создание или изменение коллекции параметров конфигурации CDR в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.

При установке Microsoft Lync Server 2013 создается отдельная глобальная коллекция параметров конфигурации CDR. Администраторы также имеют возможность создания пользовательских параметров на уровне сайта. При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами. Например, если вы создаете параметры уровня сайта для сайта Redmond, то эти параметры (а не глобальные параметры) будут использоваться для управления CDR в Редмонде.

Параметры конфигурации CDR можно создать с помощью панели управления Lync Server или командлета [New – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . С помощью панели управления Lync Server или командлета [Set – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) можно изменять существующие параметры. Если вы используете панель управления Lync Server для создания или изменения параметров, будут доступны следующие параметры:


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
<td><p>Удостоверение</p></td>
<td><p>Уникальный идентификатор создаваемых параметров конфигурации CDR. Эти параметры можно создавать только на уровне сайта.</p></td>
</tr>
<tr class="even">
<td><p>Включение мониторинга CDRs</p></td>
<td><p>EnableCDR</p></td>
<td><p>Указывает, включен ли мониторинг регистрации вызовов (CDR).</p></td>
</tr>
<tr class="odd">
<td><p>Включение очистки CDRs</p></td>
<td><p>EnablePurging</p></td>
<td><p>Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.</p></td>
</tr>
<tr class="even">
<td><p>Хранить CDRs для максимальной продолжительности (дней)</p></td>
<td><p>кипкаллдетаилфордайс</p></td>
<td><p>Указывает количество дней, в течение которых записи CDR будут храниться в базе данных CDR. Все записи старше указанного числа дней будут автоматически удалены. (Обратите внимание на то, что очистка будет выполняться только в том случае, если очистка включена.)</p></td>
</tr>
<tr class="odd">
<td><p>Хранить данные отчета об ошибках для максимальной длительности (дней)</p></td>
<td><p>киперроррепортфордайс</p></td>
<td><p>Указывает количество дней, в течение которых хранятся отчеты об ошибках CDR. Все отчеты старше указанного числа дней будут автоматически удалены. Отчеты об ошибках CDR — это диагностические отчеты, отправляемые клиентскими приложениями.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Командлеты New-CsCdrConfiguration и Set-CsCdrConfiguration включают дополнительные параметры, недоступные в панели управления Lync Server. Для получения дополнительных сведений просмотрите разделы справки <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New – CsCdrConfiguration</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set – CsCdrConfiguration</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Создание параметров конфигурации CDR с помощью панели управления Lync Server

1.  В панели управления Lync Server щелкните **мониторинг и архивация**.

2.  На вкладке **Регистрация вызовов** нажмите кнопку **создать**.

3.  В диалоговом окне **Выбор сайта** выберите сайт, в котором будут созданы новые параметры конфигурации. Если диалоговое окно пусто, это означает, что всем сайтам уже назначена коллекция параметров конфигурации CDR. Каждый сайт может иметь только одну такую коллекцию. В этом случае можно либо удалить, либо повторно создать параметры, или просто изменить существующие параметры.

4.  В диалоговом окне **новый параметр записи сведений о вызовах (CDR)** выберите нужные параметры и нажмите кнопку **сохранить**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Изменение существующих параметров конфигурации CDR с помощью панели управления Lync Server

1.  В панели управления Lync Server щелкните **мониторинг и архивация**.

2.  Дважды щелкните изменяемую коллекцию параметров или выберите коллекцию, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**. Обратите внимание на то, что вы можете изменять только одну коллекцию за раз. Чтобы внести одни и те же изменения в несколько коллекций, используйте командную консоль Lync Server.

3.  В диалоговом окне **изменение параметров записи сведений о вызовах (CDR)** выберите нужные параметры и нажмите кнопку **сохранить**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации CDR с помощью командлетов Windows PowerShell

Вы также можете создать параметры конфигурации CDR с помощью Windows PowerShell и командлета **New – CsCdrConfiguration** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Создание новой коллекции параметров конфигурации CDR

  - Эта команда создает новую коллекцию параметров конфигурации CDR, применяемых к сайту Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Создание коллекции параметров конфигурации CDR, которые отключают регистрацию вызовов

  - Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации сведений о вызовах, которые по умолчанию позволяют отключить регистрацию сведений о вызовах, используйте команду следующим образом:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Указание нескольких значений свойств при создании новой коллекции параметров конфигурации CDR

  - Можно изменить несколько значений свойств, включив несколько параметров. Например, эта команда настраивает новые параметры для сохранения записей о вызовах в течение 30 дней и отчетов об ошибках в течение 90 дней:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

