---
title: 'Lync Server 2013: обзор подготовки доменных служб Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4590a3aff21683b12d22a1253522d6c49f626957
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Обзор подготовки доменных служб Active Directory в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-29_

Чтобы подготовить доменные службы Active Directory для развертывания Lync Server 2013, необходимо выполнить три действия в определенной последовательности.

В следующей таблице описаны действия, необходимые для подготовки AD DS для Lync Server.

### <a name="active-directory-preparation-steps"></a>Действия по подготовке Active Directory

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Шаг</th>
<th>Описание</th>
<th>Место выполнения</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Подготовка схемы Active Directory в Lync Server 2013</a></p></td>
<td><p>Расширяет схему Active Directory, добавляя новые классы и атрибуты, используемые Lync Server.</p>
<p>Выполните один раз для каждого леса в развертывании, в котором будет развернуто Lync Server.</p></td>
<td><p>Для хозяина схемы в корневом домене каждого леса, где будет развернут сервер Lync Server.</p>
<div>

> [!NOTE]  
> Нет необходимости выполнять этот шаг в корневом домене, если у вас есть разрешения на доступ к хозяину схемы, но вы должны быть участником группы администраторов схемы в корневом домене и членом группы администраторов предприятия на хозяине схемы. В топологии леса ресурсов выполните этот шаг только в лесу ресурсов, а не в лесах пользователя. В топологии с центральным лесом выполните этот шаг только в центральном лесу, а не в лесах пользователя.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Подготовка леса для Lync Server 2013</a></p></td>
<td><p>Создает глобальные параметры и универсальные группы, используемые Lync Server.</p>
<p>Выполните один раз для каждого леса в развертывании, в котором будет развернуто Lync Server.</p></td>
<td><p>В корневом домене каждого леса, где будет развернут сервер Lync Server. Для выполнения этого действия необходимо быть членом группы администраторов предприятия.</p>
<div>

> [!NOTE]  
> В топологии леса ресурсов выполните этот шаг только в лесу ресурсов, а не в лесах пользователя. В топологии с центральным лесом выполните этот шаг только в центральном лесу, а не в лесах пользователя.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Подготовка доменов для Lync Server 2013</a></p></td>
<td><p>Добавляет разрешения для объектов, которые будут использоваться членами универсальных групп.</p>
<p>Выполнить один раз для каждого домена пользователя или домена сервера.</p>
<div>

> [!NOTE]  
> При переходе с Lync Server 2010 на Lync Server 2013 мастер развертывания может указать, что подготовка домена уже завершена. Не нужно повторно выполнять подготовку домена. Разрешения не изменились с Lync Server 2010 на Lync Server 2013.


</div></td>
<td><p>На рядовом сервере в каждом домене, где будет развернут Lync Server. Для выполнения этого действия необходимо быть членом группы администраторов домена.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013, как и Lync Server 2010, сохраняет значительную часть сведений о конфигурации в центральном хранилище управления, а не в AD DS, как в случае с Office Communications Server 2007 R2. Однако следующие сведения хранятся в доменных СЛУЖБах Active Directory:

  - **Расширения схемы**:
    
      - расширения объектов-пользователей;
    
      - Расширения для классов Office Communications Server 2007 R2 для поддержки обратной совместимости

<!-- end list -->

  - **Данные** (хранятся в расширенной схеме Lync Server и существующих классах схемы):
    
      - универсальный код ресурса (URI) SIP и другие параметры пользователя;
    
      - контактные объекты для приложений, такие как группа ответа и помощник по конференц-связи;
    
      - Указатель на центральное хранилище управления
    
      - Учетная запись для проверки подлинности Kerberos (необязательный объект-компьютер)

В Lync Server 2013 вы Делегируйте установку и администрирование, предоставляя разрешения установки для универсальной группы RTCUniversalServerAdmins, чтобы участники этой группы могли устанавливать и активировать Lync Server 2013 на локальном сервере (после добавления сервера в топология, опубликована и включена. Делегированные пользователи должны быть локальными администраторами на компьютере, на котором они устанавливаются и активируются Lync Server 2013, но они не обязательно должны быть членами группы администраторов домена. Вы также можете предоставлять разрешения для объектов в указанных подразделениях (OU), чтобы члены универсальных групп, создаваемых во время подготовки леса, могли получать доступ к этим объектам, не открывая группу "Администраторы домена".

Для новых развертываний Lync Server 2013 глобальные параметры должны храниться в контейнере конфигурации. Если в вашей организации выполняется обновление более ранней версии и у вас по-прежнему есть глобальные параметры в контейнере System, системный контейнер по-прежнему поддерживается.

</div>

<div>

## <a name="see-also"></a>См. также


[Подготовка схемы Active Directory в Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
[Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Подготовка леса для Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Подготовка доменов для Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

