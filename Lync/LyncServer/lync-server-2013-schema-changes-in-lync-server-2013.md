---
title: 'Lync Server 2013: изменения схемы в Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70b090f59c0a0f8510d778ef659def77cfd0747
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Изменения схемы в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-18_

Перед развертыванием и эксплуатацией Lync Server 2013 необходимо подготовить доменные службы Active Directory, расширив схему. Расширения схемы добавляют классы и атрибуты, необходимые для Lync Server 2013.

Lync Server 2013 требует нескольких новых классов и атрибутов и изменяет некоторые существующие классы и атрибуты. Кроме того, многие сведения о конфигурации для Lync Server 2013 хранятся в центральном хранилище управления, а не в службах AD DS, как в предыдущих версиях. Следующие сведения по-прежнему хранятся в AD DS в Lync Server 2013:

  - **Расширения схемы**:
    
      - расширения объектов-пользователей;
    
      - Расширения для классов Office Communications Server 2007 и Office Communications Server 2007 R2 для обеспечения обратной совместимости с поддерживаемыми предыдущими версиями

<!-- end list -->

  - **Данные** (хранятся в расширенной схеме Lync Server и существующих классах схемы):
    
      - универсальный код ресурса (URI) SIP и другие параметры пользователя;
    
      - контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;
    
      - Указатель на центральное хранилище управления
    
      - Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)

В этом разделе описываются изменения схемы Active Directory, необходимые для Lync Server 2013. В нем не описываются изменения схемы, представленные в предыдущих версиях Office Communications Server. Список классов и их описаний приведен [в статье классы и описания схемы в Lync Server 2013](lync-server-2013-schema-classes-and-descriptions.md). Список атрибутов и их описание приведены [в статье атрибуты и описания схемы в Lync Server 2013](lync-server-2013-schema-attributes-and-descriptions.md). Список классов с атрибутами, которые они могут содержать, приведен [в статье атрибуты схемы по классу в Lync Server 2013](lync-server-2013-schema-attributes-by-class.md).

Префикс msRTCSIP определяет классы и атрибуты, характерные для Lync Server.

<div>

## <a name="new-active-directory-attributes"></a>Новые атрибуты Active Directory

В следующей таблице описываются атрибуты Active Directory, добавленные в Lync Server 2013.

### <a name="attributes-added-by-lync-server-2013"></a>Атрибуты, добавленные Lync Server 2013

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
<td><p>Этот атрибут, поддерживающий несколько значений, содержит идентификаторы политик хранения, которые применяются к пользователю. Политики хранения определяют срок хранения элементов почтового ящика для пользователя. Этот атрибут используется совместно с Exchange 2013.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Усерраутингграупид</p></td>
<td><p>Это ИД группы маршрутизации SIP. Пользователи в одной группе будут регистрироваться в одном сервере переднего плана.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP — Миррорбаккендсервер</p></td>
<td><p>Этот атрибут используется для хранения зеркальной серверной части SQL Server, используемой интерфейсным пулом.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>Измененные классы Active Directory

В следующей таблице описываются классы Active Directory, измененные в Lync Server 2013.

### <a name="classes-modified-by-lync-server-2013"></a>Классы, измененные в Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Класс</th>
<th>Изменение</th>
<th>Класс или атрибут</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Пользователь</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP — Усерраутингграупид</p></td>
</tr>
<tr class="even">
<td><p>Контакт</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP — Усерраутингграупид</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP — Глобалтопологисеттинг</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP — Миррорбаккендсервер</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

