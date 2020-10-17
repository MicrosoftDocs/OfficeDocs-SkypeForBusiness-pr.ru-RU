---
title: Lync Server 2013 контрольный список развертывания для веб-конференций
description: Lync Server 2013 контрольный список развертывания для веб-конференций.
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
ms.openlocfilehash: 6194cb71af268a45dc5c142c1814d8c1ef15c09e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562185"
---
# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Контрольный список развертывания для веб-конференций в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-30_

Как и в случае развертывания других компонентов Lync Server 2013, для развертывания веб-конференций необходимо использовать построитель топологий для создания и публикации топологии, в которой выполняется организация конференций.

<div>

## <a name="deployment-sequence"></a>Порядок развертывания

Конференц-связь можно развертывать одновременно с первоначальной топологией или после развертывания по крайней мере одного пула переднего плана или сервера Standard Edition.

</div>

<div>

## <a name="conferencing-deployment-process"></a>Процесс развертывания конференц-связи

В следующей таблице представлен обзор действий, необходимых для развертывания конференц-связи в существующей топологии.


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
<th>Действия</th>
<th>Роли и членство в группах</th>
<th>Документация</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Установка обязательного оборудования и программного обеспечения.</strong></p></td>
<td><p>Конференц-связь работает на серверах переднего плана в интерфейсном пуле и серверах Standard Edition. Для нее не существуют дополнительные требования к оборудованию или программному обеспечению помимо требований для установки этих серверов.</p>
<div>

> [!NOTE]  
> Lync Server 2013 использует Office Web Apps и сервер Office Web Apps для обработки совместного использования и отрисовки презентаций PowerPoint. Сведения об установке и настройке сервера Office Web Apps приведены в статье <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Настройка интеграции с сервером Office Web Apps и Lync Server 2013</A>.


</div></td>
<td><p>Доменный пользователь, входящий в локальную группу "Администраторы"</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Поддерживаемое оборудование для Lync Server 2013</a> в документации по поддержке</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Поддержка серверного программного обеспечения и инфраструктуры в Lync Server 2013</a> в документации по поддержке</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a> в документации по планированию.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Технические требования для архивации в Lync Server 2013</a> в документации по планированию.</p></td>
</tr>
<tr class="even">
<td><p><strong>Создание соответствующей внутренней топологии для поддержки конференц-связи</strong></p></td>
<td><p>Запустите построитель топологий, чтобы добавить Конференц-связь в топологию, а затем опубликуйте топологию.</p></td>
<td><p>Чтобы определить топологию, требуется учетная запись, входящая в локальную группу "Пользователи"</p>
<p>Чтобы опубликовать топологию, учетная запись, которая является членом группы администраторов домена и группы RTCUniversalServerAdmins, обладает разрешениями на полный доступ (чтение/запись/изменение) для общего файлового ресурса, который будет использоваться для хранилища файлов Lync Server 2013 (чтобы построитель топологии мог настроить требуемые списки DACL)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Определение и Настройка топологии в построителе топологий для Lync Server 2013</a> в документации по развертыванию.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Настройка политик конференц-связи и поддержки</strong></p></td>
<td><p>Настройте параметры конференц-связи с помощью панели управления Lync Server 2013 или консоли управления Lync Server.</p></td>
<td><p>Группа RTCUniversalServerAdmins (только для Windows PowerShell) или назначение пользователей для роли [] или CSAdministrator</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Политики конференц-связи в Lync Server 2013</a> в документации по операциям.</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 теперь включает параметр **максуплоадфилесиземб** , который позволяет ограничить размер файлов, которые могут быть отправлены во время собрания. Его значение по умолчанию — 500 МБ. Значение **MaxUploadFileSizeMb** можно изменить с помощью командлета **Set-CsConferencingConfiguration**.

**Максуплоадфилесиземб** не ограничивает параметр отправки файлов для Lync Web App. В качестве ограничения на загрузку размера файла для Lync Web App задано значение приблизительно 30MB и оно управляется файлом IIS web.config:/Датаколлабвеб/Инт \[ ext \] /Хандлер/web.config. Для настройки ограничения на загрузку размера файлов для Lync Web App, обновления `maxRequestLength` и `maxAllowedContentLength` в файле web.config, как показано ниже.

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

Необходимо обновить файл web.config для каждого сервера переднего плана.

</div>

</div>

<span> </span>

</div>

</div>

</div>

