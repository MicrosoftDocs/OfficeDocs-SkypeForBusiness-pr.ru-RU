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
ms.openlocfilehash: 0b7bf02e809597092ca2212cacb3fd78336a0be2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Настройка базы данных местоположений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Чтобы включить автоматическое определение клиентами своего местоположения в сети, сначала необходимо настроить базу данных местоположений. Если не настроить эту базу данных и задать для параметра **Требуется местоположение** в политике местоположений значение **Да** или **Отказ**, пользователь получит запрос на ручной ввод местоположения.

Чтобы настроить базу данных местоположений, следует выполнить следующие задачи.

1.  Заполните базу данных с сопоставлением сетевых элементов местоположениям. Если вы используете шлюз с идентификационным номером расположения экстренной службы (ELIN), необходимо включить ELIN в поле \<CompanyName\> .

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

