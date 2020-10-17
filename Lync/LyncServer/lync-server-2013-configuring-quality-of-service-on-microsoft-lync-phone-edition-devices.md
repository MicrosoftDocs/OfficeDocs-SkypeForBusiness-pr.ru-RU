---
title: Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition
description: Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0d1e4f10c6b4a550f5da25f8bd2e9fe97606255
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547945"
---
# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Хотя качество обслуживания (QoS) не включено по умолчанию для устройств, таких как iPhone, качество обслуживания включено по умолчанию для устройств под управлением Lync Phone Edition. (Эти устройства обычно называют телефонами Объединенных коммуникаций или объединенных коммуникаций). Чтобы убедиться в этом, выполните следующую команду Windows PowerShell в командной консоли Lync Server:

    Get-CsUCPhoneConfiguration

Если вы не изменяли параметры конфигурации телефона объединенных коммуникаций, то возвращаемые данные будут выглядеть примерно так:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Для рассмотрения качества обслуживания нас интересует только свойство VoiceDiffServTag. Воицедиффсервтаг представляет значение DSCP, назначенное для трафика голосовой связи, еманатинг с устройства Lync Phone Edition.

<div>


> [!NOTE]
> Параметр Voice8021p больше не поддерживается в Lync Server 2013. Параметр по-прежнему действителен для обратной совместимости с Microsoft Lync Server 2010; Однако он не оказывает никакого действия на устройствах, используемых в Lync Server 2013.



</div>

В большинстве сетей маркировка пакетов Lync Phone Edition с помощью Воицедиффсервтаг 40 не приводит к возникновению проблем. Однако для голосового трафика вместо значения 40 практически всегда используется значение DSCP 46. Для обеспечения согласованности вы можете изменить значение свойства VoiceDiffServTag на 46 для телефонов объединенных коммуникаций.

Для этого можно использовать либо Windows PowerShell, либо панель управления Lync Server. Чтобы изменить значение Воицедиффсервтаг с помощью Windows PowerShell, выполните следующую команду в командной консоли Lync Server:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Предыдущая команда изменяет глобальный набор параметров конфигурации телефона объединенных коммуникаций. Обратите внимание, что параметры телефона объединенных коммуникаций также можно задать на уровне сайта. Для изменения параметров конфигурации телефона объединенных коммуникаций на уровне сайта необходимо указать идентификатор сайта. Пример:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Чтобы одновременно изменить все параметры конфигурации телефона объединенных коммуникаций, используйте следующую команду:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Если вы предпочитаете внести это изменение с помощью панели управления Lync Server, откройте панель управления и выполните следующую процедуру:

1.  Щелкните **Clients** (Клиенты) и затем щелкните **Device Configuration** (Конфигурация устройства).

2.  На вкладке **Device Configuration** (Конфигурация устройства) дважды щелкните набор параметров, который необходимо изменить (например, **Global** (Глобальный)).

3.  В диалоговом окне **Edit Device Configuration** (Изменение конфигурации устройства) задайте в поле **Voice Quality of Service (QoS)** (Качество для голосовых служб) значение **46** и затем щелкните **Commit** (Применить).

При наличии нескольких наборов параметров вам потребуется повторить эту процедуру для каждого набора параметров телефона объединенных коммуникаций. Панель управления Lync Server не позволяет одновременно изменить несколько коллекций параметров.

Если в организации имеются устройства не на основе ОС Windows (например, iPhone), изменение параметра VoiceDiffServTag никак не повлияет на эти устройства. Дополнительные сведения об изменении значений DSCP на этих устройствах см. в соответствующих руководствах для устройств.

</div>

<span> </span>

</div>

</div>

</div>

