---
title: Изменение маршрутов голосовой связи для использования нового сервера исправлений Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898901690b1caf5d57b33ffaec7231080554cca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Изменение маршрутов голосовой связи для использования нового сервера исправлений Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Эта процедура изменяет маршруты голосовой связи на использование сервера обновлений Lync Server 2013 вместо устаревшего сервера Office Communications Server 2007 R2.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>Изменение голосовых маршрутов для использования нового сервера обновлений

1.  управления Lync Server 2013

2.  На левой панели выберите пункт **Маршрутизация голоса** и щелкните **маршрут**.

3.  Нажмите кнопку **создать** , чтобы создать новый голосовой маршрут.

4.  Заполните следующие поля:
    
      - **Name (имя**): введите описательное имя маршрута голосовой связи. Для этого документа мы будем использовать **W15PSTNRoute**.
    
      - **Описание**: введите краткое описание голосового маршрута.

5.  Пропускать все оставшиеся разделы, пока не дойдете до **соответствующих шлюзов**. Нажмите **Добавить**. Выберите новый шлюз по умолчанию и нажмите кнопку **ОК**.

6.  В разделе **связанные использование PSTN**нажмите кнопку **выбрать**.

7.  На странице **Выбор записи по использованию PSTN** выберите имя записи и нажмите кнопку **ОК**.

8.  На странице **Новый голосовой маршрут** нажмите кнопку **ОК** , чтобы создать **голосовой маршрут**.

9.  На странице **Маршрутизация голоса** нажмите кнопку **маршрут**.

10. Переместите созданный маршрут в верхнюю часть списка и нажмите кнопку **Commit (сохранить**).

</div>

</div>

<span> </span>

</div>

</div>

</div>

