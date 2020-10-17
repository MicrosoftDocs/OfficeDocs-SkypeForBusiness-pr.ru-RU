---
title: 'Lync Server 2013: параметры групповой политики для Lync 2013'
description: 'Lync Server 2013: параметры групповой политики для Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6f2b26fc19653b0098ed4775df1f9c8146986c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564185"
---
# <a name="group-policy-settings-for-lync-2013"></a>Параметры групповой политики для Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

В предыдущих версиях Lync и Office Communicator был доступен автономный административный шаблон Communicator. adm для настройки параметров групповой политики клиентов. Для Lync 2013 новые файлы административных шаблонов (ADMX-и ADML-файлы) включены вместе с административным шаблоном групповой политики Office. Доступность файлов Lync 2013. ADMX и ADML позволяет загружать шаблоны и централизованно управлять параметрами групповой политики для всех приложений Office и языковых пакетов. Дополнительные сведения: "файлы административных шаблонов Office 2013 (ADMX, ADML)" в документации по Office 2013 по адресу <https://go.microsoft.com/fwlink/p/?linkid=267516> .

<div>

## <a name="client-bootstrapping-policies"></a>Политики начальной загрузки клиентов

Существует ряд политик начальной загрузки клиентов которые следует настроить до того, как пользователи смогут первый раз выполнить вход на сервер. Так как эти политики вступают в силу до того, как клиент войдет в систему и начнет получать с сервера параметры подготовки, их можно определять с помощью групповой политики. Дополнительные сведения приведены в статье [Настройка политик начальной загрузки клиентов в Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) в документации по развертыванию.

</div>

</div>

<span> </span>

</div>

</div>

</div>

