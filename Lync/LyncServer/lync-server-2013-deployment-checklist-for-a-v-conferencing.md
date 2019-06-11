---
title: Контрольный список развертывания Lync Server 2013 для конференц-связи с телефонным видео
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d787cbc1e2bbefcc2cb125e64ab7143ddbd6cf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a>Контрольный список развертывания для конференций/V в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-30_

Как и при развертывании других компонентов Lync Server 2013, при развертывании конференции с помощью Topology Builder требуется создать и опубликовать топологию, в которой используются Конференции.

<div>

## <a name="deployment-sequence"></a>Последовательность развертывания

Вы можете разворачивать конференции одновременно с развертыванием начальной топологии или после развертывания по крайней мере одного пула переднего плана или сервера Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Процесс развертывания конференций

В таблице ниже представлен обзор шагов, необходимых для развертывания конференций в существующей топологии.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Этап</th>
<th>Шаги</th>
<th>Роли и членство в группах</th>
<th>Документация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Установка необходимого оборудования и программного обеспечения</strong></p></td>
<td><p>Конференции выполняются на серверах переднего плана и серверах стандартных выпусков. Для нее не существует дополнительных требований к оборудованию или программному обеспечению помимо требований для установки этих серверов.</p>
<div>

> [!NOTE]  
> Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint. Подробнее об установке и настройке сервера Office Web Apps можно узнать в разделе <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с Office Web Apps Server и Lync Server 2013</A>.


</div></td>
<td><p>Пользователь домена, являющийся членом локальной группы "Администраторы"</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</p></td>
</tr>
<tr class="even">
<td><p><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></p></td>
<td><p>Запустите построитель топологии, чтобы добавить в топологию Конференц-связь, а затем опубликуйте топологию.</p></td>
<td><p>Для определения топологии требуется учетная запись члена локальной группы "Пользователи".</p>
<p>Чтобы опубликовать топологию, учетную запись, которая является членом группы "Администраторы домена" и Рткуниверсалсерверадминс, и у нее есть разрешения полного доступа (чтение/запись и изменение) в общей папке, которая будет использоваться для хранения файлов Lync Server 2013 (чтобы Topology Builder мог Настройка обязательных DACL</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определите и настройте топологию в построителе топологии для Lync Server 2013</a> в документации по развертыванию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Настройка политик конференц-связи и поддержки</strong></p></td>
<td><p>Настройте параметры конференц-связи с помощью панели управления Lync Server 2013 или командной консоли Lync Server Management Shell.</p></td>
<td><p>Группа Рткуниверсалсерверадминс (только для Windows PowerShell) или назначение пользователей для роли [] или Ксадминистратор</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Политики конференций в Lync Server 2013</a> в документации по эксплуатации.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>См. также


[Обзор конференц-связи в Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Определение требований для конференц-связи в Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

