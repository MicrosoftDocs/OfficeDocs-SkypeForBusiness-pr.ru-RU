---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Настройка доверенных серверов приложений

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-11_

Если вы создаете новый доверенный сервер приложений, в смешанной среде необходимо установить пул следующего прыжка в пул Lync Server 2013. В смешанной среде в раскрывающемся списке отображаются устаревший пул Lync Server 2010 и пул Lync Server 2013. Предыдущую версию пула выбрать нельзя.

**Выбор Lync Server 2013 в качестве следующего перехода при создании доверенного сервера приложений**

1.  Откройте построитель топологий.

2.  В области слева щелкните правой кнопкой мыши пункт **Серверы доверенных приложений**, затем щелкните **Создать пул доверенных приложений**.

3.  Введите **Полное доменное имя пула** для пула доверенных приложений и укажите, будет ли это пул с одним или несколькими серверами.

4.  Нажмите кнопку **Далее**.

5.  На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Lync Server 2013.

6.  Нажмите кнопку **Готово**.

7.  Выберите верхний узел **Lync Server** в меню **Действие** выберите действие **Опубликовать**.
    
    Убедитесь в том, что **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.

</div>

<span> </span>

</div>

</div>

</div>

