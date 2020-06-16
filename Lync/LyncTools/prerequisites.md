---
title: Необходимые компоненты
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d8f0ee6a50d40f938a9f2c6f731b0a4afa647ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a>Необходимые компоненты

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-19_

Существуют различные требования к оборудованию, программному обеспечению и конфигурации системы, которые необходимы для запуска средства нагрузки и производительности Lync Server 2013.

<div>

## <a name="client-hardware-requirements"></a>Требования к оборудованию клиента

Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 на каждые 4 500 пользователей, для которых требуется имитировать нагрузку, необходим по крайней мере один выделенный компьютер, отвечающий следующим минимальным требованиям к оборудованию:

  - 1 гигабитный сетевой адаптер

  - 8 ГБ ОЗУ

  - 2 центральных процессора с двумя ядрами

</div>

<div>

## <a name="client-software-requirements"></a>Требования к клиентскому программному обеспечению

Для запуска средства нагрузки и производительности Lync Server 2013 в развертывании Lync Server 2013 Поддерживаемые операционные системы:

  - Операционная система Windows Server 2012

  - Операционная система Windows Server 2008 (64-разрядная версия)

Ваш клиентский компьютер должен отвечать следующим требованиям к программному обеспечению:

  - Необходимо установить среду выполнения [Microsoft .NET Framework 4,5](https://go.microsoft.com/fwlink/?linkid=143212) .

  - В Windows Server 2008/Windows Server 2012 компонент "возможности рабочего стола" должен быть включен.

  - Необходимо установить [распространяемый пакет Microsoft Visual C++ 2012](https://go.microsoft.com/fwlink/?linkid=143216) (x64).

  - Полностью настроенное развертывание Lync Server 2013.

<div>


> [!IMPORTANT]  
> Библиотеки Microsoft Unified Communications Managed API (UCMA) 4,0 включены в пакет установки, поэтому UCMA не требуется и не должен устанавливаться на клиентских компьютерах.



</div>

</div>

<div>

## <a name="configuration-requirements"></a>Требования к конфигурации

Компьютеры, на которых будет работать средство нагрузки и производительности Lync Server 2013, должны быть настроены в соответствии со следующими требованиями:

1.  Необходимо войти в систему с учетной записью члена группы "домен" или "Локальные администраторы".

2.  Средство нагрузочного тестирования и производительности Lync Server 2013 (LyncPerfTool.exe) не может выполняться на компьютере, на котором также установлены компоненты Lync Server 2013.

3.  На сервере переднего плана или сервере Standard Edition, на котором будут храниться учетные записи пользователей, необходимо запустить средство создания пользователей Lync Server 2013 (UserProvisioningTool.exe). При запуске средства несколько раз у каждого пользователя, для которого включена поддержка единой системы обмена сообщениями Майкрософт, должен быть уникальный номер телефона.

4.  Размер файла подкачки должен быть управляемым системой или должен быть как минимум в 1,5 раз больше объема оперативной памяти в системе.

</div>

</div>

<span> </span>

</div>

</div>

</div>

