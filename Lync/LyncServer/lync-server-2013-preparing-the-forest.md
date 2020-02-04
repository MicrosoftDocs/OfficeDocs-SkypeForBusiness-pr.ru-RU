---
title: 'Lync Server 2013: подготовка леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Подготовка леса для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

При подготовке леса создаются глобальные параметры и объекты Active Directory, а также универсальные группы Active Directory для использования в Lync Server 2013, а также предоставляются соответствующие разрешения на доступ к объектам Active Directory. Описание универсальных групп, а также глобальных параметров и объектов, созданных с помощью подготовки леса, приведены [в разделе изменения, внесенные в процессе подготовки леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

Подготовка леса также создает объекты, которые содержат наборы свойств и спецификаторы отображения, используемые в Lync Server 2013, и сохраняет их в контейнере конфигурации.

<div>


> [!IMPORTANT]  
> Перед выполнением процедуры подготовки леса убедитесь, что изменения подготовки схемы реплицированы на все контроллеры домена. Если репликация не завершена, возникает ошибка.



</div>

Если вы выполняете развертывание Lync Server, вы должны сохранить глобальные параметры в контейнере конфигурации. Если вы обновляете более раннюю версию, но глобальные параметры по-прежнему хранятся в системном контейнере, вы можете продолжать использовать системный контейнер.

Для выполнения этой процедуры необходимо быть членом группы администраторов предприятия или администраторов домена для корневого домена леса.

<div>

## <a name="in-this-section"></a>Содержание

  - [Проведение подготовки леса для Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Использование командлетов для отмены подготовки леса в Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

