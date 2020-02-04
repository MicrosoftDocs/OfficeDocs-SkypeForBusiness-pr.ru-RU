---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: fee8a8894285a321a4a0bc51a7cdf0462be7af85
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>Настройка доверенных серверов приложений

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-11_

В смешанной среде, если вы создаете новый доверенный сервер приложений, необходимо задать пул следующего прыжка в качестве пула Lync Server 2013. В смешанной среде в раскрывающемся списке отображаются стандартный пул Lync Server 2010 и пул Lync Server 2013. Выбор устаревшего пула не поддерживается.

**Выбор пункта Lync Server 2013 в качестве следующего прыжка при создании надежного сервера приложений**

1.  Открытие построителя топологии.

2.  В левой области щелкните правой кнопкой мыши **Доверенные серверы приложений** и выберите команду **создать доверенный пул приложений**.

3.  Введите **полное доменное имя пула** для доверенного пула приложений и укажите, будет ли он одним или несколькими серверами.

4.  Нажмите кнопку **Далее**.

5.  На странице **Выбор следующего прыжка** в списке выберите пул внешних интерфейсов Lync Server 2013.

6.  Нажмите **Готово**.

7.  Выберите верхний узел **Lync Server** , а затем в меню **действия** выберите команду **опубликовать**.
    
    Убедитесь, что **доверенный пул приложений** успешно создан и связан с правильным пулом переднего плана.

</div>

<span> </span>

</div>

</div>

</div>

