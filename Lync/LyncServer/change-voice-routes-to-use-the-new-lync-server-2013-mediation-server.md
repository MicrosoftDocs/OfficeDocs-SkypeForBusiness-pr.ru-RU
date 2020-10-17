---
title: Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013
description: Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545745"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a>Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Эта процедура изменяет маршруты голосовой связи для использования сервера-посредника Lync Server 2013 вместо устаревшего сервера-посредника Office Communications Server 2007 R2.

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a>Изменение маршрутов голосовых вызовов для использования нового сервера-посредника

1.  Панель управления Lync Server 2013

2.  В левой области выберите пункт **Маршрутизация голосовой связи**, а затем — **Route**.

3.  Нажмите кнопку **Создать**, чтобы создать маршрут голосовых вызовов.

4.  Заполните следующие поля.
    
      - **Имя** — введите описательное имя маршрута голосовых вызовов. Для примера мы используем имя **W15PSTNRoute**.
    
      - **Описание** — введите краткое описание маршрута голосовых вызовов.

5.  Пропустите следующие разделы до раздела **Связанные шлюзы**. Нажмите кнопку **Добавить**. Выберите новый шлюз по умолчанию и нажмите кнопку **ОК**.

6.  В разделе **Связанные использования ТСОП** нажмите кнопку **Выбрать**.

7.  На странице **Выбор записи об использовании ТСОП** выберите имя записи и нажмите кнопку **ОК**.

8.  На странице **Новый маршрут голосовой связи** нажмите кнопку **ОК**, чтобы создать **маршрут голосовой связи**.

9.  На странице **Маршрутизация голосовой связи** выберите пункт **Route**.

10. Переместите созданный маршрут в начало списка и нажмите кнопку **Сохранить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

