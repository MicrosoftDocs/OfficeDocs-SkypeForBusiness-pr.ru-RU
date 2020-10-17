---
title: 'Lync Server 2013: контрольный список развертывания для мониторинга'
description: 'Lync Server 2013: контрольный список развертывания для мониторинга.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for monitoring
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204874(v=OCS.15)
ms:contentKeyID: 48184080
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d3293accf6e25c20ae8391f9107ae75fef338
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568333"
---
# <a name="deployment-checklist-for-monitoring-in-lync-server-2013"></a>Контрольный список развертывания для мониторинга в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-05_

Хотя мониторинг уже установлен и активирован на каждом сервере переднего плана, существует несколько действий, которые необходимо предпринять, прежде чем вы сможете собрать данные мониторинга для Microsoft Lync Server 2013. Эти действия приведены в следующем контрольном списке.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Этап</p></td>
<td><p>Действия</p></td>
<td><p>Членство в роли и группе</p></td>
<td><p>Документация</p></td>
</tr>
<tr class="even">
<td><p><strong>Установка необходимого оборудования и программного обеспечения</strong></p></td>
<td><p>Установка поддерживаемой версии Microsoft SQL Server на компьютере, который будет работать в качестве внутреннего хранилища данных для мониторинга.</p></td>
<td><p>Пользователь домена, который также является членом группы администраторов.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в руководстве по поддержке</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в руководстве по поддержке</p></td>
</tr>
<tr class="odd">
<td><p><strong>Создание приемлемой внутренней топологии для поддержки мониторинга</strong></p></td>
<td><p>Используйте построитель топологий Lync Server 2013 для добавления в топологию баз данных мониторинга и публикации обновленной топологии.</p></td>
<td><p>Чтобы определить топологию, пользователь, который является членом локальной группы пользователей.</p>
<p>Чтобы опубликовать топологию, пользователь, который является членом группы администраторов домена и группы RTCUniversalServerAdmins.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Связывание хранилища мониторинга с пулом переднего плана в Lync Server 2013</a> в руководстве по развертыванию</p></td>
</tr>
<tr class="even">
<td><p><strong>Включение подходящих параметров мониторинга</strong></p></td>
<td><p>Включите мониторинг регистрации вызовов (CDR) и качества связи (QoE) на глобальном уровне и уровне сайта.</p></td>
<td><p>Пользователь, который является членом группы RTCUniversalServerAdmins или которому была назначена роль RBAC, предоставляющая доступ к командлетам CsCdrConfiguration и CsQoEConfiguration.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Настройка записи сведений о вызовах и параметров качества взаимодействия в Lync Server 2013</a> в руководстве по эксплуатации</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

