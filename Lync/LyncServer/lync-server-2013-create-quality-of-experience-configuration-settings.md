---
title: 'Lync Server 2013: Создание параметров конфигурации качества взаимодействия'
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
ms.openlocfilehash: 0f651da026dcf73253eaccada14332a7f2f5c1f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Создание параметров конфигурации качества взаимодействия в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.

При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации QoE. Администраторы также могут создавать особые параметры на уровне сайта. При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами. Например, если созданы параметры уровня сайта для сайта Redmond, именно эти, а не глобальные параметры будут использоваться для управления качеством взаимодействия в сайте Redmond.

Параметры конфигурации QoE можно создать с помощью панели управления Lync Server или командлета [New-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Если вы используете панель управления Lync Server для создания новых параметров, вам будут доступны следующие параметры:


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
> Командлет New-Кскоеконфигуратион содержит дополнительные параметры, недоступные на панели управления Lync Server. Дополнительные сведения можно найти в разделе справки, посвященных <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">новым кскоеконфигуратион</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Создание параметров конфигурации QoE с помощью панели управления Lync Server

1.  Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator. Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.

4.  На странице **Данные качества взаимодействия** нажмите кнопку **Создать**.

5.  В разделе **Выбор сайта** щелкните сайт, к которому должна применяться эта политика, и нажмите кнопку **ОК**.

6.  На странице **Новый параметр качества обслуживания** сделайте следующее.
    
      - Выберите пункт **Включить мониторинг данных качества обслуживания (CDR)**, чтобы включить мониторинг.
    
      - Выберите пункт **Включить очистку данных качества обслуживания (CDR)**.
    
      - В поле **Хранить записи сведений о звонках в течение (дней)** выберите максимальное количество дней, в течение которого должны храниться записи сведений о звонках.

7.  Нажмите **Исполнить**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Создание параметров конфигурации QoE с помощью командлетов Windows PowerShell

Вы можете создавать параметры конфигурации QoE с помощью Windows PowerShell и командлета New-Кскоеконфигуратион. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

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

Дополнительные сведения можно найти в разделе справки по командлету [New-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

