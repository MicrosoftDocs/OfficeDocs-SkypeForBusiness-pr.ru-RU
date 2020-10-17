---
title: 'Lync Server 2013: Создание параметров конфигурации качества взаимодействия'
description: 'Lync Server 2013: Создание параметров конфигурации качества взаимодействия.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279265f396fc8fcbfba80d195fc587924a2979f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562195"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Создание параметров конфигурации качества взаимодействия в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.

При установке Microsoft Lync Server 2013 создается одна глобальная коллекция параметров конфигурации QoE. Администраторы также имеют возможность создания пользовательских параметров на уровне сайта. При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами. Например, если созданы параметры уровня сайта для сайта Redmond, именно эти, а не глобальные параметры будут использоваться для управления качеством взаимодействия в сайте Redmond.

Параметры конфигурации QoE можно создать с помощью панели управления Lync Server или командлета [New – CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Если вы используете панель управления Lync Server для создания новых параметров, станут доступны следующие варианты:


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
<td><p>Уникальный идентификатор создаваемых параметров. Параметры конфигурации качества взаимодействия могут быть созданы только на уровне сайта.</p></td>
</tr>
<tr class="even">
<td><p>Разрешить отслеживание данных о качестве связи</p></td>
<td><p>EnableQoE</p></td>
<td><p>Указывает, будут ли записи качества взаимодействия собраны и сохранены в базу данных мониторинга.</p></td>
</tr>
<tr class="odd">
<td><p>Разрешить очистку данных о качестве связи</p></td>
<td><p>EnablePurging</p></td>
<td><p>Определяет, можно ли очищать записи после истечения периода времени, определенного в свойстве <strong>Хранить данные о качестве взаимодействия не дольше (дн.)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Хранить данные о качестве взаимодействия не дольше (дн.):</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Число дней хранения данных о качестве взаимодействия до удаления из базы данных. Это значение игнорируется, если очистка отключена.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Командлет New-CsQoEConfiguration содержит дополнительные параметры, недоступные в панели управления Lync Server. Для получения дополнительных сведений обратитесь к разделу справки <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New – CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Создание параметров конфигурации QoE с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В области навигации слева выберите пункт **Мониторинг и архивация**, после чего щелкните **Данные качества взаимодействия**.

4.  На странице **Данные качества взаимодействия** нажмите кнопку **Создать**.

5.  В списке **Выбор сайта** щелкните сайт, которому нужно применить политику, и нажмите кнопку **ОК**.

6.  На странице **Новый параметр качества обслуживания** сделайте следующее.
    
      - Выберите пункт **Включить мониторинг данных качества обслуживания (CDR)**, чтобы включить мониторинг.
    
      - Выберите пункт **Включить очистку данных качества обслуживания (CDR)**.
    
      - В поле **Хранить записи сведений о звонках в течение (дней)** выберите максимальное количество дней, в течение которого должны храниться записи сведений о звонках.

7.  Нажмите кнопку **Сохранить**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации QoE с помощью командлетов Windows PowerShell

Вы можете создать параметры конфигурации QoE с помощью Windows PowerShell и командлета New-CsQoEConfiguration. Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия

  - Эта команда создает новую коллекцию параметров конфигурации качества взаимодействия, применяемую на сайте Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия при отключенном мониторинге качества взаимодействия

  - Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации качества взаимодействия, которые, по умолчанию, разрешают отключать запись качества взаимодействия, используйте следующую команду:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Чтобы указать значения нескольких свойств при создании новой коллекции параметров конфигурации качества взаимодействия

  - Можно задать несколько значений свойств, включив несколько параметров. Например, эта команда настраивает новые параметры для сохранения данных качества взаимодействия в течение 30 дней и очистки старых данных в 3:00:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

