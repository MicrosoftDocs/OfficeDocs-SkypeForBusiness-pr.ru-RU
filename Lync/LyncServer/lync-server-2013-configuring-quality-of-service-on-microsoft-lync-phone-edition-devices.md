---
title: Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Хотя качество обслуживания (QoS) не включено по умолчанию для устройств, таких как iPhone, Служба QoS включена по умолчанию для устройств под управлением Lync Phone Edition. (Эти устройства обычно называются телефонами UC или единой системы связи.) Чтобы проверить это, выполните следующую команду Windows PowerShell в командной консоли Lync Server.

    Get-CsUCPhoneConfiguration

Если вы не внесли никаких изменений в параметры конфигурации телефона в UC, вы получите информацию, которая выглядит следующим образом:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Для целей обеспечения качества обслуживания необходимо иметь только одно из этих свойств: Воицедиффсервтаг. Воицедиффсервтаг представляет значение DSCP, назначенное на голосовой трафик еманатинг с устройства Lync Phone Edition.

<div>


> [!NOTE]
> Параметр Voice8021p больше не поддерживается в Lync Server 2013. Этот параметр по-прежнему можно использовать для обеспечения обратной совместимости с Microsoft Lync Server 2010; Однако он не влияет на устройства, используемые в Lync Server 2013.



</div>

В большинстве сетей пометка пакетов Lync Phone Edition с помощью Воицедиффсервтаг в 40 не должна приводить к возникновению проблем. Однако 40 не является значением, которое обычно используется для передачи звука; Вместо этого голосовой трафик почти всегда помечается с помощью кода DSCP 46. Для обеспечения согласованности в сети может потребоваться изменить свойство Воицедиффсервтаг для телефонов с родным на 46.

Для этого можно использовать либо Windows PowerShell, либо панель управления Lync Server. Чтобы изменить значение Воицедиффсервтаг с помощью Windows PowerShell, выполните в командной консоли Lync Server следующую команду:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Предыдущая команда изменяет глобальную коллекцию параметров конфигурации телефонной связи UC. Однако обратите внимание, что параметры телефона в UC также можно назначить области сайта. Чтобы изменить параметры конфигурации телефона в UC на уровне сайта, необходимо указать идентификатор сайта. Например:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Вы также можете использовать следующую команду для одновременного изменения всех параметров настройки телефона в UC:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Если вы предпочитаете внести это изменение с помощью панели управления Lync Server, откройте панель управления и выполните описанные ниже действия.

1.  Откройте вкладку **Клиенты** и выберите пункт **Конфигурация устройства**.

2.  На вкладке **Конфигурация устройства** дважды щелкните коллекцию параметров, которые вы хотите изменить (например, **Global**).

3.  В диалоговом окне **изменение конфигурации устройства** установите для поля **качество голоса службы (QoS)** значение **46** и нажмите кнопку **сохранить**.

Если у вас несколько коллекций, вы должны повторить эти действия для каждой коллекции параметров телефона в UC. На панели управления Lync Server не разрешается одновременное изменение нескольких наборов параметров.

Если у вас есть устройства, не основанные на операционной системе Windows (например, iPhone) в вашей организации, это не повлияет на эти устройства, изменяя параметр Воицедиффсервтаг. Если вы хотите изменить значения DSCP на этих устройствах, вы должны будете ссылаться на руководство по администрированию для каждого из типов устройств.

</div>

<span> </span>

</div>

</div>

</div>

