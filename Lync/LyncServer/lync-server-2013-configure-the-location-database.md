---
title: 'Lync Server 2013: Настройка базы данных местоположений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Configure the location database in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. Если вы не настраиваете базу данных местоположений и для **расположения** , требуемого в политике расположения, задано значение **Да** или **отказ**, пользователю будет предложено ввести расположение вручную.

Чтобы настроить базу данных местоположений, выполните указанные ниже действия.

1.  Заполните базу данных с сопоставлением сетевых элементов местоположениям. При использовании шлюза идентификационный номер места для экстренного реагирования (Елин) необходимо добавить Елин в поле \<CompanyName\> .

2.  Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.

3.  Опубликуйте обновленную базу данных.

<div>


> [!NOTE]  
> Кроме того, вы можете определить вспомогательную базу данных расположения, которую можно использовать при размещении базы данных местоположений. Подробности можно найти <A href="lync-server-2013-configure-a-secondary-location-information-service.md">в разделе Настройка дополнительной службы сведений о расположении в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Заполнение базы данных местоположений в Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Проверка адресов в Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Публикация базы данных местоположений из Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

