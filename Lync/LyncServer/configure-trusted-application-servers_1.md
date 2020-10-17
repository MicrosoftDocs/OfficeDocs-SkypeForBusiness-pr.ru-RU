---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0474e3e75998e43965bd57ef4ed1f67ef8058a0b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503276"
---
# <a name="configure-trusted-application-servers"></a>Настройка доверенных серверов приложений

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

В смешанной среде, если вы создаете новый доверенный сервер приложений после объединения устаревшей топологии Office Communications Server с Lync Server 2013 и определяете новый доверенный сервер приложений с помощью построителя топологий, необходимо задать пул следующего прыжка в качестве пула Lync Server 2013. В Объединенной среде в раскрывающемся списке отображаются устаревший пул Office Communications Server и пул Lync Server 2013. Выбор устаревшего пула *не* поддерживается.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Выбор Lync Server 2013 в качестве следующего перехода при создании доверенного сервера приложений

1.  Откройте существующую топологию в окне построителя топологий.

2.  В левой панели щелкните правой кнопкой мыши **Серверы доверенных приложений**, затем щелкните **Создать пул надежных приложений**.

3.  Введите **Полное доменное имя пула** пула доверенных приложений и выберите будет ли это развертывание с одним или несколькими серверами.

4.  Нажмите кнопку **Далее**.

5.  На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Lync Server 2013.
    
    ![Диалоговое окно определения нового пула доверенных приложений](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Диалоговое окно определения нового пула доверенных приложений")  

6.  Нажмите кнопку **Готово**.

7.  Выберите верхний узел **Lync Server**, затем на панели **Действия** выберите **Опубликовать**.

8.  Убедитесь, что **пул надежных приложений** был создан успешно и связан с надлежащим интерфейсным пулом.

</div>

</div>

<span> </span>

</div>

</div>

</div>

