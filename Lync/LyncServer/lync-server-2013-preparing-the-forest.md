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
ms.openlocfilehash: ec335e95264c4588b81ea5cae8473e540e9af5a0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a>Подготовка леса для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

При подготовке леса создаются глобальные параметры и объекты Active Directory, а также универсальные группы Active Directory для использования в Lync Server 2013, а также предоставляются соответствующие разрешения на доступ к объектам Active Directory. Описание универсальных групп и глобальных параметров и объектов, созданных при подготовке леса, приведены [в статье изменения, внесенные при подготовке леса в Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).

При подготовке леса также создаются объекты, содержащие наборы свойств и описатели отображения, используемые Lync Server 2013, и хранятся в контейнере конфигурации.

<div>


> [!IMPORTANT]  
> Убедитесь, что изменения, внесенные при подготовке схемы, реплицированы на все контроллеры домена перед выполнением процедуры подготовки леса. Если репликация не выполнена, возникает ошибка.



</div>

При выполнении нового развертывания Lync Server необходимо хранить глобальные параметры в контейнере конфигурации. Если вы выполняете обновление предыдущей версии и все еще храните глобальные параметры в контейнере System, вы можете продолжить использовать этот контейнер.

Чтобы выполнить данную процедуру, вы должны быть членом группы «Администраторы предприятия» или «Администраторы домена» для корневого домена леса.

<div>

## <a name="in-this-section"></a>Содержание

  - [Выполнение подготовки леса для Lync Server 2013](lync-server-2013-running-forest-preparation.md)

  - [Использование командлетов для отмены подготовки леса для Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

