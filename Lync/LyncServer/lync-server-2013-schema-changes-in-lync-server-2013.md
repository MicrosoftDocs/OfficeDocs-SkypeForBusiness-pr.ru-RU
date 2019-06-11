---
title: 'Lync Server 2013: изменения схемы в Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Изменения схемы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-18_

Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить доменные службы Active Directory, расширив схему. Расширения схемы добавляют классы и атрибуты, необходимые для Lync Server 2013.

Lync Server 2013 требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты. Кроме того, многие сведения о конфигурации Lync Server 2013 хранятся в главном хранилище, а не в службах AD DS, как в предыдущих версиях. Следующая информация сохраняется в службах AD DS в Lync Server 2013:

  - **Расширения схемы**.
    
      - Расширения объекта пользователя
    
      - Расширения для классов Office Communications Server 2007 и Office Communications Server 2007 R2 обеспечивают обратную совместимость с предыдущими версиями

<!-- end list -->

  - **Data (данные** ) (хранится в расширенной схеме Lync Server и существующих классах схемы).
    
      - Универсальный код ресурса (URI) пользователя SIP и другие пользовательские параметры
    
      - Объекты контактов для таких приложений, как группа ответа и конференц-связь
    
      - Указатель на хранилище Центрального управления
    
      - Учетная запись проверки подлинности Kerberos (необязательный объект компьютера)

В этой статье описаны изменения схемы Active Directory, необходимые для Lync Server 2013. В нем не описаны изменения схемы, которые появились в предыдущих версиях Office Communications Server. Список классов и их описаний можно найти в разделе [классы и описания схемы в Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Список атрибутов и их описание можно найти [в разделе атрибуты и описания схемы в Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Список классов с атрибутами, которые они могут содержать, можно найти [в разделе атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Префикс msRTCSIP определяет классы и атрибуты, специфичные для сервера Lync Server.

<div>

## <a name="new-active-directory-attributes"></a>Новые атрибуты Active Directory

В таблице ниже описаны атрибуты Active Directory, добавленные в Lync Server 2013.

### <a name="attributes-added-by-lync-server-2013"></a>Атрибуты, добавленные в Lync Server 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Атрибут</th>
<th>Описание</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Этот атрибут с несколькими значениями содержит идентификаторы для политик хранения, которые применяются к пользователю. Политики удержания сохраняют для пользователя элементы почтового ящика на время удержания. Этот атрибут является общим для Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Усерраутингграупид</p></td>
<td><p>Это идентификатор группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться на одном и том же внешнем сервере.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Миррорбаккендсервер</p></td>
<td><p>Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой в пуле переднего плана.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Измененные классы Active Directory

В таблице ниже описаны классы Active Directory, измененные в Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Классы, измененные в Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Классов</th>
<th>Изменение</th>
<th>Класс или атрибут</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пользователь</p></td>
<td><p>Add (Добавить): Майконтаин</p>
<p>Add (Добавить): Майконтаин</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-Усерраутингграупид</p></td>
</tr>
<tr class="even">
<td><p>Службу</p></td>
<td><p>Add (Добавить): Майконтаин</p>
<p>Add (Добавить): Майконтаин</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-Усерраутингграупид</p></td>
</tr>
<tr class="odd">
<td><p>Почта-получатель</p></td>
<td><p>Add (Добавить): Майконтаин</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Глобалтопологисеттинг</p></td>
<td><p>Add (Добавить): Майконтаин</p></td>
<td><p>msRTCSIP-Миррорбаккендсервер</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

