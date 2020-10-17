---
title: 'Lync Server 2013: Настройка основного сервера управления'
description: 'Lync Server 2013: Настройка основного сервера управления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43f986f4f03e96cafa27dfdd302bb98a00d8b2ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544165"
---
# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Настройка основного сервера управления в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-03-19_

Чтобы воспользоваться всеми преимуществами новых возможностей мониторинга работоспособности, включенных в состав Microsoft Lync Server 2013, администраторы должны сначала назначить компьютеру роль основного сервера управления; на этом компьютере необходимо установить System Center Operations Manager 2007 R2 или System Center Operations Manager 2012. Кроме того, необходимо установить поддерживаемую версию SQL Server, которая будет выступать в качестве внутренней базы данных Operations Manager. Если вы используете System Center Operations Manager 2012, вы можете использовать любую из следующих версий SQL Server в качестве серверной базы данных:

  - SQL Server 2008 R2 с пакетом обновления 1 (SP1)

  - SQL Server 2008 R2 с пакетом обновления 2 (SP2)

При использовании System Center Operations Manager 2007 R2 рекомендуется установить SQL Server 2005 с пакетом обновления 4 (SP4) или SQL Server 2008 с пакетом обновления 3 (SP3). Вы также можете использовать SQL Server 2008 R2 в качестве серверной базы данных для System Center Operations Manager 2007 R2. Дополнительные сведения о настройке SQL Server 2008 R2 для работы с System Center Operations Manager 2007 R2 приведены в приложении 1 этой документации.

При установке System Center Operations Manager 2012 или System Center Operations Manager 2007 R2 необходимо установить все компоненты этого продукта, в том числе:

  - рабочую базу данных;

  - Сервер

  - Текстовое

  - Командлеты Windows PowerShell

  - веб-консоль;

  - Reporting

  - хранилище данных.

Эти компоненты и их установка не будут обсуждаться подробно в этом документе. Подробные сведения о System Center Operations Manager 2007 R2 представлены в документации по Operations Manager 2007 R2 на сайте <https://go.microsoft.com/fwlink/p/?linkid=257526> , а также в документации System Center Operations manager 2012 по адресу <https://go.microsoft.com/fwlink/p/?linkid=257527> . Следуйте этим инструкциям, если вы планируете использовать SQL Server 2005 или SQL Server 2008 с пакетом обновления 1 в качестве серверной базы данных.

Если вы используете System Center Operations Manager 2012, то можете использовать SQL Server 2012 в качестве серверной базы данных. Дополнительные сведения о SQL Server 2012 вы найдете в статье электронная документация по SQL Server 2012 по адресу [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528) .

Помните, что для развертывания Lync Server можно использовать только один основной сервер управления. Кроме того, несмотря на то, что вы можете использовать System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, вы не сможете запускать два приложения одновременно — необходимо выбрать одно или другое. Например, если вы используете System Center Operations Manager 2012, то все агенты System Center также должны работать под управлением System Center Operations Manager 2012. Некоторые агенты запуска System Center Operations Manager 2012 и других агентов, работающих с System Center Operations Manager 2007 R2, не могут быть выполнены.

</div>

<span> </span>

</div>

</div>

</div>

