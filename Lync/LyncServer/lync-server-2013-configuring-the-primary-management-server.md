---
title: 'Lync Server 2013: Настройка основного сервера управления'
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
ms.openlocfilehash: 7d6cb7d0f27413449873cb8a0d8498aec230fdfd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Настройка основного сервера управления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-03-19_

Чтобы воспользоваться всеми преимуществами новых возможностей мониторинга работоспособности, включенных в Microsoft Lync Server 2013, администраторы должны сначала назначить компьютер для работы в качестве основного сервера управления; на этом компьютере необходимо установить System Center Operations Manager 2007 R2 или System Center Operations Manager 2012. Кроме того, необходимо установить поддерживаемую версию SQL Server, которая будет выступать в качестве серверной базы данных Operations Manager. Если вы используете System Center Operations Manager 2012, вы можете использовать в качестве серверной базы данных любую из указанных ниже версий SQL Server.

  - SQL Server 2008 R2 с пакетом обновления 1 (SP1)

  - SQL Server 2008 R2 с пакетом обновления 2 (SP2)

Если вы используете System Center Operations Manager 2007 R2, рекомендуется установить либо SQL Server 2005 с пакетом обновления 4, либо SQL Server 2008 с пакетом обновления 3. Вы также можете использовать SQL Server 2008 R2 в качестве серверной базы данных для System Center Operations Manager 2007 R2. Более подробную информацию о настройке SQL Server 2008 R2 для работы с System Center Operations Manager 2007 R2 можно найти в приложении 1 из этой документации.

При установке System Center Operations Manager 2012 или System Center Operations Manager 2007 R2 вам нужно установить все компоненты этого продукта, в том числе:

  - рабочую базу данных;

  - Сервер

  - консоль;

  - Командлеты Windows PowerShell

  - веб-консоль;

  - отчеты;

  - хранилище данных.

Эти компоненты и их установка не будут подробно рассмотрены в этом документе. Подробные сведения о System Center Operations Manager 2007 R2 можно найти в документации Operations Manager 2007 <http://go.microsoft.com/fwlink/p/?linkid=257526> R2 на странице System Center Operations Manager 2012 <http://go.microsoft.com/fwlink/p/?linkid=257527>по адресу. Следуйте этим инструкциям, если вы планируете использовать сервер SQL Server 2005 или SQL Server 2008 с пакетом обновления 1 в качестве серверной части базы данных.

Если вы используете System Center Operations Manager 2012, то можете использовать SQL Server 2012 в качестве серверной базы данных. Подробные сведения о SQL Server 2012 можно найти в книге электронная документация по SQL Server [http://go.microsoft.com/fwlink/p/?LinkId=257528](http://go.microsoft.com/fwlink/p/?linkid=257528)2012 по адресу.

Имейте в виду, что для развертывания Lync Server вы можете использовать только один основной сервер управления. Кроме того, несмотря на то что вы можете использовать System Center Operations Manager 2012 или System Center Operations Manager 2007 R2, вы не сможете запускать два приложения одновременно — вы можете выбрать одно из них или другое. Например, если вы используете System Center Operations Manager 2012, то все агенты System Center должны быть также запущены с помощью System Center Operations Manager 2012. У вас не может быть некоторых агентов, использующих System Center Operations Manager 2012, а другие агенты работают под управлением System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

