---
title: 'Lync Server 2013: Настройка базы данных местоположений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9495bc0c52e8e9af4af0daa3d29304d5b25d4b7e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520266"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a>Настройка базы данных местоположений в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. Если не настроить эту базу данных и задать для параметра **Требуется местоположение** в политике местоположений значение **Да** или **Отказ**, пользователь получит запрос на ручной ввод местоположения.

Чтобы настроить базу данных местоположений, следует выполнить следующие задачи.

1.  Заполните базу данных с сопоставлением сетевых элементов местоположениям. Если вы используете шлюз с идентификационным номером расположения экстренной службы (ELIN), в поле необходимо включить ELIN \<CompanyName\> .

2.  Поверьте адрес по руководству MSAG, которое поддерживается поставщиком услуг E9-1-1.

3.  Опубликуйте обновленную базу данных.

<div>


> [!NOTE]  
> Кроме того, можно определить дополнительную базу данных местоположений, которую можно использовать вместо базы данных местоположений. Дополнительные сведения: <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Настройка службы сведений о дополнительном местоположении в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Заполнение базы данных расположений в Lync Server 2013](lync-server-2013-populate-the-location-database.md)

  - [Проверка адресов в Lync Server 2013](lync-server-2013-validate-addresses.md)

  - [Публикация базы данных местоположений из Lync Server 2013](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

