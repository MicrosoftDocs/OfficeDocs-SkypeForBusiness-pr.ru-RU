---
title: Контрольный список развертывания Lync Server 2013 для веб-конференций
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 426f6419b2127a09dd3c758cdb7d6e418e6c4fc6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Контрольный список развертывания для веб-конференций в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-30_

Как и при развертывании других компонентов Lync Server 2013, для развертывания веб-конференций требуется использование построителя топологии для создания и публикации топологии, которая включает Конференции.

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
> Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки общего просмотра и отрисовки презентаций PowerPoint. Сведения о том, как установить и настроить сервер Office Web Apps, приведены в разделе <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с Office Web Apps Server и Lync Server 2013</A>.


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
<p>Чтобы опубликовать топологию, учетную запись, которая является членом группы "Администраторы домена" и Рткуниверсалсерверадминс, и у нее есть разрешения полного доступа (чтение/запись и изменение) в общей папке, которая будет использоваться для хранения файлов Lync Server 2013 (чтобы Topology Builder мог настроить нужные DACL),</p></td>
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


Lync Server 2013 теперь включает параметр **максуплоадфилесиземб** , который ограничивает размер файлов, которые можно отправлять во время собрания. Значение по умолчанию для этого параметра — 500 МБАЙТ. Вы можете настроить **максуплоадфилесиземб** с помощью командлета **Set-ксконференЦингконфигуратион** .

**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App. Для приложения Lync Web App задано значение "примерно 30MB", а управление IIS Web. config —/Датаколлабвеб/Инт\[ext\]/Хандлер/веб.Конфиг.. Чтобы настроить предельный размер для отправки файлов в Lync Web App `maxRequestLength` , `maxAllowedContentLength` Update и в файле Web. config, как показано ниже.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

Вы должны обновить файл Web. config для каждого сервера переднего плана.

</div>

</div>

<span> </span>

</div>

</div>

</div>

